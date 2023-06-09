---
title: Reemplazar primera ocurrencia
linktitle: Reemplazar primera ocurrencia
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a reemplazar la primera aparición de texto en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 330
url: /es/net/programming-with-text/replace-first-occurrence/
---

En este tutorial, explicaremos cómo reemplazar la primera aparición de un texto específico en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Pasaremos por el proceso paso a paso de abrir un documento PDF, encontrar la primera aparición de la frase de búsqueda, reemplazar el texto, actualizar las propiedades y guardar el PDF modificado usando el código fuente de C# provisto.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde tiene el archivo PDF de entrada. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a su archivo PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 A continuación, abrimos el documento PDF usando el`Document` clase de la biblioteca Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Paso 3: encuentre la primera ocurrencia de la frase de búsqueda

 Creamos un`TextFragmentAbsorber` acéptelo para todas las páginas del documento PDF para encontrar todas las instancias de la frase de búsqueda.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Paso 4: reemplaza el texto

Si la frase de búsqueda se encuentra en el documento PDF, recuperamos la primera aparición del fragmento de texto y actualizamos sus propiedades con el nuevo texto y formato.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## Paso 5: Guarde el PDF modificado

Finalmente, guardamos el documento PDF modificado en el archivo de salida especificado.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para Reemplazar la primera ocurrencia usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Aceptar el absorbedor para todas las páginas.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// Obtener la primera aparición de texto y reemplazar
	TextFragment textFragment = textFragmentCollection[1];
	// Actualizar texto y otras propiedades
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## Conclusión

En este tutorial, aprendió a reemplazar la primera aparición de un texto específico en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso y ejecutando el código C# provisto, puede abrir un documento PDF, encontrar la primera aparición de una frase de búsqueda, reemplazar el texto, actualizar las propiedades y guardar el PDF modificado.