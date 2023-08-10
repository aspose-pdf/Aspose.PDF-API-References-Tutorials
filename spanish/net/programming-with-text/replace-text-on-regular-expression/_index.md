---
title: Reemplazar texto en expresión regular
linktitle: Reemplazar expresión regular de Texton
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a reemplazar texto basado en una expresión regular en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 360
url: /es/net/programming-with-text/replace-text-on-regular-expression/
---

En este tutorial, explicaremos cómo reemplazar texto basado en una expresión regular en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Proporcionaremos una guía paso a paso junto con el código fuente de C# necesario.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Aspose.PDF para la biblioteca .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Establezca la ruta al directorio donde tiene el archivo PDF de entrada. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir`variable con la ruta a su archivo PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento PDF

 Cargue el documento PDF usando el`Document` clase de la biblioteca Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Paso 3: busque y reemplace texto usando expresiones regulares

 Crear un`TextFragmentAbsorber` objeto y especifique el patrón de expresión regular para encontrar todas las frases que coincidan con el patrón. Configure la opción de búsqueda de texto para habilitar el uso de expresiones regulares.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Como 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Paso 4: reemplazar texto

Recorra los fragmentos de texto extraídos y reemplace el texto según sea necesario. Actualice el texto y otras propiedades, como la fuente, el tamaño de fuente, el color de primer plano y el color de fondo.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Paso 5: Guarde el PDF modificado

Guarde el documento PDF modificado en el archivo de salida especificado.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para Reemplazar expresión regular de Texton usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Cree un objeto TextAbsorber para encontrar todas las frases que coincidan con la expresión regular
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Como 1999-2000
// Establezca la opción de búsqueda de texto para especificar el uso de expresiones regulares
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Aceptar el absorbedor para una sola página
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Bucle a través de los fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Actualizar texto y otras propiedades
	textFragment.Text = "New Phrase";
	// Establecer en una instancia de un objeto.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendió a reemplazar texto basado en una expresión regular en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso y ejecutando el código C# provisto, puede cargar un documento PDF, buscar texto usando una expresión regular, reemplazarlo y guardar el PDF modificado.