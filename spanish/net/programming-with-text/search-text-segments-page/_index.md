---
title: Página de búsqueda de segmentos de texto
linktitle: Página de búsqueda de segmentos de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar segmentos de texto en una página de un documento PDF y recupere sus propiedades con Aspose.PDF para .NET.
type: docs
weight: 470
url: /es/net/programming-with-text/search-text-segments-page/
---

Este tutorial explica cómo usar Aspose.PDF para .NET para buscar segmentos de texto específicos en una página de un documento PDF y recuperar sus propiedades. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Reemplazar`"SearchTextSegmentsPage.pdf"` con el nombre real de su archivo PDF.

## Paso 5: Crea un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda de entrada:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Reemplazar`"text"` con la frase de búsqueda deseada.

## Paso 6: Aceptar el absorbedor para una página específica

Acepte el absorbedor para la página deseada del documento:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Reemplazar`2` con el número de página deseado (índice basado en 1).

## Paso 7: recuperar los segmentos de texto extraídos

 Obtenga los segmentos de texto extraídos usando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Paso 8: recorrer los segmentos de texto

Recorra los segmentos de texto recuperados y acceda a sus propiedades:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Modifique el código dentro del ciclo para realizar más acciones en cada segmento de texto si es necesario.

### Ejemplo de código fuente para la página de segmentos de texto de búsqueda usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Aceptar el absorbedor para todas las páginas.
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Bucle a través de los fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo buscar segmentos de texto específicos en una página de un documento PDF utilizando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde cargar el documento hasta acceder a los segmentos de texto extraídos. Ahora puede incorporar este código en sus propios proyectos de C# para realizar búsquedas avanzadas de segmentos de texto en archivos PDF.