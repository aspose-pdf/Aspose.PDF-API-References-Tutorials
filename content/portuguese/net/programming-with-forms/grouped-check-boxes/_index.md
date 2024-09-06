---
title: Caixas de seleção agrupadas em documento PDF
linktitle: Caixas de seleção agrupadas em documento PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Crie facilmente caixas de seleção agrupadas em documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 170
url: /pt/net/programming-with-forms/grouped-check-boxes/
---
Neste tutorial, mostraremos como criar caixas de seleção agrupadas em um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Instanciar um objeto de documento

Instanciar um objeto Document:

```csharp
Document pdfDocument = new Document();
```

## Etapa 3: Adicionar página ao documento PDF

Adicione uma página ao documento PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Etapa 4: Instanciar um objeto RadioButtonField

Instanciar um objeto RadioButtonField com o número da página como argumento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Etapa 5: Adicionar opções de botão de opção

Adicione opções de botões de opção usando o objeto RadioButtonOptionField e especifique sua posição usando o objeto Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Etapa 6: personalizar opções de botão de opção

Personalize as opções dos botões de opção definindo seu estilo, borda e aparência:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Etapa 7: adicione os botões de opção ao formulário

Adicione os botões de opção ao objeto de formulário do documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Etapa 8: Salve o documento

Salve o documento PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Código-fonte de exemplo para caixas de seleção agrupadas usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instanciar objeto Document
	Document pdfDocument = new Document();
	// Adicionar uma página ao arquivo PDF
	Page page = pdfDocument.Pages.Add();
	// Instanciar objeto RadioButtonField com número de página como argumento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Adicione a primeira opção de botão de opção e também especifique sua origem usando o objeto Rectangle
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Adicionar botão de opção ao objeto de formulário do objeto Documento
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Salvar o documento PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Neste tutorial, aprendemos como criar caixas de seleção agrupadas em um documento PDF usando Aspose.PDF para .NET. Seguindo essas etapas, você pode facilmente adicionar opções de botões de rádio personalizados e agrupá-los em seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: O que são caixas de seleção agrupadas em um documento PDF?

R: Caixas de seleção agrupadas em um documento PDF referem-se a um conjunto de opções de botões de opção que são agrupadas. Os botões de opção permitem que os usuários selecionem apenas uma opção de um grupo de escolhas mutuamente exclusivas. Quando um botão de opção é selecionado, os outros no mesmo grupo são automaticamente desmarcados. Esse comportamento de agrupamento é útil quando você deseja apresentar aos usuários várias opções, mas limitar a seleção deles a apenas uma escolha.

#### P: Posso personalizar a aparência de caixas de seleção agrupadas no Aspose.PDF para .NET?

R: Sim, você pode personalizar a aparência de caixas de seleção agrupadas no Aspose.PDF para .NET. A API fornece várias opções para definir o estilo, a borda e a aparência das opções de botões de opção. Você pode definir a posição de cada opção, escolher entre diferentes estilos de caixa (por exemplo, quadrado, círculo, cruz) e ajustar as propriedades da borda para obter a representação visual desejada.

#### P: Como adiciono caixas de seleção agrupadas a uma página específica em um documento PDF?

R: Para adicionar caixas de seleção agrupadas a uma página específica em um documento PDF, você precisa instanciar uma`RadioButtonField` objeto com o número da página desejada como argumento. Em seguida, crie`RadioButtonOptionField` objetos que representam cada opção de botão de rádio e especificam sua posição usando o`Rectangle` objeto. Por fim, adicione essas opções ao`RadioButtonField` e personalizar sua aparência conforme necessário antes de adicionar o`RadioButtonField` para o formulário do documento.

#### P: Posso adicionar vários grupos de caixas de seleção a um único documento PDF?

 R: Sim, você pode adicionar vários grupos de caixas de seleção a um único documento PDF. Cada grupo deve ter um`RadioButtonField` objeto, e o`RadioButtonOptionField` objetos dentro de cada grupo devem compartilhar a mesma página e nomes exclusivos para suas opções. Isso garante que os botões de opção dentro de cada grupo funcionem corretamente, e as seleções sejam mutuamente exclusivas.

#### P: Caixas de seleção agrupadas são suportadas em todos os aplicativos e visualizadores de PDF?

R: Sim, caixas de seleção agrupadas são suportadas em todos os visualizadores e aplicativos de PDF compatíveis com o padrão. A especificação PDF define botões de opção e seu comportamento de agrupamento, tornando-os universalmente reconhecidos no formato PDF. No entanto, é essencial testar a funcionalidade em diferentes visualizadores de PDF para garantir um comportamento consistente em várias plataformas.