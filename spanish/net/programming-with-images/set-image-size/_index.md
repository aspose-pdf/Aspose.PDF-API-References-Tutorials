---
title: Establecer tamaño de imagen
linktitle: Establecer tamaño de imagen
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para configurar el tamaño de una imagen en un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 270
url: /es/net/programming-with-images/set-image-size/
---

En este tutorial, lo guiaremos a través de cómo configurar el tamaño de una imagen en un documento PDF usando Aspose.PDF para .NET. Siga estos pasos para realizar esta operación fácilmente.

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

// Ruta al archivo fuente de la imagen
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
//agregar página a la colección de páginas del archivo PDF
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