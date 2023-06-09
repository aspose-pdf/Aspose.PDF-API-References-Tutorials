---
title: Rotar texto usando párrafo de texto y generador
linktitle: Rotar texto usando párrafo de texto y generador
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a rotar texto usando un párrafo de texto y un generador en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 410
url: /es/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---

Este tutorial explica cómo usar Aspose.PDF para .NET para rotar texto usando constructores y párrafos de texto. El código fuente de C# proporcionado demuestra el proceso paso a paso.

## requisitos previos

Antes de continuar con el tutorial, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#.
- Aspose.PDF para la biblioteca .NET instalada. Puede obtenerlo del sitio web de Aspose o usar NuGet para instalarlo en su proyecto.

## Paso 1: configurar el proyecto

Comience por crear un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres necesarios

Agregue las siguientes directivas using al principio de su archivo C# para importar los espacios de nombres requeridos:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Paso 3: Crea el documento PDF

 Inicializar el`Document` objeto para crear un nuevo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Asegúrese de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Agrega una página

 Obtener una página particular del documento usando el`Pages.Add()` método:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Paso 5: Crear y rotar párrafos de texto

 Crear un`for` loop para generar múltiples párrafos de texto con diferentes rotaciones:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Ajuste los valores de posición y rotación según sus requisitos.

## Paso 6: Crea y configura fragmentos de texto

 Crear múltiples`TextFragment`objetos, establecer su texto y propiedades:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
```

Ajuste el texto y otras propiedades como desee.

## Paso 7: Agrega fragmentos de texto al párrafo

 Agregue los fragmentos de texto creados al párrafo usando el`AppendLine` método:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Paso 8: Cree un TextBuilder y agregue el párrafo

 Crear un`TextBuilder` objeto usando el`pdfPage` y agregue el párrafo de texto a la página PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## Paso 9: Guarde el documento PDF

 Guarde el documento PDF modificado en un archivo usando el`Save` método:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Asegúrese de reemplazar`"TextFragmentTests_Rotated4_out.pdf"` con el nombre de archivo de salida deseado.

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo rotar texto usando párrafos de texto y constructores en un documento PDF usando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde la creación del documento hasta el guardado de la versión modificada. Ahora puede incorporar este código en sus propios proyectos de C# para manipular la rotación de texto en archivos PDF.

### Ejemplo de código fuente para Rotar texto usando párrafo de texto y generador usando Aspose.PDF para .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inicializar objeto de documento
Document pdfDocument = new Document();
// Obtener página particular
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Especificar rotación
	paragraph.Rotation = i * 90 + 45;
	// Crear fragmento de texto
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Crear fragmento de texto
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Crear fragmento de texto
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Establecer propiedades de texto
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Crear fragmento de texto
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// Establecer propiedades de texto
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// Crear objeto TextBuilder
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Agregue el fragmento de texto a la página PDF
	textBuilder.AppendParagraph(paragraph);
}
// Guardar documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```