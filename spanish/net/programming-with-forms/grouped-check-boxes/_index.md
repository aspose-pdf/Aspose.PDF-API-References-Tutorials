---
title: Casillas de verificación agrupadas
linktitle: Casillas de verificación agrupadas
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente casillas de verificación agrupadas en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 170
url: /es/net/programming-with-forms/grouped-check-boxes/
---

En este tutorial, le mostraremos cómo crear casillas de verificación agrupadas en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear una instancia de un objeto de documento

Crea una instancia de un objeto Documento:

```csharp
Document pdfDocument = new Document();
```

## Paso 3: Agregar página al documento PDF

Agregue una página al documento PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Paso 4: crear una instancia de un objeto RadioButtonField

Cree una instancia de un objeto RadioButtonField con el número de página como argumento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Paso 5: Agregar opciones de botón de radio

Agregue opciones de botones de radio usando el objeto RadioButtonOptionField y especifique su posición usando el objeto Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Paso 6: personaliza las opciones de los botones de opción

Personalice las opciones de los botones de opción configurando su estilo, borde y apariencia:

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

## Paso 7: agregue los botones de radio al formulario

Agregue los botones de radio al objeto de formulario de documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Paso 8: Guarde el documento

Guarde el documento PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para casillas de verificación agrupadas usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instanciar objeto de documento
	Document pdfDocument = new Document();
	// Agregar una página a un archivo PDF
	Page page = pdfDocument.Pages.Add();
	// Instate el objeto RadioButtonField con el número de página como argumento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Agregue la primera opción de botón de opción y también especifique su origen usando el objeto Rectangle
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
	// Agregar botón de opción para formar objeto de objeto Documento
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Guardar el documento PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos a crear casillas de verificación agrupadas en un documento PDF usando Aspose.PDF para .NET. Siguiendo estos pasos, puede agregar fácilmente opciones de botones de opción personalizados y agruparlos en sus documentos PDF usando Aspose.PDF.