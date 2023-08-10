---
title: Buscar y obtener texto todo
linktitle: Buscar y obtener texto todo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar y obtener texto de todas las páginas de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 420
url: /es/net/programming-with-text/search-and-get-text-all/
---

Este tutorial explica cómo usar Aspose.PDF para .NET para buscar y obtener texto de todas las páginas de un documento PDF. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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

## Paso 3: Cargue el documento PDF

 Establezca la ruta a su directorio de documentos PDF y cargue el documento usando el`Document` clase:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Buscar y extraer texto

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda de entrada:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Reemplazar`"text"` con el texto real que desea buscar.

## Paso 5: Buscar en todas las páginas

Acepte el absorbedor para todas las páginas del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Paso 6: obtener fragmentos de texto extraídos

Obtenga los fragmentos de texto extraídos usando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Paso 7: recorrer los fragmentos de texto

Recorra los fragmentos de texto getd y acceda a sus propiedades:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Puede modificar el código dentro del ciclo para realizar más acciones en cada fragmento de texto.

### Ejemplo de código fuente para buscar y obtener texto todo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Aceptar el absorbedor para todas las páginas.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Bucle a través de los fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo buscar y obtener texto de todas las páginas de un documento PDF utilizando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde cargar el documento hasta acceder a los fragmentos de texto extraídos. Ahora puede incorporar este código en sus propios proyectos de C# para analizar y procesar contenido de texto en archivos PDF.