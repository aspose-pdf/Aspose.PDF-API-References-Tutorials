---
title: Buscar expresiones regulares en archivos PDF
linktitle: Buscar expresiones regulares en archivos PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a buscar y recuperar texto usando expresiones regulares en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 440
url: /es/net/programming-with-text/search-regular-expression/
---
Este tutorial explica cómo usar Aspose.PDF para .NET para buscar y recuperar texto que coincida con una expresión regular en un archivo PDF. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Asegúrate de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 4: buscar con expresión regular

 Crear un`TextFragmentAbsorber` objeto y establezca el patrón de expresión regular para encontrar todas las frases que coincidan con el patrón:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Como 1999-2000
```

 Reemplazar`"\\d{4}-\\d{4}"` con el patrón de expresión regular que desee.

## Paso 5: configurar las opciones de búsqueda de texto

 Crear un`TextSearchOptions` objeto y configúrelo en el`TextSearchOptions` propiedad de la`TextFragmentAbsorber` objeto para habilitar el uso de expresiones regulares:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Paso 6: buscar en todas las páginas

Acepta el absorbente para todas las páginas del documento:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Paso 7: recuperar fragmentos de texto extraídos

Obtenga los fragmentos de texto extraídos utilizando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Paso 8: recorrer los fragmentos de texto

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

### Código fuente de muestra para buscar expresiones regulares usando Aspose.PDF para .NET 
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
// Aceptar el absorbente para todas las páginas.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenga los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Recorre los fragmentos
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

¡Felicidades! Ha aprendido con éxito cómo buscar y recuperar texto que coincida con una expresión regular en un documento PDF utilizando Aspose.PDF para .NET. Este tutorial proporciona una guía paso a paso, desde cargar el documento hasta acceder a los fragmentos de texto extraídos. Ahora puede incorporar este código en sus propios proyectos de C# para realizar búsquedas de texto avanzadas en archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Buscar expresiones regulares en archivos PDF"?

R: El tutorial "Buscar expresiones regulares en archivos PDF" tiene como objetivo mostrar cómo utilizar la biblioteca Aspose.PDF para .NET para buscar y extraer texto que coincida con un patrón de expresión regular específico dentro de un archivo PDF. El tutorial proporciona una guía completa y un código C# de muestra para demostrar el proceso.

#### P: ¿Cómo ayuda este tutorial a buscar texto usando expresiones regulares en un documento PDF?

R: Este tutorial proporciona un método paso a paso para utilizar la biblioteca Aspose.PDF para realizar búsquedas de texto en un documento PDF basándose en un patrón de expresión regular. Detalla cómo configurar el proyecto, cargar el documento PDF, definir un patrón de expresión regular y recuperar los fragmentos de texto coincidentes.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial?

R: Antes de comenzar este tutorial, debes tener un conocimiento básico del lenguaje de programación C#. Además, debe tener instalada la biblioteca Aspose.PDF para .NET. Puede obtenerlo del sitio web de Aspose o utilizar NuGet para integrarlo en su proyecto.

#### P: ¿Cómo configuro mi proyecto para seguir este tutorial?

R: Para comenzar, cree un nuevo proyecto C# en su entorno de desarrollo integrado (IDE) preferido y agregue una referencia a la biblioteca Aspose.PDF para .NET. Esto le permitirá aprovechar las capacidades de la biblioteca dentro de su proyecto.

#### P: ¿Puedo utilizar expresiones regulares para buscar texto en un documento PDF?

 R: Sí, este tutorial demuestra cómo usar expresiones regulares para buscar y extraer texto de un documento PDF. Implica utilizar el`TextFragmentAbsorber` clase y especificando un patrón de expresión regular para encontrar frases que coincidan con el patrón proporcionado.

#### P: ¿Cómo defino el patrón de expresión regular para la búsqueda de texto?

 R: Para definir un patrón de expresión regular para la búsqueda de texto, cree un`TextFragmentAbsorber` objeto y establecer su patrón usando el`Text` parámetro. Reemplazar el patrón predeterminado`"\\d{4}-\\d{4}"` en el código del tutorial con el patrón de expresión regular que desee.

#### P: ¿Cómo puedo habilitar el uso de expresiones regulares para la búsqueda de texto?

 R: El uso de expresiones regulares se habilita creando un`TextSearchOptions` objeto y estableciendo su valor en`true` . Asigne este objeto al`TextSearchOptions` propiedad de la`TextFragmentAbsorber` instancia. Esto garantiza que se aplique el patrón de expresión regular durante la búsqueda de texto.

#### P: ¿Puedo recuperar fragmentos de texto que coincidan con el patrón de expresión regular?

 R: Absolutamente. Después de aplicar la búsqueda de expresiones regulares en el documento PDF, puede recuperar los fragmentos de texto extraídos utilizando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto. Estos fragmentos de texto contienen los segmentos de texto que coinciden con el patrón de expresión regular especificado.

#### P: ¿A qué puedo acceder desde los fragmentos de texto recuperados?

R: Desde los fragmentos de texto recuperados, puede acceder a varias propiedades, como el contenido del texto coincidente, la posición (coordenadas X e Y), la información de la fuente (nombre, tamaño, color) y más. El código de muestra dentro del bucle del tutorial demuestra cómo acceder y mostrar estas propiedades.

#### P: ¿Cómo puedo personalizar acciones en los fragmentos de texto extraídos?

R: Una vez que tenga los fragmentos de texto extraídos, puede personalizar el código dentro del bucle para realizar acciones adicionales en cada fragmento de texto. Esto puede incluir guardar el texto extraído, analizar patrones o implementar cambios de formato según sus requisitos.