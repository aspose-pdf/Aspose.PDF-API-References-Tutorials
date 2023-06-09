---
title: Crear imágenes en miniatura
linktitle: Crear imágenes en miniatura
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente miniaturas de imágenes a partir de archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-images/create-thumbnail-images/
---

Esta guía lo guiará paso a paso sobre cómo crear miniaturas de imágenes a partir de archivos PDF usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio que contiene sus archivos PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: obtenga los nombres de todos los archivos PDF en un directorio

 En este paso, recuperaremos los nombres de todos los archivos PDF presentes en el directorio especificado utilizando C#.`Directory`clase. Los archivos se almacenarán en una matriz de cadenas.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Paso 3: Explore todos los archivos PDF y sus páginas

 En este paso, revisaremos todos los archivos PDF y sus páginas para crear miniaturas de imágenes. Usaremos un`for` bucle para iterar a través de todos los archivos.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Abre el documento PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Ir a través de todas las páginas del documento
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Cree una transmisión para guardar la imagen en miniatura
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Crear un objeto de resolución
             Resolution resolution = new Resolution(300);
            
             // Cree un dispositivo JPEG con los atributos especificados
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Convierta una página específica y guarde la imagen en la secuencia
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Cierra la corriente
             imageStream.Close();
         }
     }
}
```

### Ejemplo de código fuente para crear imágenes en miniatura con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Recupere los nombres de todos los archivos PDF en un directorio en particular
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Iterar a través de todas las entradas de archivos en la matriz
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Abrir documento
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Crear objeto de resolución
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, resolución, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Convierta una página en particular y guarde la imagen para transmitir
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Cerrar transmisión
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Conclusión

¡Felicidades! Ha creado con éxito miniaturas de imágenes a partir de archivos PDF utilizando Aspose.PDF para .NET. Las miniaturas de imágenes se guardan en el directorio especificado. Ahora puede usar estas miniaturas para mostrar una vista previa de sus archivos PDF.