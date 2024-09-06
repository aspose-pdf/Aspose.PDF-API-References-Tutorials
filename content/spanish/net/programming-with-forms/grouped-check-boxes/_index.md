---
title: Casillas de verificación agrupadas en un documento PDF
linktitle: Casillas de verificación agrupadas en un documento PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente casillas de verificación agrupadas en documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 170
url: /es/net/programming-with-forms/grouped-check-boxes/
---
En este tutorial, le mostraremos cómo crear casillas de verificación agrupadas en un documento PDF con Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y de haber configurado la ruta al directorio de sus documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear una instancia de un objeto de documento

Crear una instancia de un objeto Documento:

```csharp
Document pdfDocument = new Document();
```

## Paso 3: Agregar página al documento PDF

Agregar una página al documento PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Paso 4: Crear una instancia de un objeto RadioButtonField

Cree una instancia de un objeto RadioButtonField con el número de página como argumento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Paso 5: Agregar opciones de botón de opción

Agregue opciones de botón de opción utilizando el objeto RadioButtonOptionField y especifique su posición utilizando el objeto Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Paso 6: Personaliza las opciones del botón de opción

Personalice las opciones del botón de opción configurando su estilo, borde y apariencia:

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

## Paso 7: Agrega los botones de opción al formulario

Agregue los botones de opción al objeto de formulario del documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Paso 8: Guardar el documento

Guardar el documento PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Código fuente de muestra para casillas de verificación agrupadas utilizando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crear una instancia del objeto Documento
	Document pdfDocument = new Document();
	// Agregar una página a un archivo PDF
	Page page = pdfDocument.Pages.Add();
	// Crear un objeto RadioButtonField con el número de página como argumento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Agregue la primera opción de botón de opción y también especifique su origen usando el objeto Rectángulo
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
	// Agregar botón de opción al objeto de formulario del objeto Documento
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

En este tutorial, aprendimos a crear casillas de verificación agrupadas en un documento PDF con Aspose.PDF para .NET. Si sigue estos pasos, podrá agregar fácilmente opciones de botones de opción personalizados y agruparlos en sus documentos PDF con Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Qué son las casillas de verificación agrupadas en un documento PDF?

R: Las casillas de verificación agrupadas en un documento PDF hacen referencia a un conjunto de opciones de botones de opción que están agrupadas. Los botones de opción permiten a los usuarios seleccionar solo una opción de un grupo de opciones mutuamente excluyentes. Cuando se selecciona un botón de opción, los demás del mismo grupo se deseleccionan automáticamente. Este comportamiento de agrupación es útil cuando desea presentarles a los usuarios varias opciones, pero limitar su selección a una sola opción.

#### P: ¿Puedo personalizar la apariencia de las casillas de verificación agrupadas en Aspose.PDF para .NET?

R: Sí, puede personalizar la apariencia de las casillas de verificación agrupadas en Aspose.PDF para .NET. La API proporciona varias opciones para configurar el estilo, el borde y la apariencia de las opciones de los botones de opción. Puede definir la posición de cada opción, elegir entre diferentes estilos de casilla (por ejemplo, cuadrado, círculo, cruz) y ajustar las propiedades del borde para lograr la representación visual deseada.

#### P: ¿Cómo puedo agregar casillas de verificación agrupadas a una página específica en un documento PDF?

A: Para agregar casillas de verificación agrupadas a una página específica en un documento PDF, debe crear una instancia`RadioButtonField` objeto con el número de página deseado como argumento. Luego, cree`RadioButtonOptionField` objetos que representan cada opción del botón de opción y especifican su posición utilizando el`Rectangle` objeto. Por último, agregue estas opciones a la`RadioButtonField` y personalizar su apariencia según sea necesario antes de agregar el`RadioButtonField` al formato del documento.

#### P: ¿Puedo agregar varios grupos de casillas de verificación a un solo documento PDF?

 R: Sí, puede agregar varios grupos de casillas de verificación a un solo documento PDF. Cada grupo debe tener una casilla de verificación única.`RadioButtonField` objeto, y el`RadioButtonOptionField` Los objetos de cada grupo deben compartir la misma página y nombres únicos para sus opciones. Esto garantiza que los botones de opción de cada grupo funcionen correctamente y que las selecciones sean mutuamente excluyentes.

#### P: ¿Las casillas de verificación agrupadas son compatibles con todos los visores y aplicaciones de PDF?

R: Sí, las casillas de verificación agrupadas son compatibles con todos los visores y aplicaciones de PDF que cumplen con los estándares. La especificación PDF define los botones de opción y su comportamiento de agrupación, lo que hace que sean universalmente reconocidos en el formato PDF. Sin embargo, es esencial probar la funcionalidad en diferentes visores de PDF para garantizar un comportamiento consistente en varias plataformas.