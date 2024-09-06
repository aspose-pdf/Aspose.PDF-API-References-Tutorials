---
title: Buscar y obtener todo el texto
linktitle: Buscar y obtener todo el texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar y obtener texto de todas las páginas de un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 420
url: /es/net/programming-with-text/search-and-get-text-all/
---
Este tutorial explica cómo utilizar Aspose.PDF para .NET para buscar y obtener texto de todas las páginas de un documento PDF. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Buscar y extraer texto

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda ingresada:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Reemplazar`"text"` con el texto real que desea buscar.

## Paso 5: Buscar en todas las páginas

Aceptar el absorbedor para todas las páginas del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Paso 6: obtener fragmentos de texto extraídos

Obtenga los fragmentos de texto extraídos utilizando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Paso 7: Recorrer los fragmentos de texto

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

Puede modificar el código dentro del bucle para realizar más acciones en cada fragmento de texto.

### Código fuente de muestra para buscar y obtener texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda ingresada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Acepta el absorbedor para todas las páginas.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Recorrer los fragmentos
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

¡Felicitaciones! Aprendió a buscar y obtener texto de todas las páginas de un documento PDF con Aspose.PDF para .NET. Este tutorial le proporcionó una guía paso a paso, desde la carga del documento hasta el acceso a los fragmentos de texto extraídos. Ahora puede incorporar este código en sus propios proyectos de C# para analizar y procesar el contenido de texto en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Buscar y obtener todo el texto"?

A: El tutorial "Buscar y obtener todo el texto" demuestra cómo utilizar la biblioteca Aspose.PDF para .NET para buscar y extraer texto de todas las páginas de un documento PDF. El tutorial proporciona instrucciones paso a paso junto con un código C# de muestra para realizar búsquedas y recuperaciones de texto.

#### P: ¿Cómo ayuda este tutorial a extraer texto de documentos PDF?

A: Este tutorial lo guía a través del proceso de extracción de texto de todas las páginas de un documento PDF. Utiliza la biblioteca Aspose.PDF para localizar frases de texto específicas y recuperar información asociada, como la posición, las propiedades de fuente y los colores.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar este tutorial, debe tener conocimientos básicos del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerla del sitio web de Aspose o usar NuGet para integrarla en su proyecto.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Para comenzar, cree un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET. Esto le permitirá acceder a la funcionalidad de la biblioteca en su proyecto.

#### P: ¿Cómo busco texto específico dentro de un documento PDF?

 A: Puedes utilizar el`TextFragmentAbsorber`Clase para buscar instancias de una frase de búsqueda específica dentro del documento PDF. Al crear una instancia de esta clase y especificar el texto de destino, puede capturar todas las apariciones de ese texto.

#### P: ¿Puedo buscar texto en todas las páginas del documento PDF?

 R: Sí, el tutorial demuestra cómo buscar texto en todas las páginas del documento PDF.`pdfDocument.Pages.Accept(textFragmentAbsorber)` Se utiliza este método para aceptar el absorbedor para todas las páginas, lo que le permite buscar el texto deseado en cada página.

#### P: ¿Cómo puedo acceder a los fragmentos de texto extraídos?

 A: Después de buscar el texto, puede acceder a los fragmentos de texto extraídos utilizando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto. Esta propiedad proporciona acceso a una colección de`TextFragment` objetos que contienen el texto extraído y la información relacionada.

#### P: ¿Qué información puedo recuperar de los fragmentos de texto extraídos?

A: Puede recuperar diversos detalles de los fragmentos de texto extraídos, como el contenido real del texto, la posición (coordenadas X e Y), información de la fuente (nombre, tamaño, color, etc.) y más. El código de muestra del tutorial demuestra cómo acceder a estos detalles e imprimirlos.

#### P: ¿Puedo realizar más acciones en los fragmentos de texto extraídos?

R: Por supuesto. Una vez que tenga los fragmentos de texto extraídos, puede modificar el código dentro del bucle para realizar acciones personalizadas en cada fragmento. Esto podría incluir guardar el texto extraído, analizar patrones de texto o aplicar cambios de formato.