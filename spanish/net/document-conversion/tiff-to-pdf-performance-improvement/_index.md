---
title: Mejora del rendimiento de TIFF a PDF
linktitle: Mejora del rendimiento de TIFF a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para mejorar el rendimiento de la conversión de TIFF a PDF con Aspose.PDF para .NET.
type: docs
weight: 310
url: /es/net/document-conversion/tiff-to-pdf-performance-improvement/
---

En este tutorial, lo guiaremos paso a paso sobre cómo mejorar el rendimiento de la conversión de archivos TIFF a PDF utilizando la biblioteca Aspose.PDF para .NET. Detallaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos. Al final de este tutorial, podrá realizar conversiones más rápidas y eficientes de archivos TIFF a PDF.

## Paso 1: establecer el directorio de documentos
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta donde guardó sus archivos.

## Paso 2: Obtenga la lista de archivos TIFF
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
Obtenga una lista de archivos TIFF presentes en el directorio especificado.

## Paso 3: crear una instancia de un objeto de documento
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
Cree una instancia del objeto Documento.

## Paso 4: busque archivos y agréguelos al documento PDF
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
 Revise cada archivo TIFF, cárguelo como un`Bitmap` objeto, luego agréguelo al documento PDF. También se configuran parámetros como márgenes, resolución y escala de la imagen.

## Paso 5: Guarde el archivo PDF resultante
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
Guarde el documento PDF resultante en el directorio especificado.

### Ejemplo de código fuente para la mejora del rendimiento de TIFF a PDF con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Obtener una lista de archivos de imagen tiff
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

// Crear una instancia de un objeto de documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Navegar a través de los archivos y ellos en el archivo pdf
foreach (string myFile in files)
{

	// Cargue todos los archivos tiff en una matriz de bytes
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	// Crear una nueva página en el documento PDF
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	// Establezca los márgenes para que la imagen quepa, etc.
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	// Crear un objeto de imagen
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	// Agregue la imagen a la colección de párrafos de la página.
	currpage.Paragraphs.Add(image1);

	// Establezca la propiedad IsBlackWhite en verdadero para mejorar el rendimiento
	image1.IsBlackWhite = true;
	// Establezca ImageStream en un objeto MemoryStream
	image1.ImageStream = mystream;
	// Establecer la escala de imagen deseada
	image1.ImageScale = 0.95F;
}

// Guardar el PDF
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo mejorar el rendimiento de la conversión de archivos TIFF a PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo los pasos provistos, podrá lograr conversiones más rápidas y eficientes de archivos TIFF a PDF. Obtenga resultados precisos y profesionales mientras optimiza el rendimiento de su aplicación