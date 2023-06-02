---
title: Sugerencia de fuentes de PDF a PNG
linktitle: Sugerencia de fuentes de PDF a PNG
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a PNG con sugerencias de fuente usando Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/document-conversion/pdf-to-png-font-hinting/
---

En este tutorial, lo guiaremos a través del proceso de convertir un PDF a imágenes PNG usando Aspose.PDF para .NET, mientras habilitamos las sugerencias de fuentes. La sugerencia de fuentes es una técnica que mejora la legibilidad de las fuentes pequeñas. Siguiendo los pasos a continuación, podrá convertir cada página del PDF en una imagen PNG con sugerencias de fuente.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: abrir el documento PDF de origen
En este paso, abriremos el archivo PDF de origen usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abre el documento
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: habilite las sugerencias de fuentes
Después de abrir el archivo PDF, habilitaremos las sugerencias de fuentes usando las opciones de representación. Usa el siguiente código:

```csharp
// Cree opciones de representación para habilitar las sugerencias de fuentes
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Paso 3: Convertir a imágenes PNG
Ahora vamos a convertir cada página del PDF en una imagen PNG con sugerencias de fuente. Usa el siguiente código:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Cree un objeto PNGDevice con los atributos especificados
         // Ancho, Alto, Resolución, Calidad
         // Calidad [0-100], 100 es el máximo
         // Crear un objeto de resolución
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Establecer opciones de renderizado predefinidas
         pngDevice.RenderingOptions = opts;

         // Convierta una página específica y guarde la imagen en la secuencia
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Cierra la corriente
         imageStream.Close();
     }
}
```

El código anterior convierte cada página del PDF en una imagen PNG con sugerencias de fuente y guarda cada imagen como un archivo PNG separado.

### Ejemplo de código fuente para PDF a PNGFont Sugerencias usando Aspose.Words para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Abrir documento
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Cree Aspose.Pdf.RenderingOptions para habilitar la sugerencia de fuente
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// Crear dispositivo PNG con atributos específicos
			// Ancho, Alto, Resolución, Calidad
			// Calidad [0-100], 100 es Máximo
			// Crear objeto de resolución
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Establecer opciones de renderizado predefinidas
			pngDevice.RenderingOptions = opts;

			// Convierta una página en particular y guarde la imagen para transmitir
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Cerrar transmisión
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir imágenes PDF a PNG con sugerencias de fuentes usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir cada página del PDF en una imagen PNG con sugerencias de fuente. Esta función es útil cuando desea mantener la legibilidad de las fuentes pequeñas al convertirlas a imágenes PNG.