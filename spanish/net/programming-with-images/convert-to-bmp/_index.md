---
title: Convertir a BMP
linktitle: Convertir a BMP
second_title: Referencia de API de Aspose.PDF para .NET
description: Convierta fácilmente PDF a imágenes BMP individuales con Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-images/convert-to-bmp/
---

Esta guía lo guiará paso a paso sobre cómo convertir un archivo PDF a imágenes BMP individuales usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Paso 3: Convierta cada página a BMP

 En este paso, revisaremos cada página del documento PDF y las convertiremos en imágenes BMP individuales. Usaremos un`for`bucle para iterar a través de todas las páginas.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Cree una secuencia para guardar la imagen BMP
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // Crear un objeto de resolución
         Resolution resolution = new Resolution(300);
        
         // Cree un dispositivo BMP con los atributos especificados
         //Ancho, alto, resolución, tamaño de página
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // Convierta una página específica y guarde la imagen en la secuencia
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Cierra la corriente
         imageStream.Close();
     }
}
```

### Ejemplo de código fuente para Convertir a BMP usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// Crear objeto de resolución
		Resolution resolution = new Resolution(300);
		// Crear dispositivo BMP con atributos específicos
		// Ancho, Alto, Resolución, Tamaño de página
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// Convierta una página en particular y guarde la imagen para transmitir
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Cerrar transmisión
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## Conclusión

¡Felicidades! Ha convertido con éxito un archivo PDF en imágenes BMP individuales utilizando Aspose.PDF para .NET. Las imágenes BMP se guardan en el directorio especificado. Ahora puede utilizar estas imágenes en sus proyectos o aplicaciones.