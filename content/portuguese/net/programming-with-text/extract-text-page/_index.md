---
title: Extrair página de texto em arquivo PDF
linktitle: Extrair página de texto em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como extrair texto de uma página específica em arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 200
url: /pt/net/programming-with-text/extract-text-page/
---
Este tutorial irá guiá-lo através do processo de extração de texto de uma página específica em arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

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
using System.IO;
```

## Etapa 3: definir o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Passo 4: Abra o documento PDF
 Abra um documento PDF existente usando o`Document`construtor e passando o caminho para o arquivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Etapa 5: Extraia o texto de uma página específica
 Criar uma`TextAbsorber` objeto para extrair texto do documento. Aceite o absorvedor da página desejada acessando-o através do`Pages` coleção do`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Etapa 6: obtenha o texto extraído
 Acesse o texto extraído do`TextAbsorber` objeto.

```csharp
string extractedText = textAbsorber.Text;
```

## Etapa 7: salve o texto extraído
 Criar uma`TextWriter` e abra o arquivo onde deseja salvar o texto extraído. Escreva o texto extraído no arquivo e feche o fluxo.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Exemplo de código-fonte para Extrair página de texto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Crie o objeto TextAbsorber para extrair texto
TextAbsorber textAbsorber = new TextAbsorber();
//Escolha o absorvente para uma página específica
pdfDocument.Pages[1].Accept(textAbsorber);
// Obtenha o texto extraído
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Crie um gravador e abra o arquivo
TextWriter tw = new StreamWriter(dataDir);
// Escreva uma linha de texto no arquivo
tw.WriteLine(extractedText);
// Fechar o fluxo
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusão
Você extraiu com sucesso o texto de uma página específica de um documento PDF usando Aspose.PDF for .NET. O texto extraído foi salvo no arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial orienta você no processo de extração de texto de uma página específica em um arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# que acompanha demonstra as etapas necessárias para realizar esta tarefa.

#### P: Quais namespaces devo importar?

R: No arquivo de código onde você planeja extrair o texto, inclua o seguinte usando diretivas no início do arquivo:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: Como especifico o diretório do documento?

 R: No código, encontre a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como abro um documento PDF existente?

 R: Na Etapa 4, você abrirá um documento PDF existente usando o`Document` construtor e fornecendo o caminho para o arquivo PDF de entrada.

#### P: Como extraio texto de uma página específica?

 R: A Etapa 5 envolve a criação de um`TextAbsorber` objeto para extrair texto do documento PDF. Você então escolherá o absorvente para a página desejada acessando-o através do`Pages` coleção do`pdfDocument`.

#### P: Como acesso o texto extraído?

 R: A Etapa 6 orienta você no acesso ao texto extraído do`TextAbsorber` objeto.

#### P: Como salvo o texto extraído em um arquivo?

 R: Na Etapa 7, você criará um`TextWriter`, abra o arquivo onde deseja salvar o texto extraído, grave o texto extraído no arquivo e feche o fluxo.

#### P: Qual é a principal conclusão deste tutorial?

R: Seguindo este tutorial, você aprendeu como extrair texto de uma página específica de um documento PDF usando Aspose.PDF for .NET. O texto extraído foi salvo em um arquivo de saída especificado, permitindo direcionar e analisar o conteúdo do texto de páginas específicas.