---
title: Buscar y obtener imágenes
linktitle: Buscar y obtener imágenes
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para buscar y obtener imágenes en un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 260
url: /es/net/programming-with-images/search-and-get-images/
---

En este tutorial, lo guiaremos a través de cómo buscar y obtener imágenes en un documento PDF usando Aspose.PDF para .NET. Siga estos pasos para realizar esta operación fácilmente.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Asegúrese de proporcionar la ruta correcta a su documento PDF.

## Paso 2: Búsqueda de ubicaciones de imágenes

Para buscar las ubicaciones de las imágenes en el documento PDF, use el siguiente código:

```csharp
// Cree un objeto ImagePlacementAbsorber para buscar ubicaciones de imágenes
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Aceptar el absorbedor para todas las páginas del documento
doc.Pages.Accept(abs);
```

Esto recopilará las ubicaciones de las imágenes en el absorbedor.

## Paso 3: busque ubicaciones de imágenes y obtenga imágenes y sus propiedades

A continuación, exploraremos las ubicaciones de las imágenes recopiladas y obtendremos las imágenes y sus propiedades. Usa el siguiente código:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //Obtenga la imagen usando el objeto ImagePlacement
     XImage image = imagePlacement.Image;

     // Mostrar las propiedades de ubicación de la imagen
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Esto buscará todas las ubicaciones de imágenes, obtendrá imágenes coincidentes y mostrará sus propiedades.

### Ejemplo de código fuente para buscar y obtener imágenes con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Cree un objeto ImagePlacementAbsorber para realizar una búsqueda de ubicación de imágenes
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Aceptar el absorbedor para todas las páginas.
doc.Pages.Accept(abs);
// Recorra todos los ImagePlacements, obtenga la imagen y las Propiedades de ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Obtenga la imagen usando el objeto ImagePlacement
	XImage image = imagePlacement.Image;
	// Mostrar propiedades de ubicación de imagen para todas las ubicaciones
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Conclusión

¡Felicidades! Ha buscado y obtenido con éxito imágenes en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede aplicar este método a sus propios proyectos para extraer imágenes y obtener sus propiedades de archivos PDF.