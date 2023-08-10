---
title: Establecer tamaño de imagen en archivo PDF
linktitle: Establecer tamaño de imagen en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para configurar el tamaño de una imagen en un archivo PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 270
url: /es/net/programming-with-images/set-image-size/
---
En este tutorial, lo guiaremos a través de cómo configurar el tamaño de una imagen en un archivo PDF usando Aspose.PDF para .NET. Siga estos pasos para realizar esta operación fácilmente.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro entorno de desarrollo instalado y configurado.
- Un conocimiento básico del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada. Puede descargarlo desde el sitio web oficial de Aspose.

## Paso 1: Creación del documento PDF

Para comenzar, use el siguiente código para crear un nuevo documento PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Crear una instancia de un objeto de documento
Document doc = new Document();

// Agregar una página a la colección de páginas del archivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Paso 2: imagen añadida

A continuación, agregaremos una imagen a la página del documento PDF. Usa el siguiente código:

```csharp
// Crear una instancia de imagen
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Establecer el ancho y alto de la imagen en puntos
img. FixWidth = 100;
img. FixHeight = 100;

// Establecer el tipo de imagen en desconocido (Desconocido)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Ruta al archivo fuente de la imagen
img.File = dataDir + "aspose-logo.jpg";

// Agregue la imagen a la colección de párrafos de la página.
page.Paragraphs.Add(img);
```

Asegúrese de proporcionar la ruta correcta al archivo de origen de la imagen.

## Paso 3: Configuración de las propiedades de la página

Finalmente, estableceremos las propiedades de la página, incluyendo su ancho y alto. Usa el siguiente código:

```csharp
// Establecer propiedades de página
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Ejemplo de código fuente para establecer el tamaño de la imagen con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto de documento
Document doc = new Document();
// agregar página a la colección de páginas del archivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crear una instancia de imagen
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Establecer el ancho y la altura de la imagen en puntos
img.FixWidth = 100;
img.FixHeight = 100;
// Establecer tipo de imagen como SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Ruta del archivo fuente
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Establecer propiedades de página
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// guardar el archivo PDF resultante
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ha establecido con éxito el tamaño de una imagen en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede aplicar este método a sus propios proyectos para ajustar el tamaño de las imágenes en archivos PDF.

### Preguntas frecuentes para establecer el tamaño de la imagen en un archivo PDF

#### P: ¿Cuál es el propósito de configurar el tamaño de una imagen en un documento PDF usando Aspose.PDF para .NET?

R: El propósito de configurar el tamaño de una imagen en un documento PDF es controlar las dimensiones de la imagen cuando se agrega al PDF. Esto le permite ajustar la apariencia y el diseño de las imágenes dentro de sus archivos PDF.

#### P: ¿Cómo funciona el proceso de establecer el tamaño de una imagen en un documento PDF?

 R: El proceso consiste en crear un`Aspose.Pdf.Image` ejemplo, especificando su ancho y alto usando el`FixWidth` y`FixHeight` propiedades y luego agregar la imagen al documento PDF. Además, puede establecer las dimensiones de la página en sí para acomodar la imagen.

#### P: ¿Puedo establecer el tamaño de una imagen en un porcentaje específico de las dimensiones de la página?

R: El código proporcionado establece el ancho y el alto absolutos de la imagen en puntos. Si desea establecer el tamaño de una imagen en función de un porcentaje de las dimensiones de la página, deberá calcular las dimensiones en consecuencia y ajustar el código en consecuencia.

####  P: ¿Cuál es el significado de la`FileType` property when adding an image to the PDF document?

 R: El`FileType`La propiedad especifica el tipo de imagen que se agrega al documento PDF. En el código proporcionado, el valor`Unknown` indica que se desconoce el tipo de imagen y Aspose.PDF intentará determinar el tipo de imagen en función de la extensión del archivo.

#### P: ¿Puedo agregar varias imágenes a una sola página usando este método?

 R: Sí, puede agregar varias imágenes a una sola página creando varias`Aspose.Pdf.Image` instancias y agregarlas a la colección de párrafos de la página. Asegúrese de ajustar la posición y el diseño de las imágenes según sea necesario.

#### P: ¿Cómo puedo controlar la ubicación y la alineación de la imagen agregada en la página?

 R: La ubicación y la alineación de la imagen agregada se pueden controlar ajustando las coordenadas y el diseño de la imagen usando propiedades como`img.Left`, `img.Top`y propiedades de formato de párrafo.

####  P: ¿Cuál es el propósito de configurar las propiedades de la página usando`page.PageInfo.Width` and `page.PageInfo.Height`?

R: Establecer las propiedades de la página le permite definir las dimensiones de la página misma. Esto asegura que las dimensiones de la página acomoden la imagen agregada y cualquier otro contenido que pueda tener en la página.

#### P: ¿Puedo configurar diferentes tamaños para diferentes imágenes dentro del mismo documento PDF?

 R: Sí, puede configurar diferentes tamaños para diferentes imágenes creando`Aspose.Pdf.Image` instancias y ajustando el`FixWidth`, `FixHeight`y propiedades de ubicación para cada imagen.

#### P: ¿Cómo puedo integrar este método en mis propios proyectos para establecer tamaños de imagen en archivos PDF?

R: Para integrar este método en sus proyectos, siga los pasos descritos y modifique el código según sea necesario. Puede usar este método para agregar imágenes de tamaños específicos a sus documentos PDF según los requisitos de su aplicación.