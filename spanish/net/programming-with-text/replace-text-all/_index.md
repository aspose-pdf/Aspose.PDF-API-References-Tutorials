---
title: Reemplazar texto todo
linktitle: Reemplazar texto todo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a reemplazar todo el texto en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 350
url: /es/net/programming-with-text/replace-text-all/
---

En este tutorial, explicaremos cómo reemplazar todo el texto en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Proporcionaremos una guía paso a paso junto con el código fuente de C# necesario.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Paso 3: buscar y reemplazar texto

 Crear un`TextFragmentAbsorber` objeto para encontrar todas las instancias de la frase de búsqueda de entrada. Acepte el absorbedor para todas las páginas del documento PDF para extraer los fragmentos de texto.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Paso 4: reemplazar texto

Recorra los fragmentos de texto extraídos y reemplace el texto según sea necesario. Actualice el texto y otras propiedades, como la fuente, el tamaño de fuente, el color de primer plano y el color de fondo.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Paso 5: Guarde el PDF modificado

Guarde el documento PDF modificado en el archivo de salida especificado.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para Reemplazar todo el texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
//Cree un objeto TextAbsorber para encontrar todas las instancias de la frase de búsqueda de entrada
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Aceptar el absorbedor para todas las páginas.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Bucle a través de los fragmentos
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Actualizar texto y otras propiedades
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Guarde el documento PDF resultante.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendió cómo reemplazar todo el texto en un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso y ejecutando el código C# provisto, puede cargar un documento PDF, buscar el texto deseado, reemplazarlo y guardar el PDF modificado.