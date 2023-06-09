---
title: Convertir región de página a DOM
linktitle: Convertir región de página a DOM
second_title: Referencia de API de Aspose.PDF para .NET
description: Convierta fácilmente una región específica de una página PDF en un modelo de objeto de documento (DOM) con Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-images/convert-page-region-to-dom/
---

Esta guía lo guiará paso a paso sobre cómo convertir una región específica de una página en un modelo de objeto de documento (DOM) usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Paso 3: obtener el rectángulo de la región de la página

 En este paso, definiremos un rectángulo que representa la región específica de la página que queremos convertir a DOM. Utilizar el`Aspose.Pdf.Rectangle` class para definir las coordenadas del rectángulo.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Paso 4: Defina el área de recorte de la página

 Utilizar el`CropBox` propiedad de la`Page` objeto para establecer el cuadro de recorte de la página en el rectángulo de la región deseada.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Paso 5: guarde el documento PDF recortado en una secuencia

 En este paso, guardaremos el documento PDF recortado en una secuencia usando el`MemoryStream` clase.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Paso 6: abra el documento PDF recortado y conviértalo en una imagen

 Abra el documento PDF recortado usando el`Document` clase y convertirlo en una imagen. Usaremos una resolución de 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Paso 7: Convierte la página específica en una imagen

 Convierta la página específica en una imagen usando el`Process` metodo de la`pngDevice` objeto. Especifique la ruta de salida de la imagen.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Ejemplo de código fuente para Convertir región de página a DOM usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document( dataDir + "AddImage.pdf");
// Obtenga un rectángulo de una región de página en particular
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//Establezca el valor de CropBox según el rectángulo de la región de página deseada
document.Pages[1].CropBox = pageRect;
// Guardar documento recortado en flujo
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Abra el documento PDF recortado y conviértalo en imagen
document = new Document(ms);
// Crear objeto de resolución
Resolution resolution = new Resolution(300);
// Crear dispositivo PNG con atributos específicos
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Convierta una página en particular y guarde la imagen para transmitir
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Conclusión

¡Felicidades! Ha convertido con éxito una región específica de una página en un modelo de objeto de documento (DOM) utilizando Aspose.PDF para .NET. La imagen resultante se guarda en el directorio especificado. Ahora puede utilizar esta imagen en sus proyectos o aplicaciones.