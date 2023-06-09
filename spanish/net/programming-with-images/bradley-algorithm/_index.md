---
title: Algoritmo de Bradley
linktitle: Algoritmo de Bradley
second_title: Referencia de API de Aspose.PDF para .NET
description: Convierta un documento PDF utilizando el algoritmo de Bradley con Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-images/bradley-algorithm/
---

Esta guía paso a paso explica cómo usar el algoritmo de Bradley con Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Paso 3: Definir archivos de salida

 Defina los nombres de archivo de salida para la imagen resultante y la imagen binaria. Reemplazar`"resultant_out.tif"` y`"37116-bin_out.tif"` con los nombres deseados para los archivos de salida.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Paso 4: crea el objeto de resolución

 Crear un`Resolution` objeto para establecer la resolución de la imagen TIFF. En este ejemplo, estamos utilizando una resolución de 300 ppp.

```csharp
Resolution resolution = new Resolution(300);
```

## Paso 5: Cree el objeto TiffSettings

 Crear un`TiffSettings` objeto para especificar la configuración del archivo TIFF de salida. En este ejemplo, estamos usando compresión LZW y una profundidad de color de 1 bit por píxel (formato de 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Paso 6: Cree el dispositivo TIFF

 Cree un dispositivo TIFF usando el`TiffDevice` objeto, especificando la resolución y la configuración TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Paso 7: Convierte la página específica y guarda la imagen

 Utilizar el`Process` método del dispositivo TIFF para convertir una página específica del documento PDF y guardar la imagen en un archivo TIFF. Especifique la ruta de salida del archivo.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Paso 8: Binarizar la imagen usando el algoritmo de Bradley

 Utilizar el`BinarizeBradley`método del dispositivo TIFF para binarizar la imagen utilizando el algoritmo de Bradley. Este método toma un flujo de entrada de la imagen original y un flujo de salida de la imagen binaria. Especifique el umbral de binarización (0,1 en este ejemplo).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Ejemplo de código fuente para el algoritmo de Bradley usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Crear objeto de resolución
Resolution resolution = new Resolution(300);
// Crear objeto TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Crear dispositivo TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Convierta una página en particular y guarde la imagen para transmitir
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Conclusión

¡Felicidades! Ha completado con éxito la conversión utilizando el algoritmo de Bradley con Aspose.PDF para .NET. Ahora puede utilizar las imágenes resultantes en sus proyectos o aplicaciones.