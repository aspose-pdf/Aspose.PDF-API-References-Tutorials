---
title: Girar texto usando fragmento de texto em arquivo PDF
linktitle: Girar texto usando fragmento de texto em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a girar texto usando fragmentos de texto em arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 390
url: /pt/net/programming-with-text/rotate-text-using-text-fragment/
---
Este tutorial explica como usar o Aspose.PDF para .NET para girar texto usando fragmentos de texto em arquivo PDF. O código-fonte C# fornecido demonstra o processo passo a passo.

## Pré-requisitos

Antes de prosseguir com o tutorial, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#.
- Biblioteca Aspose.PDF para .NET instalada. Você pode obtê-la no site da Aspose ou usar o NuGet para instalá-la no seu projeto.

## Etapa 1: Configurar o projeto

Comece criando um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido e adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários

Adicione as seguintes diretivas using no início do seu arquivo C# para importar os namespaces necessários:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Etapa 3: Crie o documento PDF

 Inicializar o`Document` objeto para criar um novo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 4: Adicionar uma página

 Obtenha uma página específica do documento usando o`Pages.Add()` método:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Etapa 5: Crie fragmentos de texto

 Crie múltiplos`TextFragment` objetos, defina seu texto e propriedades e especifique suas posições na página:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Ajuste o texto, as posições e outras propriedades conforme desejado.

## Etapa 6: Crie um TextBuilder e anexe fragmentos de texto

 Criar um`TextBuilder` objeto usando o`pdfPage` e anexe os fragmentos de texto à página PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Etapa 7: Salve o documento PDF

 Salve o documento PDF modificado em um arquivo usando o`Save` método:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Certifique-se de substituir`"TextFragmentTests_Rotated1_out.pdf"` com o nome do arquivo de saída desejado.

### Exemplo de código-fonte para Girar texto usando fragmento de texto usando Aspose.PDF para .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inicializar objeto de documento
Document pdfDocument = new Document();
// Obter página específica
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Criar fragmento de texto
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Definir propriedades de texto
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Criar fragmento de texto girado
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Definir propriedades de texto
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Criar fragmento de texto girado
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Definir propriedades de texto
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// criar objeto TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Anexar o fragmento de texto à página PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Salvar documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Conclusão

Parabéns! Você aprendeu com sucesso como girar texto usando fragmentos de texto em um documento PDF usando Aspose.PDF para .NET. Este tutorial forneceu um guia passo a passo, desde a criação do documento até salvar a versão modificada. Agora você pode incorporar este código em seus próprios projetos C# para manipular a rotação de texto em arquivos PDF.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Girar texto usando fragmento de texto"?

R: O tutorial "Rotate Text Using Text Fragment" tem como objetivo guiá-lo pelo processo de uso da biblioteca Aspose.PDF para .NET para girar texto usando fragmentos de texto em um documento PDF. O tutorial fornece instruções passo a passo e código de exemplo para obter essa funcionalidade.

#### P: O que significa "girar texto usando fragmentos de texto"?

R: Girar texto usando fragmentos de texto refere-se à capacidade de aplicar rotação a fragmentos de texto individuais dentro de um documento PDF usando a biblioteca Aspose.PDF. Essa técnica permite que você controle a orientação do texto em diferentes ângulos ou posições dentro do conteúdo do PDF.

#### P: Por que eu iria querer girar fragmentos de texto em um documento PDF?

R: Girar fragmentos de texto em um documento PDF pode ser útil para vários propósitos, como enfatizar conteúdo específico, criar designs artísticos ou melhorar o layout e a legibilidade.

#### P: Como configuro o projeto para o tutorial?

A: Para configurar o projeto:

1. Crie um novo projeto C# no seu ambiente de desenvolvimento integrado (IDE) preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.
3. Adicione as diretivas using necessárias ao seu arquivo C#.

#### P: Como posso criar um novo documento PDF?

 A: Para criar um novo documento PDF, inicialize um`Document`objeto da biblioteca Aspose.PDF. Você pode usar este objeto para adicionar páginas e conteúdo ao PDF.

#### P: Como faço para girar fragmentos de texto usando fragmentos de texto?

A: Para girar fragmentos de texto usando fragmentos de texto:

1.  Criar`TextFragment` objetos.
2. Defina o texto e as propriedades dos fragmentos de texto.
3. Especifique as posições dos fragmentos de texto na página.
4.  Defina o ângulo de rotação usando o`TextState.Rotation` propriedade dos fragmentos de texto.
5.  Criar um`TextBuilder`objeto e anexar os fragmentos de texto à página PDF.

#### P: Posso aplicar diferentes ângulos de rotação a diferentes fragmentos de texto?

 R: Sim, você pode aplicar diferentes ângulos de rotação a diferentes`TextFragment` objetos. Cada fragmento de texto pode ter seu próprio ângulo de rotação especificado usando o`TextState.Rotation` propriedade.

#### P: Como faço para salvar o documento PDF com fragmentos de texto girados?

 R: Para salvar o documento PDF com fragmentos de texto girados, use o`Save` método do`Document` objeto e forneça o caminho e o nome do arquivo de saída desejado.