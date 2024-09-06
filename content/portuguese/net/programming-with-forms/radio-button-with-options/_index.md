---
title: Botão de rádio com opções
linktitle: Botão de rádio com opções
second_title: Referência da API do Aspose.PDF para .NET
description: Adicione facilmente um botão de opção com opções a um documento PDF usando o Aspose.PDF para .NET.
type: docs
weight: 230
url: /pt/net/programming-with-forms/radio-button-with-options/
---

Neste tutorial, mostraremos como adicionar um botão de opção com opções a um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Instanciar um objeto de documento

Instanciar um objeto Document para criar um novo documento PDF:

```csharp
Document doc = new Document();
```

## Etapa 3: Adicionar página e tabela

Adicione uma página ao documento e crie uma tabela para armazenar as opções dos botões de opção:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## Etapa 4: Instanciar um objeto RadioButtonField

Instanciar um objeto RadioButtonField para representar o botão de opção:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## Etapa 5: Adicionar opções de botão de opção

Adicione as opções do botão de opção ao objeto RadioButtonField:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## Etapa 6: personalizar opções de botão de opção

Personalize as opções dos botões de opção definindo atributos como borda, cor do texto e texto da legenda:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// Repita os mesmos passos para opt2 e opt3

```

## Etapa 7: adicione as opções de botão de opção à tabela

Adicione as opções de botão de opção à tabela para exibi-las:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## Etapa 8: Salve o documento PDF

Salve o documento PDF criado:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### Código-fonte de exemplo para botão de rádio com opções usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// Salvar o arquivo PDF
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Parabéns! Você adicionou com sucesso um botão de opção com opções a um documento PDF usando Aspose.PDF para .NET. Agora você pode usar esse método para criar formulários interativos em seus documentos PDF.