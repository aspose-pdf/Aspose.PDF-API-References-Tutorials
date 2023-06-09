---
title: Almacenar imagen en la colección XImage
linktitle: Almacenar imagen en la colección XImage
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para almacenar una imagen en la colección XImage usando Aspose.PDF para .NET.
type: docs
weight: 290
url: /es/net/programming-with-images/store-image-in-ximage-collection/
---

En este tutorial, lo guiaremos a través de cómo almacenar una imagen en la colección XImage usando Aspose.PDF para .NET. Siga estos pasos para realizar esta operación fácilmente.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro entorno de desarrollo instalado y configurado.
- Un conocimiento básico del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada. Puede descargarlo desde el sitio web oficial de Aspose.

## Paso 1: inicialización del documento PDF

Para comenzar, use el siguiente código para inicializar un nuevo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Inicializar el documento
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Paso 2: agregar la imagen a la colección XImage

A continuación, agregaremos la imagen a la colección XImage del documento PDF. Usa el siguiente código:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Asegúrese de proporcionar la ruta correcta al archivo de origen de la imagen.

## Paso 3: Colocación de la imagen en la página

Ahora coloquemos la imagen en la página del documento PDF. Usa el siguiente código:

```csharp
page. Contents. Add(new GSave());

// Establecer coordenadas
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//Usando el operador ConcatenateMatrix: defina cómo se debe colocar la imagen
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Esto colocará la imagen en las coordenadas especificadas en la página.

## Paso 4: Guardar el documento PDF

Finalmente, guardaremos el documento PDF actualizado. Usa el siguiente código:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Asegúrese de proporcionar la ruta y el nombre de archivo deseados para el documento PDF final.

### Ejemplo de código fuente para Store Image In XImage Collection usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inicializar documento
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Establecer coordenadas
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//Usando el operador ConcatenateMatrix (matriz concatenada): define cómo se debe colocar la imagen
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusión

¡Felicidades! Ha almacenado correctamente una imagen en la colección XImage utilizando Aspose.PDF para .NET. Ahora puede aplicar este método a sus propios proyectos para manipular y personalizar imágenes en archivos PDF.