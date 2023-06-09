---
title: Identificar Imágenes
linktitle: Identificar Imágenes
second_title: Referencia de API de Aspose.PDF para .NET
description: Identifique fácilmente imágenes en un archivo PDF y determine su tipo de color con Aspose.PDF para .NET.
type: docs
weight: 150
url: /es/net/programming-with-images/identify-images/
---

Esta guía lo guiará paso a paso sobre cómo identificar imágenes en un archivo PDF usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Asegúrese de establecer el directorio de documentos correcto. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Inicializar los contadores

En este paso, inicializaremos los contadores para imágenes en escala de grises e imágenes RGB.

```csharp
int grayscaled = 0; // Contador de imágenes en escala de grises
int rdg = 0; // Contador de imágenes RGB
```

## Paso 3: Abra el documento PDF

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## Paso 4: Examinar las páginas del documento

En este paso, recorreremos todas las páginas del documento PDF e identificaremos las imágenes en cada página.

```csharp
foreach(Page page in document.Pages)
{
```

## Paso 5: recuperar ubicaciones de imágenes

 En este paso, usaremos`ImagePlacementAbsorber` para recuperar las ubicaciones de las imágenes en cada página.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## Paso 6: Cuente las imágenes e identifique su tipo de color

En este paso, contaremos la cantidad de imágenes en cada página e identificaremos su tipo de color (escala de grises o RGB).

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### Ejemplo de código fuente para identificar imágenes usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Contador de imágenes en escala de grises
int grayscaled = 0;
// Contador de imágenes RGB
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// Obtenga el recuento de imágenes en una página específica
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Documento.Páginas[29].Aceptar(abs);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## Conclusión

¡Felicidades! Ha identificado con éxito imágenes en un PDF utilizando Aspose.PDF para .NET. Se contaron las imágenes y se identificó su tipo de color (escala de grises o RGB). Ahora puede utilizar esta información para sus necesidades específicas.