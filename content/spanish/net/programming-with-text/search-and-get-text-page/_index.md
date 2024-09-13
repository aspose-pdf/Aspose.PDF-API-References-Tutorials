---
title: Buscar y obtener página de texto en archivo PDF
linktitle: Buscar y obtener página de texto en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar y obtener texto de una página específica en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 430
url: /es/net/programming-with-text/search-and-get-text-page/
---
Este tutorial explica cómo utilizar Aspose.PDF para .NET para buscar y obtener texto de una página específica en un archivo PDF. El código fuente de C# proporcionado demuestra el proceso paso a paso.

## Prerrequisitos

Antes de continuar con el tutorial, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada. Puede obtenerla desde el sitio web de Aspose o usar NuGet para instalarla en su proyecto.

## Paso 1: Configurar el proyecto

Comience creando un nuevo proyecto C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios

Agregue las siguientes directivas using al comienzo de su archivo C# para importar los espacios de nombres requeridos:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: Cargue el documento PDF

 Establezca la ruta al directorio de su documento PDF y cargue el documento utilizando el`Document` clase:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Buscar y extraer texto de una página

 Crear un`TextFragmentAbsorber`objeto para encontrar todas las instancias de la frase de búsqueda ingresada en una página específica:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Reemplazar`"Figure"` con el texto real que desea buscar.

## Paso 5: Buscar en una página específica

Aceptar el absorbedor para una página específica del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Paso 6: obtener fragmentos de texto extraídos

 Obtenga los fragmentos de texto extraídos utilizando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Paso 7: Recorrer los fragmentos y segmentos de texto

Recorra los fragmentos de texto getd y sus segmentos y acceda a sus propiedades:

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

Puede modificar el código dentro del bucle para realizar más acciones en cada segmento de texto.

### Código fuente de muestra para la página de búsqueda y obtención de texto con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda ingresada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Acepta el absorbedor para todas las páginas.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Recorrer los fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusión

¡Felicitaciones! Aprendió con éxito cómo buscar y obtener texto de una página específica de un documento PDF utilizando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde la carga del documento hasta el acceso a los segmentos de texto extraídos. Ahora puede incorporar

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Página de búsqueda y obtención de texto"?

R: El tutorial "Buscar y obtener página de texto" está diseñado para ilustrar cómo utilizar la biblioteca Aspose.PDF para .NET para buscar y recuperar texto de una página específica dentro de un archivo PDF. El tutorial proporciona instrucciones detalladas y código C# de muestra para demostrar el proceso.

#### P: ¿Cómo ayuda este tutorial a extraer texto de una página específica en un documento PDF?

A: Este tutorial lo guía a través del proceso de extracción de texto de una página particular de un documento PDF mediante la biblioteca Aspose.PDF. Describe los pasos necesarios y proporciona código C# para buscar una frase de texto específica en la página seleccionada y recuperar segmentos de texto asociados.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar este tutorial, debe tener conocimientos básicos del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerla del sitio web de Aspose o usar NuGet para integrarla en su proyecto.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Para comenzar, cree un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET. Esto le permitirá utilizar las capacidades de la biblioteca en su proyecto.

#### P: ¿Puedo buscar texto en una página específica del documento PDF?

R: Sí, este tutorial demuestra cómo buscar texto en una página específica de un documento PDF. Implica el uso de la función`TextFragmentAbsorber` clase para localizar instancias de una frase de texto particular en la página elegida.

#### P: ¿Cómo puedo acceder a los segmentos de texto extraídos de la página específica?

 A: Después de buscar el texto en la página designada, puede acceder a los segmentos de texto extraídos utilizando el`TextSegments` propiedad de la`TextFragment` objeto. Esta propiedad proporciona acceso a una colección de`TextSegment` objetos que contienen el texto extraído y la información relacionada.

#### P: ¿Qué información puedo recuperar de los segmentos de texto extraídos?

A: Puede recuperar diversos detalles de los segmentos de texto extraídos, incluido el contenido del texto, la posición (coordenadas X e Y), la información de la fuente (nombre, tamaño, color, etc.) y más. El código de muestra del tutorial demuestra cómo acceder e imprimir estos detalles para cada segmento de texto.

#### P: ¿Puedo realizar acciones personalizadas en los segmentos de texto extraídos?

R: Por supuesto. Una vez que haya extraído los segmentos de texto, puede personalizar el código dentro del bucle para realizar acciones adicionales en cada segmento. Esto podría incluir guardar el texto extraído, analizar patrones de texto o aplicar cambios de formato.