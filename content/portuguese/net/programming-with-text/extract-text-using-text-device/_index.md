---
title: Extraia texto usando dispositivo de texto
linktitle: Extraia texto usando dispositivo de texto
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como extrair texto de um documento PDF usando o dispositivo de texto no Aspose.PDF for .NET.
type: docs
weight: 210
url: /pt/net/programming-with-text/extract-text-using-text-device/
---
Este tutorial irá guiá-lo através do processo de extração de texto de um documento PDF usando o Dispositivo de Texto no Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-lo do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-lo.

## Etapa 1: configurar o projeto
1. Crie um novo projeto C# em seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: importar namespaces necessários
No arquivo de código onde você deseja extrair o texto, adicione o seguinte usando diretivas na parte superior do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Etapa 3: definir o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Passo 4: Abra o documento PDF
 Abra um documento PDF existente usando o`Document`construtor e passando o caminho para o arquivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Etapa 5: extrair texto usando dispositivo de texto
 Criar uma`StringBuilder` objeto para conter o texto extraído. Itere em cada página do documento e use um`TextDevice` para extrair o texto de cada página.

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

## Etapa 6: salve o texto extraído
 Especifique o caminho do arquivo de saída e salve o texto extraído em um arquivo de texto usando o`File.WriteAllText` método.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Exemplo de código-fonte para extrair texto usando dispositivo de texto usando Aspose.PDF para .NET 
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
		// Definir opções de extração de texto - definir o modo de extração de texto (Raw ou Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Converta uma página específica e salve o texto no stream
		textDevice.Process(pdfPage, textStream);
		// Converta uma página específica e salve o texto no stream
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Fechar fluxo de memória
		textStream.Close();
		// Obtenha texto do fluxo de memória
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Salve o texto extraído em arquivo de texto
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusão
Você extraiu com sucesso o texto de um documento PDF usando o dispositivo de texto no Aspose.PDF for .NET. O texto extraído foi salvo no arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial fornece orientação sobre como extrair texto de um documento PDF usando o recurso Text Device no Aspose.PDF for .NET. O código-fonte C# que acompanha demonstra as etapas necessárias para realizar essa tarefa.

#### P: Quais namespaces devo importar?

R: No arquivo de código onde você planeja extrair o texto, inclua o seguinte usando diretivas no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### P: Como especifico o diretório do documento?

 R: No código, encontre a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como abro um documento PDF existente?

 R: Na Etapa 4, você abrirá um documento PDF existente usando o`Document` construtor e fornecendo o caminho para o arquivo PDF de entrada.

#### P: Como extraio texto usando o dispositivo de texto?

 R: A Etapa 5 envolve a criação de um`StringBuilder` objeto para conter o texto extraído. Em seguida, você percorrerá cada página do documento e usará um`TextDevice` juntamente com`TextExtractionOptions` para extrair texto de cada página.

#### P: Como salvo o texto extraído em um arquivo?

 R: Na Etapa 6, você especificará o caminho do arquivo de saída e usará o`File.WriteAllText`método para salvar o texto extraído em um arquivo de texto.

#### P: Qual é a principal conclusão deste tutorial?

R: Seguindo este tutorial, você aprendeu como aproveitar o recurso Text Device no Aspose.PDF for .NET para extrair texto de um documento PDF. O texto extraído foi salvo em um arquivo de saída especificado, permitindo manipular e utilizar o conteúdo extraído conforme necessário.