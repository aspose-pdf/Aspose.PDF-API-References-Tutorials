---
title: Extraer imágenes
linktitle: Extraer imágenes
second_title: Referencia de API de Aspose.PDF para .NET
description: Extraiga fácilmente imágenes de un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-images/extract-images/
---

Esta guía lo guiará paso a paso sobre cómo extraer imágenes de un archivo PDF usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Paso 3: extrae una imagen específica

 En este paso, vamos a extraer una imagen específica de una página en particular. Utilizar el`Images` colección de la página`s `Objeto de recursos para acceder a la imagen deseada. En el siguiente ejemplo, extraemos la imagen con el índice 1 de la primera página.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Paso 4: Guarda la imagen extraída

 Guarde la imagen extraída en un archivo usando el`Save` metodo de la`xImage`objeto. Especifique la ruta de salida y el formato de la imagen (en este ejemplo estamos usando el formato JPEG).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Paso 5: Guarde el archivo PDF actualizado

 Guarde el archivo PDF actualizado usando el`Save` metodo de la`pdfDocument` objeto. Especifique la ruta de salida para el archivo PDF.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para extraer imágenes usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Extraer una imagen en particular
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Guardar imagen de salida
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Guardar archivo PDF actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Conclusión

¡Felicidades! Ha extraído con éxito imágenes de un PDF utilizando Aspose.PDF para .NET. La imagen extraída se guarda en el directorio especificado y también se guarda el archivo PDF actualizado. Ahora puede utilizar estos archivos para sus necesidades específicas.