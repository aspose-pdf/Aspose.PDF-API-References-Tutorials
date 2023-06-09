---
title: Compresión de decodificación plana
linktitle: Compresión de decodificación plana
second_title: Referencia de API de Aspose.PDF para .NET
description: Comprima eficientemente imágenes en un PDF utilizando la compresión Flate Decode con Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/programming-with-images/flate-decode-compression/
---

Esta guía lo guiará paso a paso sobre cómo comprimir imágenes usando la compresión Flate Decode en un archivo PDF usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Asegúrese de establecer el directorio de documentos correcto. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## Paso 3: inicialice las opciones de optimización

 En este paso, inicializaremos las opciones de optimización para la compresión de imágenes. Crear una instancia de`OptimizationOptions` y configure las opciones apropiadas. En este ejemplo, estamos utilizando la compresión Flate Decode para optimizar las imágenes.

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## Paso 4: optimizar el documento PDF

 En este paso, optimizaremos el documento PDF utilizando las opciones de optimización definidas anteriormente. Llama a`OptimizeResources` metodo de la`doc` objeto y pasar las opciones de optimización.

```csharp
doc.OptimizeResources(optimizationOptions);
```

## Paso 5: Guarde el documento PDF actualizado

 Guarde el documento PDF actualizado usando el`Save` metodo de la`doc` objeto. Especifique la ruta de salida para el archivo PDF.

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### Ejemplo de código fuente para Flate Decode Compression usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document doc = new Document(dataDir + "AddImage.pdf");
// Inicializar opciones de optimización
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
//Para optimizar la imagen usando FlateDecode Compression establezca las opciones de optimización para Flate
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
// Establecer opciones de optimización
doc.OptimizeResources(optimizationOptions);
// Guardar documento
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusión

¡Felicidades! Ha comprimido con éxito imágenes en un PDF utilizando la compresión Flate Decode con Aspose.PDF para .NET. El archivo PDF optimizado se guarda en el directorio especificado. Ahora puede usar este archivo PDF para necesidades de almacenamiento o uso compartido más eficientes.