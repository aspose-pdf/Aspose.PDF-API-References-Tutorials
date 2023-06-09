---
title: Cambiar el tamaño de las imágenes
linktitle: Cambiar el tamaño de las imágenes
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para cambiar el tamaño de imágenes en un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 250
url: /es/net/programming-with-images/resize-images/
---

En este tutorial, lo guiaremos a través de cómo cambiar el tamaño de las imágenes en un documento PDF usando Aspose.PDF para .NET. Siga estos pasos para realizar esta operación fácilmente.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro entorno de desarrollo instalado y configurado.
- Un conocimiento básico del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada. Puede descargarlo desde el sitio web oficial de Aspose.

## Paso 1: Cargar el documento PDF

Para comenzar, use el siguiente código para cargar el documento PDF:

```csharp
// Inicializar el tiempo
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abre el documento
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Asegúrese de proporcionar la ruta correcta a su documento PDF.

## Paso 2: Inicialización de las opciones de optimización

Antes de cambiar el tamaño de las imágenes, debemos inicializar las opciones de optimización. Usa el siguiente código:

```csharp
// Inicializar opciones de optimización
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Activar la opción CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Establecer calidad de imagen
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Activar la opción RedimensionarImagenes
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Establecer resolución máxima
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

Puede ajustar la configuración de optimización según sus necesidades.

## Paso 3: Optimización del documento PDF

Ahora vamos a optimizar el documento PDF usando las opciones de optimización que definimos. Usa el siguiente código:

```csharp
// Optimice el documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Guardar el documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Asegúrese de proporcionar la ruta y el nombre de archivo deseados para el documento PDF actualizado.

### Ejemplo de código fuente para Redimensionar imágenes usando Aspose.PDF para .NET 
```csharp
// Tiempo de inicialización
var time = DateTime.Now.Ticks;
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Inicializar opciones de optimización
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Establecer la opción CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Establecer la opción ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Establecer la opción ResizeImage
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Establecer la opción MaxResolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// Optimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha cambiado correctamente el tamaño de las imágenes en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede aplicar este método a sus propios proyectos para cambiar el tamaño de las imágenes en archivos PDF.