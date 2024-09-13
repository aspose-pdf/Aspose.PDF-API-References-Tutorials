---
title: Extrair texto usando dispositivo de texto
linktitle: Extrair texto usando dispositivo de texto
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a extrair texto de um documento PDF usando o Dispositivo de Texto no Aspose.PDF para .NET.
type: docs
weight: 210
url: /pt/net/programming-with-text/extract-text-using-text-device/
---
Este tutorial guiará você pelo processo de extração de texto de um documento PDF usando o Text Device no Aspose.PDF para .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-la do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-la.

## Etapa 1: Configurar o projeto
1. Crie um novo projeto C# no seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários
No arquivo de código onde você deseja extrair o texto, adicione as seguintes diretivas using no topo do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Etapa 3: Defina o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Etapa 4: Abra o documento PDF
 Abra um documento PDF existente usando o`Document`construtor e passando o caminho para o arquivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Etapa 5: Extraia texto usando o dispositivo de texto
 Criar um`StringBuilder` objeto para conter o texto extraído. Itere por cada página do documento e use um`TextDevice` para extrair o texto de cada página.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Etapa 6: Salve o texto extraído
 Especifique o caminho do arquivo de saída e salve o texto extraído em um arquivo de texto usando o`File.WriteAllText` método.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Código-fonte de exemplo para Extrair texto usando dispositivo de texto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//String para armazenar o texto extraído
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Criar dispositivo de texto
		TextDevice textDevice = new TextDevice();
		// Definir opções de extração de texto - definir modo de extração de texto (Raw ou Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Converta uma página específica e salve o texto no fluxo
		textDevice.Process(pdfPage, textStream);
		// Converta uma página específica e salve o texto no fluxo
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Fechar fluxo de memória
		textStream.Close();
		// Obter texto do fluxo de memória
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Salve o texto extraído em um arquivo de texto
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusão
Você extraiu com sucesso o texto de um documento PDF usando o Text Device no Aspose.PDF para .NET. O texto extraído foi salvo no arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o propósito deste tutorial?

R: Este tutorial fornece orientação sobre como extrair texto de um documento PDF usando o recurso Text Device no Aspose.PDF para .NET. O código-fonte C# que o acompanha demonstra as etapas necessárias para realizar essa tarefa.

#### P: Quais namespaces devo importar?

R: No arquivo de código onde você planeja extrair o texto, inclua as seguintes diretivas using no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### P: Como especifico o diretório do documento?

 A: No código, encontre a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como abro um documento PDF existente?

 R: Na Etapa 4, você abrirá um documento PDF existente usando o`Document` construtor e fornecendo o caminho para o arquivo PDF de entrada.

#### P: Como faço para extrair texto usando o Dispositivo de Texto?

 A: A etapa 5 envolve a criação de um`StringBuilder` objeto para armazenar o texto extraído. Você então iterará por cada página do documento e usará um`TextDevice` juntamente com`TextExtractionOptions` para extrair texto de cada página.

#### P: Como faço para salvar o texto extraído em um arquivo?

 R: Na Etapa 6, você especificará o caminho do arquivo de saída e usará o`File.WriteAllText`método para salvar o texto extraído em um arquivo de texto.

#### P: Qual é a principal lição deste tutorial?

R: Ao seguir este tutorial, você aprendeu como aproveitar o recurso Text Device no Aspose.PDF for .NET para extrair texto de um documento PDF. O texto extraído foi salvo em um arquivo de saída especificado, permitindo que você manipule e utilize o conteúdo extraído conforme necessário.