# Bloco X
Bloco X - Assinatura e geração de XML Hash

Pode-se resumir o Bloco X em 3 etapas:

* Assinar XML;
* Compactar XML e gerar o Hash da compactação em base64;
* Envelopar o Hash para envio ao Webservice;

No exemplo abaixo, utilizamos a liguagem Visual FoxPro 9 para implementar a DLL feita em C#.

* Instanciando a DLL:
~~~
DECLARE XmlSignature IN "D:\Bases\NXS\Detoni\XmlSignature.dll"
oXmlSignature = CREATEOBJECT("XmlSignature.AssinadorXML")
~~~

* Primeiro devemos chamar o método `obterCertificadoRepositorio` para carregarmos o certificado em um objeto:


