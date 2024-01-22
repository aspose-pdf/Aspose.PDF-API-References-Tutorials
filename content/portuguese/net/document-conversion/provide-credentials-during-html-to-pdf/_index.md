---
title: Forneça credenciais durante HTML para PDF
linktitle: Forneça credenciais durante HTML para PDF
second_title: Referência da API Aspose.PDF para .NET
description: Guia passo a passo para converter HTML em PDF fornecendo credenciais com Aspose.PDF para .NET.
type: docs
weight: 240
url: /pt/net/document-conversion/provide-credentials-during-html-to-pdf/
---
Neste tutorial, orientaremos você no processo de conversão de um arquivo HTML em PDF e, ao mesmo tempo, forneceremos credenciais ao acessar um URL seguro usando Aspose.PDF para .NET. Seguindo as etapas abaixo, você poderá converter conteúdo HTML em PDF usando as credenciais apropriadas.

## Pré-requisitos
Antes de começar, certifique-se de atender aos seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada em seu sistema.
- Um ambiente de desenvolvimento como o Visual Studio.

## Etapa 1: buscar conteúdo HTML seguro
Nesta etapa, buscaremos conteúdo HTML seguro de um URL usando as credenciais apropriadas. Use o seguinte código:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie uma solicitação para o URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Se necessário para o servidor, defina as credenciais.
request.Credentials = CredentialCache.DefaultCredentials;
// Obtenha a resposta.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Obtenha o stream que contém o conteúdo retornado pelo servidor.
Stream dataStream = response. GetResponseStream();
// Abra o stream usando um StreamReader para facilitar o acesso.
StreamReader reader = new StreamReader(dataStream);
// Leia o conteúdo.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o diretório real onde você deseja salvar o arquivo PDF resultante.

## Etapa 2: converta HTML em PDF fornecendo credenciais
Agora carregaremos o conteúdo HTML recuperado e o converteremos para o formato PDF, fornecendo as credenciais apropriadas. Use o seguinte código:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://Meu.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Carregue o arquivo HTML
Document pdfDocument = new Document(stream, options);
```

## Passo 3: Salvando o arquivo PDF resultante
Finalmente, salvaremos o arquivo PDF resultante. Use o seguinte código:

```csharp
// Salve o arquivo PDF resultante
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 O código acima salva o arquivo PDF resultante com o nome do arquivo`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Exemplo de código-fonte para fornecer credenciais durante HTML para PDF usando Aspose.PDF para .NET

```csharp
try
{
	
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Crie uma solicitação para o URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Se exigido pelo servidor, defina as credenciais.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Obtenha a resposta.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Obtenha o fluxo que contém o conteúdo retornado pelo servidor.
	Stream dataStream = response.GetResponseStream();
	// Abra o stream usando um StreamReader para facilitar o acesso.
	StreamReader reader = new StreamReader(dataStream);
	// Leia o conteúdo.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// Meu.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Carregar arquivo HTML
	Document pdfDocument = new Document(stream, options);
	// Salvar arquivo resultante
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão
Neste tutorial, cobrimos o processo passo a passo de conversão de um arquivo HTML em PDF e, ao mesmo tempo, fornecemos credenciais ao acessar um URL seguro usando Aspose.PDF para .NET. Seguindo as instruções descritas acima, você poderá converter conteúdo HTML em PDF com êxito, fornecendo as credenciais corretas.

### Perguntas frequentes

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca robusta que permite aos desenvolvedores trabalhar com documentos PDF em aplicativos C#. Oferece uma ampla gama de funcionalidades, incluindo conversão de HTML para PDF.

#### P: Como posso obter conteúdo HTML seguro de um URL?

 R: Para buscar conteúdo HTML seguro de um URL, você pode usar o`WebRequest` classe em C#. Certifique-se de definir as credenciais apropriadas usando o`Credentials` propriedade.

#### P: Quais são os pré-requisitos para este tutorial?

R: Antes de prosseguir com o tutorial, certifique-se de ter os seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada em seu sistema.
- Um ambiente de desenvolvimento como o Visual Studio.

#### P: Como o Aspose.PDF for .NET lida com recursos externos durante a conversão de HTML em PDF?

 R: Aspose.PDF for .NET fornece o`HtmlLoadOptions`classe para lidar com recursos externos durante a conversão de HTML para PDF. Você pode definir as credenciais de recursos externos usando o`ExternalResourcesCredentials` propriedade.

#### P: Posso personalizar o nome do arquivo PDF resultante?

 R: Sim, você pode personalizar o nome do arquivo PDF resultante modificando o código que salva o documento PDF. Basta alterar o nome do arquivo desejado no`pdfDocument.Save()` método.