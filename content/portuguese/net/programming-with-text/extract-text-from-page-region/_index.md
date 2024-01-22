---
title: Extraia texto da região da página em arquivo PDF
linktitle: Extraia texto da região da página em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como extrair texto de uma região específica de uma página em arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 190
url: /pt/net/programming-with-text/extract-text-from-page-region/
---
Este tutorial irá guiá-lo através do processo de extração de texto de uma região específica em uma página em arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Etapa 5: extrair texto de uma região da página
 Criar uma`TextAbsorber` objeto para extrair texto do documento. Configurar o`TextSearchOptions` para limitar a pesquisa a uma região específica da página definida por um retângulo.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Etapa 6: obtenha o texto extraído
 Acesse o texto extraído do`TextAbsorber` objeto.

```csharp
string extractedText = absorb.Text;
```

## Etapa 7: salve o texto extraído
 Criar uma`TextWriter` e abra o arquivo onde deseja salvar o texto extraído. Escreva o texto extraído no arquivo e feche o fluxo.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Exemplo de código-fonte para extrair texto da região da página usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crie o objeto TextAbsorber para extrair texto
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Aceite o absorvente para a primeira página
pdfDocument.Pages[1].Accept(absorber);
// Obtenha o texto extraído
string extractedText = absorber.Text;
// Crie um gravador e abra o arquivo
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Escreva uma linha de texto no arquivo
tw.WriteLine(extractedText);
// Fechar o fluxo
tw.Close();
```

## Conclusão
Você extraiu com sucesso o texto de uma região específica em uma página de um documento PDF usando Aspose.PDF for .NET. O texto extraído foi salvo no arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o objetivo deste tutorial?

R: Este tutorial tem como objetivo orientá-lo no processo de extração de texto de uma região específica de uma página em um arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# que acompanha fornece instruções passo a passo para realizar essa tarefa.

#### P: Quais namespaces devo importar?

R: No arquivo de código onde você pretende extrair o texto, inclua o seguinte usando diretivas no início do arquivo:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: Como especifico o diretório do documento?

 R: Localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` no código e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como abro um documento PDF existente?

 R: Na Etapa 4, você abrirá um documento PDF existente usando o`Document` construtor e fornecendo o caminho para o arquivo PDF de entrada.

#### P: Como extraio texto de uma região específica da página?

 R: A Etapa 5 envolve a criação de um`TextAbsorber`objeto para extrair texto do documento PDF. Você então configurará o`TextSearchOptions` para definir uma região retangular específica na página usando coordenadas.

#### P: Como acesso o texto extraído?

 R: A Etapa 6 orienta você no acesso ao texto extraído do`TextAbsorber` objeto.

#### P: Como salvo o texto extraído em um arquivo?

 R: Na Etapa 7, você criará um`TextWriter`, abra o arquivo onde deseja salvar o texto extraído, grave o texto extraído no arquivo e feche o fluxo.

#### P: Qual é a principal conclusão deste tutorial?

R: Seguindo este tutorial, você aprendeu como extrair texto de uma região específica em uma página de um documento PDF usando Aspose.PDF for .NET. O texto extraído foi salvo em um arquivo de saída especificado, permitindo direcionar e analisar com precisão o conteúdo textual desejado.