---
title: Obtener propiedades
linktitle: Obtener propiedades
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para obtener propiedades de PDF como dimensiones de caja y rotación usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-pdf-pages/get-properties/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para obtener las propiedades de un PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo acceder a diferentes propiedades de una página PDF, como cuadro de arte, cuadro de recorte, cuadro de recorte, etc., utilizando Aspose.PDF para .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: establecer el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación del archivo PDF cuyas propiedades desea obtener. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Abra el documento PDF
 A continuación, debe abrir el documento PDF utilizando el`Document` clase de Aspose.PDF. Asegúrese de especificar la ruta correcta al archivo PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Paso 3: acceda a la colección de páginas
 Ahora puede acceder a la colección de páginas del documento usando el`Pages` propiedad de la`pdfDocument` objeto.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Paso 4: Ir a una página específica
Luego puede saltar a una página específica usando el índice de la página en la colección. En el ejemplo siguiente, accedemos a la segunda página (índice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Paso 5: Obtenga las propiedades de la página
 Ahora puede obtener las diferentes propiedades de la página PDF, como cuadro de arte, cuadro de recorte, cuadro de recorte, etc., utilizando las propiedades correspondientes de la`pdfPage` objeto.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Ejemplo de código fuente para Obtener propiedades usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Obtener colección de páginas
PageCollection pageCollection = pdfDocument.Pages;
// Obtener página particular
Page pdfPage = pageCollection[1];
// Obtener propiedades de la página
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Conclusión
¡Felicidades! Ha obtenido con éxito las propiedades de un PDF utilizando Aspose.PDF para .NET. Aprendió a abrir un documento PDF, navegar a una página específica y obtener varias propiedades de página, como cuadros de dimensiones y rotación. Ahora puede usar esta información para personalizar el manejo de sus archivos PDF en función de sus propiedades.

Asegúrese de consultar la documentación oficial de Aspose.PDF para .NET para obtener más información sobre funciones avanzadas y posibilidades de personalización.
