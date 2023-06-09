---
title: Página a PNG
linktitle: Página a PNG
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir una página a formato PNG utilizando Aspose.PDF para .NET.
type: docs
weight: 220
url: /es/net/programming-with-images/page-to-png/
---

En este tutorial, lo guiaremos a través de cómo convertir una página a formato PNG usando Aspose.PDF para .NET. Siga estos pasos para realizar esta operación fácilmente.

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
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
```

Asegúrese de proporcionar la ruta correcta a su documento PDF.

## Paso 2: Convierte la página a PNG

A continuación, convertiremos una página específica del documento PDF a formato PNG. Usa el siguiente código:

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
// Crear un objeto de resolución
Resolution resolution = new Resolution(300);
// Cree un dispositivo PNG con los atributos especificados (ancho, alto, resolución)
PngDevice pngDevice = new PngDevice(resolution);
// Convierta una página específica y guarde la imagen en la secuencia
pngDevice.Process(pdfDocument.Pages[1], imageStream);
// Cierra la corriente
imageStream.Close();
}
```

Asegúrese de proporcionar la ruta y el nombre de archivo deseados para la imagen PNG de salida.

### Ejemplo de código fuente para Page To PNG usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
	// Crear objeto de resolución
	Resolution resolution = new Resolution(300);
	// Crear dispositivo PNG con atributos específicos (ancho, alto, resolución)
	PngDevice pngDevice = new PngDevice(resolution);
	// Convierta una página en particular y guarde la imagen para transmitir
	pngDevice.Process(pdfDocument.Pages[1], imageStream);
	// Cerrar transmisión
	imageStream.Close();
}
```

## Conclusión

¡Felicidades! Ha convertido con éxito una página a formato PNG utilizando Aspose.PDF para .NET. Ahora puede aplicar este método a sus propios proyectos para extraer páginas específicas de archivos PDF y guardarlas como imágenes PNG.