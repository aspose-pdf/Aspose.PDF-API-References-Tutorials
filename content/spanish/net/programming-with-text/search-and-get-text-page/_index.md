---
title: Buscar y obtener página de texto en un archivo PDF
linktitle: Buscar y obtener página de texto en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a buscar y obtener texto de una página específica en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 430
url: /es/net/programming-with-text/search-and-get-text-page/
---
Este tutorial explica cómo usar Aspose.PDF para .NET para buscar y obtener texto de una página específica en un archivo PDF. El código fuente de C# proporcionado demuestra el proceso paso a paso.

## Requisitos previos

Antes de continuar con el tutorial, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#.
- Aspose.PDF para la biblioteca .NET instalada. Puede obtenerlo del sitio web de Aspose o utilizar NuGet para instalarlo en su proyecto.

## Paso 1: configurar el proyecto

Comience creando un nuevo proyecto C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios

Agregue las siguientes directivas de uso al principio de su archivo C# para importar los espacios de nombres requeridos:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: cargue el documento PDF

 Establezca la ruta a su directorio de documentos PDF y cargue el documento usando el`Document` clase:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Asegúrate de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: buscar y extraer texto de una página

 Crear un`TextFragmentAbsorber`objeto para encontrar todas las instancias de la frase de búsqueda de entrada en una página específica:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Reemplazar`"Figure"` con el texto real que desea buscar.

## Paso 5: buscar en una página específica

Acepte el absorbente para una página específica del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Paso 6: obtenga fragmentos de texto extraídos

Obtenga los fragmentos de texto extraídos utilizando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Paso 7: recorra los fragmentos y segmentos de texto

Recorra los fragmentos de texto obtenidos y sus segmentos, y acceda a sus propiedades:

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

### Código fuente de muestra para la página Buscar y obtener texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Aceptar el absorbente para todas las páginas.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenga los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Recorre los fragmentos
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

¡Felicidades! Ha aprendido con éxito cómo buscar y obtener texto de una página específica de un documento PDF utilizando Aspose.PDF para .NET. Este tutorial proporciona una guía paso a paso, desde cargar el documento hasta acceder a los segmentos de texto extraídos. Ya puedes incorporar

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Buscar y obtener página de texto"?

R: El tutorial "Buscar y obtener página de texto" está diseñado para ilustrar cómo utilizar la biblioteca Aspose.PDF para .NET para buscar y recuperar texto de una página específica dentro de un archivo PDF. El tutorial proporciona instrucciones detalladas y código C# de muestra para demostrar el proceso.

#### P: ¿Cómo ayuda este tutorial a extraer texto de una página específica en un documento PDF?

R: Este tutorial lo guía a través del proceso de extracción de texto de una página particular de un documento PDF utilizando la biblioteca Aspose.PDF. Describe los pasos necesarios y proporciona código C# para buscar una frase de texto específica en la página seleccionada y recuperar segmentos de texto asociados.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar este tutorial, debes tener un conocimiento básico del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerlo del sitio web de Aspose o utilizar NuGet para integrarlo en su proyecto.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Para comenzar, cree un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET. Esto le permitirá utilizar las capacidades de la biblioteca en su proyecto.

#### P: ¿Puedo buscar texto en una página específica del documento PDF?

R: Sí, este tutorial muestra cómo buscar texto en una página específica de un documento PDF. Implica utilizar el`TextFragmentAbsorber` clase para localizar instancias de una frase de texto particular en la página elegida.

#### P: ¿Cómo accedo a los segmentos de texto extraídos de una página específica?

 R: Después de buscar el texto en la página designada, puede acceder a los segmentos de texto extraídos usando el`TextSegments` propiedad de la`TextFragment` objeto. Esta propiedad proporciona acceso a una colección de`TextSegment` objetos que contienen el texto extraído e información relacionada.

#### P: ¿Qué información puedo recuperar de los segmentos de texto extraídos?

R: Puede recuperar varios detalles de los segmentos de texto extraídos, incluido el contenido del texto, la posición (coordenadas X e Y), información de fuente (nombre, tamaño, color, etc.) y más. El código de muestra del tutorial demuestra cómo acceder e imprimir estos detalles para cada segmento de texto.

#### P: ¿Puedo realizar acciones personalizadas en los segmentos de texto extraídos?

R: Ciertamente. Una vez que tenga los segmentos de texto extraídos, puede personalizar el código dentro del bucle para realizar acciones adicionales en cada segmento. Esto podría incluir guardar el texto extraído, analizar patrones de texto o aplicar cambios de formato.