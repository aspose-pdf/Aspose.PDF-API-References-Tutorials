---
title: Buscar página de segmentos de texto en un archivo PDF
linktitle: Buscar página de segmentos de texto en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a buscar segmentos de texto en una página en un archivo PDF y recuperar sus propiedades usando Aspose.PDF para .NET.
type: docs
weight: 470
url: /es/net/programming-with-text/search-text-segments-page/
---
Este tutorial explica cómo usar Aspose.PDF para .NET para buscar segmentos de texto específicos en una página de un archivo PDF y recuperar sus propiedades. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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

## Paso 3: establezca la ruta al directorio de documentos

 Establezca la ruta a su directorio de documentos usando el`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: cargue el documento PDF

 Cargue el documento PDF usando el`Document` clase:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Reemplazar`"SearchTextSegmentsPage.pdf"` con el nombre real de su archivo PDF.

## Paso 5: crear un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda de entrada:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Reemplazar`"text"` con la frase de búsqueda deseada.

## Paso 6: acepte el absorbente para una página específica

Acepte el absorbente para la página deseada del documento:

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

Modifique el código dentro del bucle para realizar más acciones en cada segmento de texto si es necesario.

### Código fuente de muestra para la página de búsqueda de segmentos de texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Aceptar el absorbente para todas las páginas.
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Obtenga los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Recorre los fragmentos
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

¡Felicidades! Ha aprendido con éxito cómo buscar segmentos de texto específicos en una página de un documento PDF utilizando Aspose.PDF para .NET. Este tutorial proporciona una guía paso a paso, desde cargar el documento hasta acceder a los segmentos de texto extraídos. Ahora puede incorporar este código en sus propios proyectos de C# para realizar búsquedas avanzadas de segmentos de texto en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Buscar página de segmentos de texto en un archivo PDF"?

R: El tutorial "Buscar página de segmentos de texto en un archivo PDF" proporciona una guía completa sobre cómo utilizar la biblioteca Aspose.PDF para .NET para buscar segmentos de texto específicos en una página particular de un documento PDF. Cubre el proceso de configurar un proyecto, cargar un documento PDF, buscar segmentos de texto y recuperar sus propiedades usando código C#.

#### P: ¿Cómo ayuda este tutorial a buscar segmentos de texto específicos en un documento PDF?

R: Este tutorial demuestra el proceso de localizar y extraer segmentos de texto específicos en una página particular de un documento PDF. Siguiendo los pasos y los ejemplos de código proporcionados, los usuarios pueden buscar eficazmente los segmentos de texto deseados y recuperar información sobre sus propiedades.

#### P: ¿Qué requisitos previos se requieren para seguir este tutorial?

R: Antes de comenzar el tutorial, debes tener un conocimiento básico del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerlo del sitio web de Aspose o instalarlo en su proyecto usando NuGet.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Para comenzar, cree un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET. Esto le permitirá utilizar las funciones de la biblioteca para buscar y trabajar con documentos PDF.

#### P: ¿Puedo utilizar este tutorial para buscar segmentos de texto específicos en cualquier página de un PDF?

R: Sí, este tutorial proporciona instrucciones sobre cómo buscar segmentos de texto específicos en una página seleccionada de un documento PDF. Guía a los usuarios sobre cómo configurar un proyecto, cargar un PDF y utilizar la biblioteca Aspose.PDF para localizar y recuperar propiedades de los segmentos de texto deseados.

#### P: ¿Cómo especifico el texto que quiero buscar en este tutorial?

 R: Para especificar el texto que desea buscar, cree un`TextFragmentAbsorber` objeto y establezca su parámetro de búsqueda usando el`Text` propiedad. Reemplazar el valor predeterminado`"text"` en el código del tutorial con la frase de búsqueda deseada.

#### P: ¿Cómo recupero las propiedades de los segmentos de texto extraídos?

Después de aceptar el`TextFragmentAbsorber` para una página específica del PDF, puede recuperar los segmentos de texto extraídos utilizando el`TextFragments` propiedad del objeto absorbente. Esto proporciona acceso a una colección de fragmentos de texto, cada uno de los cuales contiene múltiples segmentos de texto.

#### P: ¿Puedo personalizar el código para realizar acciones adicionales en cada segmento de texto?

R: Absolutamente. El código de muestra del tutorial proporciona un bucle para recorrer los segmentos de texto recuperados. Puede personalizar el código dentro de este bucle para realizar acciones adicionales en cada segmento de texto, según los requisitos de su proyecto.

#### P: ¿Cómo guardo el documento PDF modificado después de extraer segmentos de texto?

R: Este tutorial se centra principalmente en buscar segmentos de texto y recuperar sus propiedades. Si tiene la intención de realizar modificaciones en el PDF, puede consultar otra documentación de Aspose.PDF para aprender cómo manipular y guardar el documento según sus necesidades específicas.