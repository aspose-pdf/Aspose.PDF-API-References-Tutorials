---
title: Eliminar imágenes
linktitle: Eliminar imágenes
second_title: Referencia de API de Aspose.PDF para .NET
description: Elimine fácilmente imágenes de un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-images/delete-images/
---

Esta guía lo guiará paso a paso sobre cómo eliminar imágenes de un archivo PDF usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## Paso 3: Eliminar una imagen específica

 En este paso, vamos a eliminar una imagen específica de una página en particular. Utilizar el`Delete` método del recurso de la página`Images` objeto para eliminar la imagen. En el siguiente ejemplo, eliminamos la imagen con el índice 1 de la primera página.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## Paso 4: Guarde el archivo PDF actualizado

 Guarde el archivo PDF actualizado usando el`Save` metodo de la`pdfDocument` objeto. Especifique la ruta de salida para el archivo PDF.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Eliminar imágenes usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//Eliminar una imagen en particular
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// Guardar archivo PDF actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## Conclusión

¡Felicidades! Ha eliminado con éxito imágenes de un archivo PDF utilizando Aspose.PDF para .NET. El archivo PDF actualizado se guarda en el directorio especificado. Ahora puede usar este archivo PDF sin las imágenes eliminadas.