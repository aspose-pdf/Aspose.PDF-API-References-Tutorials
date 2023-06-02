---
title: Crear documento
linktitle: Crear documento
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente un documento con botones de radio usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-forms/create-doc/
---

En este tutorial, le mostraremos cómo crear un documento con botones de opción usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

##Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Crear un nuevo documento

Cree un nuevo objeto Documento para contener el documento PDF:

```csharp
Document doc = new Document();
```

## Paso 3: Agrega una página

Agregar una nueva página al documento:

```csharp
Page page = doc.Pages.Add();
```

## Paso 4: agregue un campo de botón de opción

Cree un campo de botón de radio y establezca su posición y tamaño:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Paso 5: Agregar opciones de botón de opción

Agregue las opciones deseadas al campo del botón de opción. Puede establecer las coordenadas y el tamaño de cada opción según sea necesario:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Paso 6: agregue el campo de botón de opción al formulario

Agregue el campo de botón de opción a la colección de campos de formulario de documento:

```csharp
doc.Form.Add(field);
```

## Paso 7: Guarde el documento

Guarde el documento PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para Create Doc usando Aspose.Words para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crear un nuevo documento
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Agregar campo de botón de radio
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Agregar opciones de botón de radio. tenga en cuenta que estas opciones se encuentran
	// Ni en horizontal ni en vertical.
	// Puede intentar establecer cualquier coordenada (e incluso tamaño) para ellos.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Guardar el documento PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos cómo crear un documento con botones de radio usando Aspose.PDF para .NET. Siguiendo estos pasos, puede agregar fácilmente botones de opción a sus documentos PDF usando Aspose.PDF.