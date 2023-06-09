---
title: Imágenes de reducción rápida
linktitle: Imágenes de reducción rápida
second_title: Referencia de API de Aspose.PDF para .NET
description: Reduzca rápidamente el tamaño de las imágenes en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 130
url: /es/net/programming-with-images/fast-shrink-images/
---

Esta guía lo guiará paso a paso sobre cómo reducir rápidamente el tamaño de las imágenes en un archivo PDF usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Inicializa la hora

Antes de comenzar, inicializaremos el tiempo para medir el rendimiento de la compresión. Agregue el siguiente código para registrar la hora de inicio:

```csharp
var time = DateTime.Now.Ticks;
```

## Paso 2: Definir el directorio de documentos

 Asegúrese de establecer el directorio de documentos correcto. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## Paso 4: inicialice las opciones de optimización

 En este paso, inicializaremos las opciones de optimización para la compresión de imágenes. Crear una instancia de`OptimizationOptions` y configure las opciones apropiadas. En este ejemplo, habilitamos la compresión de imágenes, configuramos la calidad de imagen en 75 y usamos la versión de compresión rápida.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## Paso 5: optimizar el documento PDF

 En este paso, optimizaremos el documento PDF utilizando las opciones de optimización definidas anteriormente. Llama a`OptimizeResources` metodo de la`pdfDocument` objeto y pasar las opciones de optimización.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Paso 6: Guarde el documento PDF actualizado

 Guarde el documento PDF actualizado usando el`Save` metodo de la`pdfDocument` objeto. Especifique la ruta de salida para el archivo PDF.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para imágenes de reducción rápida usando Aspose.PDF para .NET 
```csharp
// Tiempo de inicialización
var time = DateTime.Now.Ticks;
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Inicializar opciones de optimización
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Establecer la opción CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Establecer la opción ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// Establezca la versión de compresión de Imagae en rápida
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// Optimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Rápidamente redujo el tamaño de las imágenes en un PDF usando Aspose.PDF para .NET. El archivo PDF optimizado se guarda en el directorio especificado. Ahora puede usar este archivo PDF con imágenes reducidas para un almacenamiento o uso compartido más eficiente.