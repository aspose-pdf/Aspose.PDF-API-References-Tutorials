---
title: Convertir flujo de imágenes a PDF
linktitle: Convertir flujo de imágenes a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Convierta fácilmente un flujo de imágenes en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-images/convert-image-stream-to-pdf/
---

Esta guía lo guiará paso a paso sobre cómo convertir un flujo de imágenes en un archivo PDF usando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su imagen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear una instancia de un objeto de documento

 En este paso, instanciaremos un`Document` objeto usando el constructor vacío del`Aspose.Pdf.Document` clase.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Paso 3: agregue una página al documento PDF

 Agregue una página al documento PDF usando el`Add` metodo de la`Pages` objeto de`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Paso 4: Leer el flujo de imágenes

 En este paso crearemos un`FileStream` objeto para leer el archivo de imagen de la secuencia.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Paso 5: lee la imagen en una matriz de bytes

 Lea la imagen de la transmisión y guárdela en una matriz de bytes usando el`Read` metodo de la`fs` objeto.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Paso 6: Cree un objeto MemoryStream a partir de la matriz de bytes

 Crear un`MemoryStream` objeto de la matriz de bytes que contiene la imagen.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Paso 7: crea un objeto de imagen

 En este paso, crearemos un`Image` objeto usando el`Aspose.Pdf.Image` clase. Especifique el flujo de la imagen usando el`ImageStream` propiedad y pasar la`ms` objeto que creamos anteriormente.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Paso 8: agregue el objeto de imagen a la colección de párrafos

 Añade el`imageht` objetar a la`Paragraphs` colección de la`sec` sección.

```csharp
sec.Paragraphs.Add(imageht);
```

## Paso 9: Guarde el documento PDF

 Guarde el documento PDF usando el`Save` metodo de la`pdf1` objeto. Especifique la ruta de salida del archivo PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Paso 10: cierre el objeto MemoryStream

 Cierra el`ms` objeto usando el`Close` método para liberar los recursos.

```csharp
ms. Close();
```

### Ejemplo de código fuente para Convertir flujo de imágenes a PDF usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Crea una instancia de documento llamando a su constructor vacío
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Añadir una página en el documento pdf
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Cree un objeto FileStream para leer el archivo de imagen
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Leer la imagen en la matriz de bytes
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Cree un objeto MemoryStream a partir de una matriz de bytes de imagen
MemoryStream ms = new MemoryStream(data);
// Crear un objeto de imagen
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Especifique la fuente de la imagen como MemoryStream
imageht.ImageStream = ms;
// Agregue un objeto de imagen a la colección de párrafos de la sección
sec.Paragraphs.Add(imageht);
// Guardar el PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Cierre el objeto MemoryStream
ms.Close();
```

## Conclusión

¡Felicidades! Ha convertido con éxito un flujo de imágenes en un archivo PDF utilizando Aspose.PDF para .NET. El archivo PDF generado se guarda en el directorio especificado. Ahora puede utilizar este archivo PDF en sus proyectos o aplicaciones.