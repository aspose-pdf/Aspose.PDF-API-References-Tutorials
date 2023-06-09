---
title: Reducir imágenes
linktitle: Reducir imágenes
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para reducir el tamaño de las imágenes en un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 280
url: /es/net/programming-with-images/shrink-images/
---

En este tutorial, le diremos cómo reducir el tamaño de las imágenes en un documento PDF utilizando Aspose.PDF para .NET. Siga estos pasos para realizar esta operación fácilmente.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro entorno de desarrollo instalado y configurado.
- Un conocimiento básico del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada. Puede descargarlo desde el sitio web oficial de Aspose.

## Paso 1: Cargar el documento PDF

Para comenzar, use el siguiente código para cargar el documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abre el documento
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

Asegúrese de proporcionar la ruta correcta a su documento PDF.

## Paso 2: Inicialización de las opciones de optimización

A continuación, inicializaremos las opciones de optimización para reducir el tamaño de las imágenes. Usa el siguiente código:

```csharp
// Inicializar opciones de optimización
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Activar la opción CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Establecer calidad de imagen
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

Puede ajustar la configuración de optimización según sus necesidades.

## Paso 3: Optimización del documento PDF

Ahora vamos a optimizar el documento PDF reduciendo el tamaño de las imágenes. Usa el siguiente código:

```csharp
// Optimice el documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// Guardar el documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

Asegúrese de proporcionar la ruta y el nombre de archivo deseados para el documento PDF actualizado.

### Ejemplo de código fuente para reducir imágenes usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Inicializar opciones de optimización
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Establecer la opción CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Establecer la opción ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// Optimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha reducido con éxito el tamaño de las imágenes en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede aplicar este método a sus propios proyectos para optimizar el tamaño de las imágenes en archivos PDF.