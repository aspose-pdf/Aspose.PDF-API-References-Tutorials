---
title: Casillas de verificación agrupadas en un documento PDF
linktitle: Casillas de verificación agrupadas en un documento PDF
second_title: Aspose.PDF para referencia de API .NET
description: Cree fácilmente casillas de verificación agrupadas en un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 170
url: /es/net/programming-with-forms/grouped-check-boxes/
---
En este tutorial, le mostraremos cómo crear casillas de verificación agrupadas en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: preparación

Asegúrese de haber importado las bibliotecas necesarias y establecer la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear una instancia de un objeto de documento

Crear una instancia de un objeto de documento:

```csharp
Document pdfDocument = new Document();
```

## Paso 3: agregar página al documento PDF

Agregue una página al documento PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Paso 4: crear una instancia de un objeto RadioButtonField

Cree una instancia de un objeto RadioButtonField con el número de página como argumento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Paso 5: agregue opciones de botón de opción

Agregue opciones de botón de opción usando el objeto RadioButtonOptionField y especifique su posición usando el objeto Rectángulo:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Paso 6: personaliza las opciones del botón de opción

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

## Paso 7: agregue los botones de opción al formulario

Agregue los botones de opción al objeto de formulario de documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Paso 8: guarde el documento

Guarde el documento PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Código fuente de muestra para casillas de verificación agrupadas usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crear una instancia del objeto Documento
	Document pdfDocument = new Document();
	// Agregar una página al archivo PDF
	Page page = pdfDocument.Pages.Add();
	// Instalar el objeto RadioButtonField con el número de página como argumento
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
	// Agregar botón de opción para formar el objeto del objeto Documento
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Guarde el documento PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos cómo crear casillas de verificación agrupadas en un documento PDF usando Aspose.PDF para .NET. Si sigue estos pasos, puede agregar fácilmente opciones de botones de opción personalizados y agruparlas en sus documentos PDF usando Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Qué son las casillas de verificación agrupadas en un documento PDF?

R: Las casillas de verificación agrupadas en un documento PDF se refieren a un conjunto de opciones de botones de opción que están agrupadas. Los botones de opción permiten a los usuarios seleccionar solo una opción de un grupo de opciones mutuamente excluyentes. Cuando se selecciona un botón de opción, los demás en el mismo grupo se deseleccionan automáticamente. Este comportamiento de agrupación es útil cuando desea presentar a los usuarios múltiples opciones pero limitar su selección a una sola opción.

#### P: ¿Puedo personalizar la apariencia de las casillas de verificación agrupadas en Aspose.PDF para .NET?

R: Sí, puede personalizar la apariencia de las casillas de verificación agrupadas en Aspose.PDF para .NET. La API proporciona varias opciones para configurar el estilo, el borde y la apariencia de las opciones de los botones de opción. Puede definir la posición de cada opción, elegir entre diferentes estilos de cuadro (por ejemplo, cuadrado, círculo, cruz) y ajustar las propiedades del borde para lograr la representación visual deseada.

#### P: ¿Cómo agrego casillas de verificación agrupadas a una página específica en un documento PDF?

R: Para agregar casillas de verificación agrupadas a una página específica en un documento PDF, necesita crear una instancia de una`RadioButtonField` objeto con el número de página deseado como argumento. Luego, crea`RadioButtonOptionField` objetos que representan cada opción de botón de opción y especificar su posición usando el`Rectangle` objeto. Finalmente, agregue estas opciones al`RadioButtonField` y personalizar su apariencia según sea necesario antes de agregar el`RadioButtonField` al formulario del documento.

#### P: ¿Puedo agregar varios grupos de casillas de verificación a un solo documento PDF?

 R: Sí, puedes agregar varios grupos de casillas de verificación a un solo documento PDF. Cada grupo debe tener un único`RadioButtonField` objeto, y el`RadioButtonOptionField` Los objetos dentro de cada grupo deben compartir la misma página y nombres únicos para sus opciones. Esto garantiza que los botones de opción dentro de cada grupo funcionen correctamente y que las selecciones sean mutuamente excluyentes.

#### P: ¿Se admiten casillas de verificación agrupadas en todos los visores y aplicaciones de PDF?

R: Sí, las casillas de verificación agrupadas son compatibles con todos los visores y aplicaciones de PDF compatibles con los estándares. La especificación PDF define los botones de opción y su comportamiento de agrupación, haciéndolos universalmente reconocidos en el formato PDF. Sin embargo, es esencial probar la funcionalidad en diferentes visores de PDF para garantizar un comportamiento coherente en las distintas plataformas.