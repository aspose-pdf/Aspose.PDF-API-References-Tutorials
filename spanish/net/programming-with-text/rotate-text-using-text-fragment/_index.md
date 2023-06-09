---
title: Rotar texto usando fragmento de texto
linktitle: Rotar texto usando fragmento de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a rotar texto usando fragmentos de texto en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 390
url: /es/net/programming-with-text/rotate-text-using-text-fragment/
---

Este tutorial explica cómo usar Aspose.PDF para .NET para rotar texto usando fragmentos de texto. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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

## Paso 5: crea fragmentos de texto

 Crear múltiples`TextFragment` objetos, establecer su texto y propiedades, y especificar sus posiciones en la página:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Ajuste el texto, las posiciones y otras propiedades como desee.

## Paso 6: crea un TextBuilder y agrega fragmentos de texto

 Crear un`TextBuilder` objeto usando el`pdfPage` y agregue los fragmentos de texto a la página PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Paso 7: Guarde el documento PDF

 Guarde el documento PDF modificado en un archivo usando el`Save` método:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Asegúrese de reemplazar`"TextFragmentTests_Rotated1_out.pdf"` con el nombre de archivo de salida deseado.

### Ejemplo de código fuente para Rotar texto usando Fragmento de texto usando Aspose.PDF para .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inicializar objeto de documento
Document pdfDocument = new Document();
// Obtener página particular
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crear fragmento de texto
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Establecer propiedades de texto
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Crear fragmento de texto rotado
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Establecer propiedades de texto
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Crear fragmento de texto rotado
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Establecer propiedades de texto
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// crear objeto TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Agregue el fragmento de texto a la página PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Guardar documento
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo rotar texto usando fragmentos de texto en un documento PDF usando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde la creación del documento hasta el guardado de la versión modificada. Ahora puede incorporar este código en sus propios proyectos de C# para manipular la rotación de texto en archivos PDF.