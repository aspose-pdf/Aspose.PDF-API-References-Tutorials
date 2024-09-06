---
title: Aplicar estilo numérico em arquivo PDF
linktitle: Aplicar estilo numérico em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como aplicar um estilo de numeração a títulos em arquivo PDF usando Aspose.PDF para .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-headings/apply-number-style/
---
Neste tutorial, mostraremos passo a passo o seguinte código-fonte em C# para aplicar estilo de numeração em arquivo PDF usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também tenha conhecimento básico de programação C#.

### Etapa 1: Configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde deseja salvar o arquivo PDF gerado. Altere a variável "dataDir" para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Etapa 2: Criando o documento PDF

Criamos um novo documento PDF com dimensões e margens especificadas.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Etapa 3: Criando uma página e um contêiner flutuante

Adicionamos uma página ao documento e criamos um contêiner flutuante para organizar o conteúdo.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Etapa 4: adicione títulos com numeração

Criamos cabeçalhos com numerações especificadas e os adicionamos ao contêiner flutuante.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Etapa 5: Salvando o documento PDF

Salvamos o documento PDF gerado no diretório especificado.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Código-fonte de exemplo para Aplicar estilo numérico usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Conclusão

Neste tutorial, explicamos como aplicar um estilo de numeração a títulos em um documento PDF usando o Aspose.PDF para .NET. Agora você pode usar esse conhecimento para criar documentos PDF com numerações personalizadas para títulos.

### Perguntas frequentes sobre como aplicar estilo numérico em arquivo PDF

#### P: O que é estilo de numeração em um documento PDF?

R: O estilo de numeração se refere ao formato em que os títulos ou seções são numerados em um documento PDF. Ele pode incluir numerais, letras ou outros caracteres para fornecer uma estrutura hierárquica.

#### P: Por que preciso aplicar estilo de numeração aos títulos em um documento PDF?

A: Aplicar estilo de numeração aos títulos melhora a legibilidade e a organização do seu documento PDF. Ajuda os leitores a navegar facilmente e entender a estrutura hierárquica do conteúdo.

#### P: O que é Aspose.PDF para .NET?

A: Aspose.PDF para .NET é uma biblioteca que permite que desenvolvedores trabalhem com arquivos PDF programaticamente em aplicativos .NET. Ela fornece uma ampla gama de recursos para criar, editar, converter e manipular documentos PDF.

#### P: Como importo as bibliotecas necessárias para meu projeto C#?

R: Para importar as bibliotecas necessárias para seu projeto C#, inclua as seguintes diretivas de importação:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Essas diretivas permitem que você acesse as classes e os métodos necessários para trabalhar com documentos PDF e aplicar estilos de numeração.

#### P: Como especifico o diretório para salvar o arquivo PDF gerado?

R: No código-fonte fornecido, modifique a variável "dataDir" para especificar o diretório onde você deseja salvar o arquivo PDF gerado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho do diretório real.

#### P: Como posso criar um documento PDF com dimensões e margens especificadas?

R: Para criar um documento PDF com dimensões e margens especificadas, use o seguinte código:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### P: Como adiciono títulos com estilo de numeração ao documento PDF?

R: Para adicionar títulos com estilo de numeração ao documento PDF, use os exemplos de código fornecidos para criar títulos e personalizar seus estilos de numeração. Ajuste propriedades como texto, estilo de numeração, número inicial e sequência automática conforme necessário.

#### P: Como faço para salvar o documento PDF gerado?

 A: Para salvar o documento PDF gerado, utilize o`Save` método do`pdfDoc` objeto:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### P: Como posso confirmar se o estilo de numeração foi aplicado?

R: Abra o arquivo PDF gerado para verificar se o estilo de numeração especificado foi aplicado aos títulos.

#### P: Posso personalizar ainda mais o estilo de numeração?

 R: Sim, você pode personalizar ainda mais o estilo de numeração ajustando as propriedades do`Heading` objetos, como tipo de estilo de numeração, número inicial e sequência automática.

#### P: Posso aplicar diferentes estilos de numeração a diferentes seções do documento?

 R: Sim, você pode aplicar diferentes estilos de numeração a diferentes seções do documento criando vários`Heading` objetos com diferentes estilos e sequências.