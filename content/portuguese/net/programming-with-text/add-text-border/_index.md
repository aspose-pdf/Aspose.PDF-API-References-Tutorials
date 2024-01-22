---
title: Adicionar borda de texto em arquivo PDF
linktitle: Adicionar borda de texto em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar uma borda de texto em um arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 70
url: /pt/net/programming-with-text/add-text-border/
---
Este tutorial irá guiá-lo através do processo de adição de uma borda de texto em um arquivo PDF usando Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-lo do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-lo.

## Etapa 1: configurar o projeto
1. Crie um novo projeto C# em seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: importar namespaces necessários
No arquivo de código onde você deseja adicionar a borda do texto, adicione o seguinte usando a diretiva na parte superior do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Etapa 3: definir o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Etapa 4: crie um novo objeto Documento
 Instanciar um novo`Document` objeto adicionando a seguinte linha de código:

```csharp
Document pdfDocument = new Document();
```

## Etapa 5: adicione uma página ao documento
 Adicione uma nova página ao documento usando o`Add` método do`Pages`coleção. No código fornecido, a nova página é atribuída à variável`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Etapa 6: crie um TextFragment
 Criar uma`TextFragment` objeto e forneça o texto desejado. Defina a posição do fragmento de texto usando o`Position` propriedade. No código fornecido, o texto é definido como “texto principal” e posicionado em (100, 600) na página.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Etapa 7: definir propriedades de texto
Personalize as propriedades do texto, como tamanho da fonte, tipo de fonte, cor de fundo, cor de primeiro plano, etc. No código fornecido, propriedades como tamanho de fonte, fonte, cor de fundo, cor de primeiro plano e cor de traço são definidas para o fragmento de texto.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Etapa 8: ativar a borda do texto
 Para ativar a borda do texto, defina o`DrawTextRectangleBorder`propriedade do fragmento de texto`TextState` para`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Etapa 9: adicione o TextFragment à página
 Use o`TextBuilder` classe para adicionar o`TextFragment` objeto para a página.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Passo 10: Salve o documento PDF
 Salve o documento PDF usando o`Save` método do`Document` objeto. Especifique o caminho do arquivo de saída definido na Etapa 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Exemplo de código-fonte para adicionar borda de texto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Criar novo objeto de documento
Document pdfDocument = new Document();
// Obtenha uma página específica
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Criar fragmento de texto
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Definir propriedades de texto
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Defina a propriedade StrokingColor para desenhar a borda (traçado) ao redor do retângulo de texto
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Defina o valor da propriedade DrawTextRectangleBorder como verdadeiro
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Salve o documento
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusão
Você adicionou com sucesso uma borda de texto ao seu documento PDF usando Aspose.PDF for .NET. O arquivo PDF resultante agora pode ser encontrado no caminho do arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o foco principal deste tutorial?

R: Este tutorial orienta você no processo de adição de uma borda de texto a um arquivo PDF usando a biblioteca Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias para conseguir isso.

#### P: Quais namespaces preciso importar para este tutorial?

R: No arquivo de código onde você deseja adicionar a borda do texto, importe os seguintes namespaces no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Como especifico o diretório do documento?

 R: No código, localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como posso criar um objeto Document?

 R: Na Etapa 4, você instanciará um novo`Document` objeto usando a seguinte linha de código:

```csharp
Document pdfDocument = new Document();
```

#### P: Como adiciono uma página ao documento?

 R: Na Etapa 5, você adicionará uma nova página ao documento usando o`Add` método do`Pages` coleção:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### P: Como faço para criar um TextFragment e definir sua posição?

 R: Na Etapa 6, você criará um`TextFragment`objeto e definir sua posição na página usando o`Position` propriedade:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### P: Como posso personalizar as propriedades do texto, incluindo a borda do texto?

R: Na Etapa 7, você personalizará várias propriedades de texto, como tamanho da fonte, tipo de fonte, cor de fundo, cor de primeiro plano e borda do texto:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### P: Como adiciono o TextFragment ao documento PDF?

 R: Na Etapa 9, você usará o`TextBuilder` classe para adicionar o`TextFragment` objeto para a página:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### P: Como salvo o documento PDF resultante?

 R: Depois de adicionar o texto com borda, use o`Save` método do`Document` objeto para salvar o documento PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### P: Qual é a principal conclusão deste tutorial?

R: Seguindo este tutorial, você aprendeu como aprimorar seu documento PDF adicionando uma borda de texto usando Aspose.PDF for .NET. Isso pode ser particularmente útil para enfatizar conteúdo de texto específico em seus arquivos PDF.