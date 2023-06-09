---
title: Ubicaciones de imágenes
linktitle: Ubicaciones de imágenes
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para colocar imágenes en un documento PDF.
type: docs
weight: 170
url: /es/net/programming-with-images/image-placements/
---

En este tutorial, usaremos la biblioteca Aspose.PDF para .NET para trabajar con documentos PDF y realizar operaciones en imágenes. Cargaremos un documento PDF, extraeremos la información de ubicación de la imagen y recuperaremos las imágenes con sus dimensiones visibles.

## Paso 1: Configuración del entorno
Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con lo siguiente:
- Aspose.PDF para .NET instalado en su máquina.
- Proyecto AC# listo para ser utilizado.

## Paso 2: Cargar el documento PDF
Para empezar, necesitamos cargar el documento PDF que queremos procesar. Asegúrese de tener la ruta correcta al directorio que contiene el documento PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el documento PDF de origen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su directorio de documentos que contiene el archivo PDF.

## Paso 3: extraiga la información de ubicación de las imágenes
 Ahora que hemos cargado el documento PDF, podemos extraer la información de ubicación de las imágenes. Usaremos`ImagePlacementAbsorber`para absorber ubicaciones de imágenes de la primera página del documento.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Cargar el contenido de la primera página
doc.Pages[1].Accept(abs);
```

Ahora hemos extraído la información de ubicación de la imagen de la primera página del documento.

## Paso 4: Recuperación de imágenes con dimensiones visibles
Ahora recuperaremos las imágenes con sus dimensiones visibles de la información de ubicación que extrajimos anteriormente.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Obtener propiedades de imagen
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Recuperar la imagen con dimensiones visibles
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Obtener la imagen de los recursos.
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Crear una imagen con dimensiones reales
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

En este bucle, recuperamos las propiedades de cada imagen, como el ancho, la altura, las coordenadas X e Y de la esquina inferior izquierda y la resolución horizontal y vertical. Luego recuperamos cada imagen con sus dimensiones visibles utilizando la información de ubicación.

### Ejemplo de código fuente para ubicaciones de imágenes con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargue el documento PDF de origen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Cargar el contenido de la primera página
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Obtener propiedades de imagen
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Recuperar imagen con dimensiones visibles
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Recuperar imagen de recursos
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Crear mapa de bits con dimensiones reales
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Conclusión
¡Felicidades! Ahora ha aprendido a usar Aspose.PDF para .NET para realizar colocaciones de imágenes en un documento PDF. Explicamos el código fuente de C# proporcionado, que le permite cargar un documento PDF, extraer la información de ubicación de las imágenes y recuperar las imágenes con sus dimensiones visibles. Siéntase libre de experimentar más con Aspose.PDF para explorar sus muchas otras características.