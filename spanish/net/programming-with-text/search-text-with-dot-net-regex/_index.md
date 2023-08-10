---
title: Texto de búsqueda con Dot Net Regex
linktitle: Texto de búsqueda con Dot Net Regex
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar texto usando expresiones regulares de .NET en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 480
url: /es/net/programming-with-text/search-text-with-dot-net-regex/
---

Este tutorial explica cómo usar Aspose.PDF para .NET para buscar texto usando expresiones regulares de .NET en un documento PDF. El código fuente de C# proporcionado demuestra el proceso paso a paso.

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

## Paso 4: Cree un objeto .NET Regex

 Crear un`.NET Regex` objeto para definir el patrón de búsqueda:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Reemplazar`@"[\S]+"` con el patrón de expresión regular deseado.

## Paso 5: Cargue el documento PDF

 Cargue el documento PDF usando el`Document` clase:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Reemplazar`"SearchTextRegex.pdf"` con el nombre real de su archivo PDF.

## Paso 6: Obtener una página específica

Obtenga la página deseada del documento:

```csharp
Page page = document.Pages[1];
```

 Reemplazar`1` con el número de página deseado (índice basado en 1).

## Paso 7: Crea un TextFragmentAbsorber

 Crear un`TextFragmentAbsorber`objeto para encontrar todas las instancias de la expresión regular de entrada:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Paso 8: Acepte el absorbedor para la página

Acepte el absorbedor para la página:

```csharp
page.Accept(textFragmentAbsorber);
```

## Paso 9: recupera los fragmentos de texto extraídos

Obtenga los fragmentos de texto extraídos usando el`TextFragments` propiedad de la`TextFragmentAbsorber` objeto:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Paso 10: recorrer los fragmentos de texto

Recorra los fragmentos de texto recuperados y realice las acciones deseadas:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Modifique el código dentro del ciclo para realizar más acciones en cada fragmento de texto si es necesario.

### Ejemplo de código fuente para Buscar texto con Dot Net Regex usando Aspose.PDF para .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear objeto Regex para encontrar todas las palabras
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Abrir documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Obtener una página en particular
Page page = document.Pages[1];
// Cree un objeto TextAbsorber para encontrar todas las instancias de la expresión regular de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Aceptar el absorbedor para la página.
page.Accept(textFragmentAbsorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Bucle a través de los fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo buscar texto usando expresiones regulares de .NET en un documento PDF usando Aspose.PDF para .NET. Este tutorial proporcionó una guía paso a paso, desde configurar el proyecto hasta acceder a los fragmentos de texto extraídos. Ahora puede incorporar este código en sus propios proyectos de C# para realizar búsquedas de texto avanzadas en archivos PDF.