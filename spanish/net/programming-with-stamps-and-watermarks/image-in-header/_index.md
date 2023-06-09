---
title: Imagen en encabezado
linktitle: Imagen en encabezado
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar una imagen en la sección de encabezado de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/programming-with-stamps-and-watermarks/image-in-header/
---
En este tutorial, lo guiaremos paso a paso sobre cómo agregar una imagen en la sección de encabezado de un documento PDF usando Aspose.PDF para .NET. Usaremos el código fuente de C# proporcionado para abrir un documento PDF existente, crear un búfer de imagen, configurar sus propiedades y agregarlo a todas las páginas del documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF existente

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abra el documento PDF existente
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: crear y agregar la imagen en la sección de encabezado

Ahora que el documento PDF está cargado, podemos crear un búfer de imagen y agregarlo a todas las páginas del documento como una sección de encabezado. Así es cómo:

```csharp
// Crear el búfer de cuadro
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Establecer propiedades de búfer de imagen
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

//Agregar búfer de imagen a todas las páginas
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

El código anterior crea un búfer de imagen a partir del archivo "aspose-logo.jpg" y establece sus propiedades, como el margen superior, la alineación horizontal y vertical. Luego, el sello de imagen se agrega a todas las páginas del documento PDF como una sección de encabezado.

## Paso 4: Guardar el documento PDF modificado

Una vez que se agrega la imagen en la sección de encabezado, podemos guardar el documento PDF modificado. Así es cómo:

```csharp
// Guarde el documento PDF modificado
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Ejemplo de código fuente para Imagein Header usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Crear encabezado
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Establecer propiedades del sello
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Agregar encabezado en todas las páginas
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Conclusión

¡Felicidades! Ha aprendido a agregar una imagen en la sección de encabezado de un documento PDF utilizando Aspose.PDF para .NET. Ahora puede personalizar los encabezados de sus documentos PDF agregando imágenes.
