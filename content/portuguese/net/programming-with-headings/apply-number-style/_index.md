---
title: Aplicar estilo numérico em arquivo PDF
linktitle: Aplicar estilo numérico em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como aplicar um estilo de numeração a títulos em arquivos PDF usando Aspose.PDF for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-headings/apply-number-style/
---
Neste tutorial, orientaremos você através do seguinte código-fonte C#, passo a passo, para aplicar o estilo de numeração em um arquivo PDF usando Aspose.PDF para .NET.

Certifique-se de ter instalado a biblioteca Aspose.PDF e configurado seu ambiente de desenvolvimento antes de começar. Também possui conhecimentos básicos de programação C#.

### Etapa 1: configuração do diretório de documentos

No código-fonte fornecido, você precisa especificar o diretório onde deseja salvar o arquivo PDF gerado. Altere a variável “dataDir” para o diretório desejado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Passo 2: Criando o Documento PDF

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

### Passo 5: Salvando o Documento PDF

Salvamos o documento PDF gerado no diretório especificado.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Exemplo de código-fonte para Aplicar estilo numérico usando Aspose.PDF para .NET 
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

Neste tutorial, explicamos como aplicar um estilo de numeração aos títulos de um documento PDF usando Aspose.PDF for .NET. Agora você pode usar esse conhecimento para criar documentos PDF com numeração personalizada para títulos.

### Perguntas frequentes para aplicar estilo de número em arquivo PDF

#### P: Qual é o estilo de numeração em um documento PDF?

R: O estilo de numeração refere-se ao formato no qual os títulos ou seções são numerados em um documento PDF. Pode incluir números, letras ou outros caracteres para fornecer uma estrutura hierárquica.

#### P: Por que eu precisaria aplicar um estilo de numeração aos títulos de um documento PDF?

R: Aplicar estilo de numeração aos títulos melhora a legibilidade e a organização do seu documento PDF. Ajuda os leitores a navegar e compreender facilmente a estrutura hierárquica do conteúdo.

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca que permite aos desenvolvedores trabalhar com arquivos PDF programaticamente em aplicativos .NET. Ele oferece uma ampla gama de recursos para criar, editar, converter e manipular documentos PDF.

#### P: Como importo as bibliotecas necessárias para meu projeto C#?

R: Para importar as bibliotecas necessárias para o seu projeto C#, inclua as seguintes diretivas de importação:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Estas diretivas permitem acessar as classes e métodos necessários para trabalhar com documentos PDF e aplicar estilos de numeração.

#### P: Como especifico o diretório para salvar o arquivo PDF gerado?

R: No código-fonte fornecido, modifique a variável "dataDir" para especificar o diretório onde deseja salvar o arquivo PDF gerado.

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

#### P: Como salvo o documento PDF gerado?

 R: Para salvar o documento PDF gerado, use o`Save` método do`pdfDoc` objeto:

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