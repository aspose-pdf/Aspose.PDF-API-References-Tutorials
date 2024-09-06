---
title: Buscar expresiones regulares en un archivo PDF
linktitle: Buscar expresiones regulares en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar y recuperar texto usando expresiones regulares en archivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 440
url: /es/net/programming-with-text/search-regular-expression/
---
Este tutorial explica cómo utilizar Aspose.PDF para .NET para buscar y recuperar texto que coincida con una expresión regular en un archivo PDF. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: Buscar con expresión regular

 Crear un`TextFragmentAbsorber` objeto y establezca el patrón de expresión regular para encontrar todas las frases que coincidan con el patrón:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Como 1999-2000
```

 Reemplazar`"\\d{4}-\\d{4}"` con el patrón de expresión regular deseado.

## Paso 5: Establecer las opciones de búsqueda de texto

 Crear un`TextSearchOptions` objeto y configúrelo en el`TextSearchOptions` propiedad de la`TextFragmentAbsorber` objeto para habilitar el uso de expresiones regulares:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Paso 6: Buscar en todas las páginas

Aceptar el absorbedor para todas las páginas del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Paso 7: Recuperar fragmentos de texto extraídos

Obtenga los fragmentos de texto extraídos utilizando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Paso 8: Recorrer los fragmentos de texto

Recorra los fragmentos de texto recuperados y acceda a sus propiedades:

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

### Código fuente de muestra para búsqueda de expresiones regulares con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Cree un objeto TextAbsorber para encontrar todas las frases que coincidan con la expresión regular
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Como 1999-2000
// Establecer la opción de búsqueda de texto para especificar el uso de expresiones regulares
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

¡Felicitaciones! Aprendió a buscar y recuperar texto que coincida con una expresión regular en un documento PDF con Aspose.PDF para .NET. Este tutorial le proporcionó una guía paso a paso, desde la carga del documento hasta el acceso a los fragmentos de texto extraídos. Ahora puede incorporar este código en sus propios proyectos de C# para realizar búsquedas de texto avanzadas en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Buscar expresiones regulares en un archivo PDF"?

A: El tutorial "Buscar expresiones regulares en un archivo PDF" tiene como objetivo mostrar cómo utilizar la biblioteca Aspose.PDF para .NET para buscar y extraer texto que coincida con un patrón de expresión regular específico dentro de un archivo PDF. El tutorial proporciona una guía completa y un código C# de muestra para demostrar el proceso.

#### P: ¿Cómo ayuda este tutorial a buscar texto utilizando expresiones regulares en un documento PDF?

A: Este tutorial ofrece un método paso a paso para utilizar la biblioteca Aspose.PDF para realizar búsquedas de texto en un documento PDF según un patrón de expresión regular. Detalla cómo configurar el proyecto, cargar el documento PDF, definir un patrón de expresión regular y recuperar los fragmentos de texto coincidentes.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar este tutorial, debe tener conocimientos básicos del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerla del sitio web de Aspose o usar NuGet para integrarla en su proyecto.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Para comenzar, cree un nuevo proyecto de C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET. Esto le permitirá aprovechar las capacidades de la biblioteca dentro de su proyecto.

#### P: ¿Puedo usar expresiones regulares para buscar texto en un documento PDF?

 R: Sí, este tutorial demuestra cómo usar expresiones regulares para buscar y extraer texto de un documento PDF. Implica utilizar la función`TextFragmentAbsorber` clase y especificar un patrón de expresión regular para encontrar frases que coincidan con el patrón proporcionado.

#### P: ¿Cómo defino el patrón de expresión regular para la búsqueda de texto?

 A: Para definir un patrón de expresión regular para la búsqueda de texto, cree una`TextFragmentAbsorber` objeto y establecer su patrón utilizando el`Text` parámetro. Reemplazar el patrón predeterminado`"\\d{4}-\\d{4}"` en el código del tutorial con el patrón de expresión regular deseado.

#### P: ¿Cómo puedo habilitar el uso de expresiones regulares para la búsqueda de texto?

 A: El uso de expresiones regulares se habilita mediante la creación de una`TextSearchOptions` objeto y estableciendo su valor en`true` Asignar este objeto a la`TextSearchOptions` propiedad de la`TextFragmentAbsorber` instancia. Esto garantiza que el patrón de expresión regular se aplique durante la búsqueda de texto.

#### P: ¿Puedo recuperar fragmentos de texto que coincidan con el patrón de expresión regular?

 R: Por supuesto. Después de aplicar la búsqueda de expresión regular en el documento PDF, puede recuperar los fragmentos de texto extraídos mediante el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto. Estos fragmentos de texto contienen los segmentos de texto que coinciden con el patrón de expresión regular especificado.

#### P: ¿A qué puedo acceder de los fragmentos de texto recuperados?

A: A partir de los fragmentos de texto recuperados, puede acceder a varias propiedades, como el contenido del texto coincidente, la posición (coordenadas X e Y), la información de la fuente (nombre, tamaño, color) y más. El código de muestra dentro del bucle del tutorial demuestra cómo acceder y mostrar estas propiedades.

#### P: ¿Cómo puedo personalizar acciones en los fragmentos de texto extraídos?

R: Una vez que tenga los fragmentos de texto extraídos, puede personalizar el código dentro del bucle para realizar acciones adicionales en cada fragmento de texto. Esto puede incluir guardar el texto extraído, analizar patrones o implementar cambios de formato según sus requisitos.