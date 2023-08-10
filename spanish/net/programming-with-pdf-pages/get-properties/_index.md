---
title: Obtener propiedades de PDF
linktitle: Obtener propiedades de PDF
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
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación del archivo PDF cuyas propiedades desea obtener. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

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

### Preguntas frecuentes

#### P: ¿Cómo puedo obtener las propiedades de un PDF usando Aspose.PDF para .NET?

R: Para obtener las propiedades de un PDF usando Aspose.PDF para .NET, puede seguir estos pasos:

1. Establezca el directorio del documento especificando la ruta al archivo PDF cuyas propiedades desea recuperar.
2.  Abra el documento PDF usando el`Document` clase de Aspose.PDF, proporcionando la ruta correcta al archivo PDF.
3.  Acceda a la colección de páginas del documento usando el`Pages` propiedad de la`pdfDocument` objeto.
4. Salta a una página específica usando el índice de la página en la colección (la indexación comienza desde 1).
5.  Obtenga las diferentes propiedades de la página PDF, como ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Número de página y Rotación, utilizando las propiedades correspondientes del`pdfPage` objeto.

#### P: ¿Cuáles son las diferentes propiedades de una página PDF que puedo recuperar con Aspose.PDF para .NET?

R: Puede recuperar varias propiedades de una página PDF utilizando Aspose.PDF para .NET, como:

- ArtBox: representa las dimensiones de la ilustración de la página.
- BleedBox: Representa las dimensiones del sangrado de la página.
- CropBox: representa las dimensiones del contenido visible de la página después de recortar.
- MediaBox: Representa las dimensiones del soporte físico de la página.
- TrimBox: representa las dimensiones del contenido recortado de la página.
- Rect: representa las dimensiones del cuadro delimitador de la página.
- Número de página: representa el número de página del documento.
- Rotar: representa el ángulo de rotación de la página.

#### P: ¿Cómo accedo a una página específica en el documento PDF para recuperar sus propiedades?

 R: Para acceder a una página específica en el documento PDF y recuperar sus propiedades, puede usar el`Pages` propiedad de la`pdfDocument` objeto para acceder a la colección de páginas del documento. Luego, puede usar el índice de la página en la colección para saltar a la página deseada. Por ejemplo, para acceder a la segunda página, puede utilizar`pdfDocument.Pages[1]` (la indexación comienza desde 1).

#### P: ¿Puedo realizar operaciones en las propiedades recuperadas, como modificar o cambiar el tamaño de los cuadros de página?

R: Sí, una vez que recupera las propiedades de una página PDF usando Aspose.PDF para .NET, puede realizar varias operaciones en ellas. Por ejemplo, puede modificar las dimensiones de los cuadros de página, girar la página o utilizar la información recuperada para el procesamiento y la manipulación personalizados del documento PDF.

#### P: ¿Admite Aspose.PDF para .NET la extracción de propiedades de archivos PDF cifrados o protegidos con contraseña?

R: Sí, Aspose.PDF para .NET admite la extracción de propiedades de archivos PDF cifrados o protegidos con contraseña. Siempre que proporcione la contraseña correcta para abrir el documento PDF, puede acceder y recuperar sus propiedades utilizando el mismo enfoque que se muestra en el tutorial.