---
title: Imagen MCG a PDF
linktitle: Imagen MCG a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Convierta fácilmente imágenes CGM a PDF con Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-images/cgm-image-to-pdf/
---

Esta guía paso a paso explica cómo convertir una imagen CGM a PDF usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su archivo CGM.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Definir el archivo de entrada y salida

 Configure el nombre del archivo de entrada CGM y el nombre del archivo de salida PDF. Reemplazar`"corvette.cgm"` con el nombre de su archivo CGM y actualice`dataDir`con el directorio de salida deseado y el nombre del archivo PDF.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## Paso 3: Convierta la imagen CGM a PDF

 Utilizar el`Produce` método de`PdfProducer` para convertir el archivo CGM a formato PDF usando`ImportFormat.Cgm`. Especifique el archivo de entrada CGM y el archivo de salida PDF.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### Ejemplo de código fuente para CGMImage a PDF usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// Guardar CGM en formato PDF
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Conclusión

¡Felicidades! Ha convertido con éxito un archivo CGM a PDF utilizando Aspose.PDF para .NET. Ahora puede utilizar el archivo PDF generado en sus proyectos o aplicaciones.