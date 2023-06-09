---
title: Establecer nombre de fuente predeterminado
linktitle: Establecer nombre de fuente predeterminado
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para configurar el nombre de fuente predeterminado en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 270
url: /es/net/document-conversion/set-default-font-name/
---

En este tutorial, le mostraremos cómo configurar el nombre de fuente predeterminado en un archivo PDF usando Aspose.PDF para .NET. A veces, cuando extrae imágenes de un archivo PDF, es posible que encuentre problemas de fuentes faltantes. Al especificar un nombre de fuente predeterminado, puede asegurarse de que el texto extraído se muestre correctamente. Siga los pasos a continuación para establecer el nombre de fuente predeterminado en un archivo PDF.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargar el documento PDF
 El primer paso es cargar el documento PDF en un`Document` objeto. Usa el siguiente código:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Código para agregar
}
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: establecer el nombre de fuente predeterminado
 A continuación, estableceremos el nombre de fuente predeterminado usando el`DefaultFontName` opción de la`RenderingOptions` objeto. Usa el siguiente código:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Código para agregar
     }
}
```

 Asegúrese de reemplazar`"Arial"` con el nombre de fuente deseado.

## Paso 3: Extracción de imágenes
A continuación, extraeremos la imagen de la página especificada del documento PDF. Usa el siguiente código:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Asegúrese de especificar el número de página correcto en`pdfDocument.Pages[1]`.

### Ejemplo de código fuente para establecer el nombre de fuente predeterminado usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Conclusión
En este tutorial, aprendimos cómo establecer el nombre de fuente predeterminado en un archivo PDF usando Aspose.PDF para .NET. Al especificar un nombre de fuente predeterminado, puede asegurarse de que el texto extraído se muestre correctamente. Utilice este método para resolver problemas de fuentes faltantes al extraer imágenes de archivos PDF.