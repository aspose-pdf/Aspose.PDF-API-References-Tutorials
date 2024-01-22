---
title: Extrair texto de colunas em arquivo PDF
linktitle: Extrair texto de colunas em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como extrair texto de colunas em arquivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 150
url: /pt/net/programming-with-text/extract-columns-text/
---
Este tutorial irá guiá-lo através do processo de extração de texto de colunas em arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-lo do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-lo.

## Etapa 1: configurar o projeto
1. Crie um novo projeto C# em seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: importar namespaces necessários
No arquivo de código onde você deseja extrair o texto das colunas, adicione o seguinte usando diretivas na parte superior do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Etapa 3: definir o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Passo 4: Abra o documento PDF
 Abra um documento PDF existente usando o`Document`construtor e passando o caminho para o arquivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Etapa 5: ajuste o tamanho da fonte
Reduza o tamanho da fonte dos fragmentos de texto em um fator de 0,7 para melhorar a legibilidade e representar melhor o texto em colunas.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Etapa 6: extrair texto das colunas
 Salve o documento PDF modificado em um fluxo de memória e recarregue-o como um novo documento. Então, use o`TextAbsorber` classe para extrair texto das colunas.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Etapa 7: salve o texto extraído
Salve o texto extraído em um arquivo de texto no caminho do arquivo de saída especificado.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para extrair texto de colunas usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Precisa reduzir o tamanho da fonte em pelo menos 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusão
Você extraiu com sucesso o texto das colunas de um documento PDF usando Aspose.PDF para .NET. O texto extraído foi salvo no arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial oferece um guia passo a passo sobre como extrair colunas de texto de um arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# que acompanha fornece uma demonstração prática dos procedimentos necessários.

#### P: Quais namespaces devo importar?

R: No arquivo de código onde você pretende extrair colunas de texto, inclua o seguinte usando diretivas no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### P: Como especifico o diretório do documento?

 R: Localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` no código e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como abro um documento PDF existente?

 R: Na Etapa 4, você abrirá um documento PDF existente usando o`Document` construtor e fornecendo o caminho para o arquivo PDF de entrada.

#### P: Por que o tamanho da fonte foi ajustado?

R: A Etapa 5 envolve a redução do tamanho da fonte dos fragmentos de texto por um fator de 0,7. Esse ajuste melhora a legibilidade e representa o texto colunar com mais precisão.

#### P: Como extraio texto de colunas?

 R: A etapa 6 consiste em salvar o documento PDF modificado em um fluxo de memória, recarregá-lo como um novo documento e, em seguida, usar o`TextAbsorber` classe para extrair texto das colunas.

#### P: Qual é o propósito de salvar o texto extraído?

R: Na Etapa 7, você salvará o texto extraído em um arquivo de texto no caminho do arquivo de saída especificado.

#### P: Por que reduzir o tamanho da fonte antes da extração?

R: A redução do tamanho da fonte ajuda a garantir que o texto extraído se alinhe corretamente nas colunas, proporcionando uma representação mais precisa do layout original.

#### P: Qual é a principal conclusão deste tutorial?

R: Ao seguir este tutorial, você adquiriu o conhecimento e as habilidades necessárias para extrair colunas de texto de um documento PDF usando Aspose.PDF for .NET. O texto resultante foi salvo no arquivo de saída especificado.