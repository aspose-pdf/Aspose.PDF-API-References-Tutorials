---
title: Buscar texto y dibujar rectángulo
linktitle: Buscar texto y dibujar rectángulo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar texto en un PDF, dibuje rectángulos alrededor del texto encontrado y guarde el documento modificado usando Aspose.PDF para .NET.
type: docs
weight: 460
url: /es/net/programming-with-text/search-text-and-draw-rectangle/
---

Este tutorial explica cómo usar Aspose.PDF para .NET para buscar texto específico en un documento PDF, dibujar un rectángulo alrededor del texto encontrado y guardar el documento modificado. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Paso 3: establezca la ruta al directorio del documento

 Establezca la ruta a su directorio de documentos usando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Cargue el documento PDF

 Cargue el documento PDF usando el`Document` clase:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Reemplazar`"SearchAndGetTextFromAll.pdf"` con el nombre real de su archivo PDF.

## Paso 5: Crea un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda de entrada:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Reemplazar`@"[\S]+"` con el patrón de expresión regular deseado.

## Paso 6: habilite la búsqueda de expresiones regulares

Habilite la búsqueda de expresiones regulares configurando el`TextSearchOptions` propiedad del absorbente:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Paso 7: Buscar en todas las páginas

Acepte el absorbedor para todas las páginas del documento:

```csharp
document.Pages.Accept(textAbsorber);
```

## Paso 8: Dibuja un rectángulo alrededor del texto encontrado

 Crear un`PdfContentEditor` objeto y recorra los fragmentos de texto recuperados, dibujando un rectángulo alrededor de cada segmento de texto:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Paso 9: Guarde el documento modificado

Guarde el documento modificado:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Asegúrese de reemplazar`"SearchTextAndDrawRectangle_out.pdf"` con el nombre de archivo de salida deseado.

### Ejemplo de código fuente para buscar texto y dibujar rectángulo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Cree un objeto TextAbsorber para encontrar todas las frases que coincidan con la expresión regular
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo buscar texto específico en un documento PDF, dibujar un rectángulo alrededor del texto encontrado y guardar el documento modificado usando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde la configuración del proyecto hasta la realización de las acciones requeridas. Ahora puede incorporar este código en sus propios proyectos de C# para manipular texto y dibujar rectángulos en archivos PDF.