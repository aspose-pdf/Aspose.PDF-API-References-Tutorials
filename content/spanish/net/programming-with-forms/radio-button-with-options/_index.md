---
title: Botón de opción con opciones
linktitle: Botón de opción con opciones
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente un botón de opción con opciones a un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 230
url: /es/net/programming-with-forms/radio-button-with-options/
---

En este tutorial, le mostraremos cómo agregar un botón de opción con opciones a un documento PDF mediante Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y de haber configurado la ruta al directorio de sus documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear una instancia de un objeto de documento

Cree una instancia de un objeto Documento para crear un nuevo documento PDF:

```csharp
Document doc = new Document();
```

## Paso 3: Agregar página y tabla

Agregue una página al documento y cree una tabla para contener las opciones del botón de opción:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## Paso 4: Crear una instancia de un objeto RadioButtonField

Cree una instancia de un objeto RadioButtonField para representar el botón de opción:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## Paso 5: Agregar opciones de botón de opción

Agregue las opciones del botón de opción al objeto RadioButtonField:

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

## Paso 6: Personaliza las opciones del botón de opción

Personalice las opciones del botón de opción configurando atributos como el borde, el color del texto y el texto del título:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// Repita los mismos pasos para opt2 y opt3

```

## Paso 7: Agrega las opciones del botón de opción a la tabla

Agregue las opciones del botón de opción a la tabla para mostrarlas:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## Paso 8: Guarde el documento PDF

Guardar el documento PDF creado:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para botón de opción con opciones utilizando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
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
	// Guardar el archivo PDF
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

¡Felicitaciones! Ha agregado exitosamente un botón de opción con opciones a un documento PDF usando Aspose.PDF para .NET. Ahora puede usar este método para crear formularios interactivos en sus documentos PDF.