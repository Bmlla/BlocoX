# Bloco X - PAF-ECF
Bloco X - Assinatura e geração de XML Hash

Pode-se resumir o Bloco X em 3 etapas:

* Assinar XML;
* Compactar XML e gerar o Hash da compactação em base64;
* Envelopar o Hash para envio ao Webservice;

No exemplo abaixo, utilizamos a liguagem Visual FoxPro 9 para implementar a DLL feita em C#.

* Instanciando a DLL:
```ruby
DECLARE XmlSignature IN "D:\XmlSignature.dll"
oXmlSignature = CREATEOBJECT("XmlSignature.AssinadorXML")
```

* Primeiro devemos chamar o método `obterCertificadoRepositorio` para carregarmos o certificado em um objeto:
```ruby
oCert = oXmlSignature.obterCertificadoRepositorio("D:\atm.pfx","1234")
```

* Chamamos o método `geraAssinaturaDigitalXML` para assinarmos, gerarmos hash da compactação e recebermos o XML pronto para transmissão:
```ruby
oXmlSignature.geraAssinaturaDigitalXML("D:\","D:\TesteBaga","D:\Teste.xml",oCert,.t.)
```
  * Primeiro parâmetro: Caminho padrão onde será salvo o xml final, de nome "testeee.xml";
  * Segundo parâmetro:  Caminho caminho onde será gerado o xml assinado e compactado (formato .zip);
  * Terceiro parâmetro: Caminho onde será coletado o XML inicial, antes de ser assinado;
  * Quarto parâmetro:   Objeto certificado carregado com o método `obterCertificadoRepositorio`;
  * Quinto parâmetro:   Indica se deve ser gerado xml final com Hash, para casos de ECF (caso seja passado `false`, o xml será apenas assinado, nao gerado hash e envelopamento final)
    


