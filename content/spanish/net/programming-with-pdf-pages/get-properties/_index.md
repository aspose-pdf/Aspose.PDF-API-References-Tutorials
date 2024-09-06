---
title: Obtener propiedades de PDF
linktitle: Obtener propiedades de PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para obtener propiedades de PDF como dimensiones de caja y rotación usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-pdf-pages/get-properties/
---
En este tutorial, le guiaremos paso a paso a través del proceso para obtener las propiedades de un PDF utilizando Aspose.PDF para .NET. Le explicaremos el código fuente C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo acceder a diferentes propiedades de una página PDF, como el cuadro de arte, el cuadro de recorte, el cuadro de recorte, etc., utilizando Aspose.PDF para .NET.

## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: Establecer el directorio del documento
En primer lugar, debe establecer la ruta de acceso al directorio de sus documentos. Esta es la ubicación del archivo PDF cuyas propiedades desea obtener. Reemplace "DIRECTORIO DE SUS DOCUMENTOS" por la ruta correspondiente.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Abra el documento PDF
 A continuación, debe abrir el documento PDF utilizando el`Document` Clase de Aspose.PDF. Asegúrese de especificar la ruta correcta al archivo PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Paso 3: Acceda a la colección de páginas
 Ahora puedes acceder a la colección de páginas del documento usando el`Pages` propiedad de la`pdfDocument` objeto.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Paso 4: Ir a una página específica
Luego, puede saltar a una página específica utilizando el índice de la página en la colección. En el ejemplo siguiente, accedemos a la segunda página (índice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Paso 5: Obtener las propiedades de la página
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

### Código fuente de muestra para obtener propiedades mediante Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Obtener colección de páginas
PageCollection pageCollection = pdfDocument.Pages;
// Obtener página específica
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
¡Felicitaciones! Obtuvo con éxito las propiedades de un PDF con Aspose.PDF para .NET. Aprendió a abrir un documento PDF, navegar a una página específica y obtener varias propiedades de página, como cuadros de dimensión y rotación. Ahora puede usar esta información para personalizar el manejo de sus archivos PDF en función de sus propiedades.

Asegúrese de consultar la documentación oficial de Aspose.PDF para .NET para obtener más información sobre las funciones avanzadas y las posibilidades de personalización.

### Preguntas frecuentes

#### P: ¿Cómo puedo obtener las propiedades de un PDF usando Aspose.PDF para .NET?

R: Para obtener las propiedades de un PDF usando Aspose.PDF para .NET, puede seguir estos pasos:

1. Establezca el directorio del documento especificando la ruta al archivo PDF cuyas propiedades desea recuperar.
2.  Abra el documento PDF utilizando el`Document` clase de Aspose.PDF, que proporciona la ruta correcta al archivo PDF.
3.  Acceda a la colección de páginas del documento mediante el`Pages` propiedad de la`pdfDocument` objeto.
4. Salte a una página específica utilizando el índice de la página en la colección (la indexación comienza desde 1).
5.  Obtenga las diferentes propiedades de la página PDF, como ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number y Rotation, utilizando las propiedades correspondientes de la`pdfPage` objeto.

#### P: ¿Cuáles son las diferentes propiedades de una página PDF que puedo recuperar usando Aspose.PDF para .NET?

R: Puede recuperar varias propiedades de una página PDF utilizando Aspose.PDF para .NET, como:

- ArtBox: Representa las dimensiones de la ilustración de la página.
- BleedBox: representa las dimensiones del sangrado de la página.
- CropBox: representa las dimensiones del contenido visible de la página después del recorte.
- MediaBox: Representa las dimensiones del medio físico de la página.
- TrimBox: representa las dimensiones del contenido recortado de la página.
- Rect: Representa las dimensiones del cuadro delimitador de la página.
- Número de página: Representa el número de página en el documento.
- Rotar: Representa el ángulo de rotación de la página.

#### P: ¿Cómo puedo acceder a una página específica en el documento PDF para recuperar sus propiedades?

 A: Para acceder a una página específica en el documento PDF y recuperar sus propiedades, puede utilizar el`Pages` propiedad de la`pdfDocument` objeto para acceder a la colección de páginas del documento. Luego, puede usar el índice de la página en la colección para saltar a la página deseada. Por ejemplo, para acceder a la segunda página, puede usar`pdfDocument.Pages[1]` (la indexación comienza desde 1).

#### P: ¿Puedo realizar operaciones en las propiedades recuperadas, como modificar o cambiar el tamaño de los cuadros de página?

R: Sí, una vez que recupere las propiedades de una página PDF con Aspose.PDF para .NET, podrá realizar diversas operaciones en ellas. Por ejemplo, podrá modificar las dimensiones de los cuadros de la página, rotar la página o utilizar la información recuperada para el procesamiento y la manipulación personalizados del documento PDF.

#### P: ¿Aspose.PDF para .NET admite la extracción de propiedades de archivos PDF cifrados o protegidos con contraseña?

R: Sí, Aspose.PDF para .NET permite extraer propiedades de archivos PDF cifrados o protegidos con contraseña. Siempre que proporcione la contraseña correcta para abrir el documento PDF, podrá acceder a sus propiedades y recuperarlas utilizando el mismo enfoque que se muestra en el tutorial.