---
title: Optimizar tamaño de archivo
linktitle: Optimizar tamaño de archivo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a optimizar el tamaño de archivo de sus documentos PDF con Aspose.PDF para .NET usando esta guía paso a paso.
type: docs
weight: 250
url: /es/net/programming-with-document/optimizefilesize/
---
Aspose.PDF para .NET es una biblioteca que permite a los desarrolladores crear, editar y manipular archivos PDF en sus aplicaciones .NET. Una de las características más útiles de esta biblioteca es la capacidad de optimizar el tamaño de archivo de un documento PDF. En este artículo, proporcionaremos una guía paso a paso para optimizar el tamaño de archivo de un documento PDF usando Aspose.PDF para .NET.

## Paso 1: Cargue el documento PDF

 El primer paso para optimizar el tamaño de archivo de un documento PDF es cargar el documento en su aplicación. Puedes hacer esto usando el`Document` clase proporcionada por la biblioteca Aspose.PDF para .NET. Aquí hay un ejemplo de cómo cargar un documento PDF:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Asegúrese de reemplazar`YOUR DOCUMENT DIRECTORY` con la ruta al directorio que contiene su documento PDF.

## Paso 2: Establecer opciones de optimización

Una vez que haya cargado el documento PDF, puede configurar las opciones de optimización para especificar qué partes del documento desea optimizar. El`OptimizationOptions` La clase proporcionada por la biblioteca Aspose.PDF para .NET le permite especificar una variedad de opciones para optimizar el tamaño de archivo del documento PDF. Aquí hay un ejemplo de cómo configurar algunas opciones de optimización:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

En este ejemplo, estamos configurando las siguientes opciones:
- `LinkDuplcateStreams`: esta opción habilita la eliminación de secuencias duplicadas en el documento PDF, lo que puede ayudar a reducir el tamaño del archivo.
- `RemoveUnusedObjects`: esta opción permite la eliminación de cualquier objeto no utilizado en el documento PDF, lo que también puede ayudar a reducir el tamaño del archivo.
- `RemoveUnusedStreams`: esta opción permite la eliminación de cualquier secuencia no utilizada en el documento PDF, lo que puede reducir aún más el tamaño del archivo.
- `CompressImages`: esta opción permite la compresión de imágenes en el documento PDF, lo que puede reducir significativamente el tamaño del archivo.
- `ImageQuality`Esta opción establece la calidad de las imágenes comprimidas. Una configuración de menor calidad dará como resultado un tamaño de archivo más pequeño, pero también puede resultar en una imagen de menor calidad.

## Paso 4: Optimice el documento PDF

 Ahora que ha configurado las opciones de optimización, puede optimizar el documento PDF usando el`OptimizeResources` método proporcionado por el`Document` clase. Aquí hay un ejemplo de cómo optimizar el documento PDF:

```csharp
// Optimice el tamaño del archivo eliminando objetos no utilizados
pdfDocument.OptimizeResources(optimizationOptions);
```

## Paso 5: Guarde el documento PDF optimizado

Una vez que haya optimizado el documento PDF, puede guardar la versión optimizada en un nuevo archivo. Aquí hay un ejemplo de cómo guardar el documento PDF optimizado:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Guardar documento de salida
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para optimizar el tamaño del archivo con Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// Optimice el tamaño del archivo eliminando objetos no utilizados
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Guardar documento de salida
pdfDocument.Save(dataDir);
```
