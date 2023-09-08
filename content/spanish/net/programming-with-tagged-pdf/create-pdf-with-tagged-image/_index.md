---
title: Crear PDF con imagen etiquetada
linktitle: Crear PDF con imagen etiquetada
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para crear PDF con imagen etiquetada usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo crear un documento PDF con una imagen etiquetada usando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Utilizando las funciones de estructura de contenido etiquetado de Aspose.PDF, puede agregar imágenes etiquetadas a su documento PDF.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

1. Visual Studio instalado con .NET framework.
2. La biblioteca Aspose.PDF para .NET.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto en Visual Studio y agregue una referencia a la biblioteca Aspose.PDF para .NET. Puede descargar la biblioteca desde el sitio web oficial de Aspose e instalarla en su máquina.

## Paso 2: importe los espacios de nombres necesarios

En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Paso 3: crear el documento PDF con una imagen etiquetada

Utilice el siguiente código para crear un documento PDF con una imagen etiquetada:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Este código crea un documento PDF vacío y agrega una imagen etiquetada utilizando los métodos proporcionados por Aspose.PDF. La imagen se especifica con texto alternativo, título y etiqueta.

## Paso 4: guardar el documento PDF

Utilice el siguiente código para guardar el documento PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Este código guarda el documento PDF con la imagen etiquetada en un archivo específico.

### Código fuente de muestra para crear PDF con imagen etiquetada usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Agregar imagen con resolución 300 DPI (por defecto)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Guardar documento PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusión

En este tutorial, aprendió cómo crear un documento PDF con una imagen etiquetada usando Aspose.PDF para .NET. Las imágenes etiquetadas agregan información estructurada adicional a su documento PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de crear un documento PDF con una imagen etiquetada usando Aspose.PDF para .NET?

R: Crear un documento PDF con una imagen etiquetada usando Aspose.PDF para .NET le permite agregar imágenes etiquetadas al contenido del documento. Las imágenes etiquetadas proporcionan información estructurada, como texto alternativo y títulos, lo que mejora la accesibilidad y la organización.

#### P: ¿Cómo ayuda la biblioteca Aspose.PDF a crear un documento PDF con una imagen etiquetada?

R: Aspose.PDF para .NET es una biblioteca sólida que proporciona funcionalidades para crear, manipular y convertir documentos PDF mediante programación. En este tutorial, las funciones de estructura de contenido etiquetado de la biblioteca se utilizan para agregar una imagen etiquetada al documento PDF.

#### P: ¿Cuáles son los requisitos previos para crear un documento PDF con una imagen etiquetada usando Aspose.PDF para .NET?

R: Antes de comenzar, asegúrese de tener Visual Studio instalado con .NET framework y de tener referencia a la biblioteca Aspose.PDF para .NET en su proyecto.

#### P: ¿Cómo crea el código C# proporcionado un documento PDF con una imagen etiquetada?

R: El código demuestra cómo crear un documento PDF, definir un elemento de imagen etiquetado y agregarlo al contenido del documento. La imagen etiquetada incluye texto alternativo, un título y una etiqueta utilizando los métodos proporcionados por Aspose.PDF.

#### P: ¿Puedo utilizar diferentes formatos de imagen para la imagen etiquetada?

R: Sí, puedes usar diferentes formatos de imagen para la imagen etiquetada, como JPEG, PNG, GIF, etc. El ejemplo de código proporcionado en el tutorial usa una imagen JPEG, pero puedes reemplazarla con la ruta a un archivo de imagen en su formato preferido.

#### P: ¿Cómo se utiliza el texto alternativo (alt text) en las imágenes etiquetadas?

 R: El texto alternativo proporciona una descripción textual de la imagen, que los lectores de pantalla para usuarios con discapacidad visual leen en voz alta. En el código proporcionado, el texto alternativo se establece usando el`AlternativeText` propiedad de la`IllustrationElement` que representa la imagen etiquetada.

####  P: ¿Cómo funciona el`SetTitle` method contribute to the PDF document's tagged image?

 R: El`SetTitle` El método establece el título del contenido etiquetado del documento PDF, proporcionando contexto adicional para la imagen etiquetada. Este título puede ayudar a identificar el propósito o el tema del contenido etiquetado.

#### P: ¿Puedo personalizar la etiqueta y el título de la imagen etiquetada?

 R: Sí, puedes personalizar la etiqueta y el título de la imagen etiquetada usando el`SetTag` y`Title` métodos de la`IllustrationElement`. El ejemplo de código muestra cómo configurar la etiqueta en "Fig" y el título en "Imagen 1".

#### P: ¿Cómo puedo garantizar que la imagen etiquetada sea accesible y cumpla con los estándares de accesibilidad?

R: Al utilizar las funciones de estructura de contenido etiquetado de Aspose.PDF y proporcionar texto alternativo y otra información relevante, contribuye a la accesibilidad de la imagen etiquetada. Garantizar el cumplimiento de los estándares de accesibilidad implica seguir las mejores prácticas para el texto alternativo y la estructura de los documentos.

#### P: ¿Es posible agregar varias imágenes etiquetadas al mismo documento PDF utilizando técnicas similares?

 R: Sí, puedes agregar varias imágenes etiquetadas al mismo documento PDF utilizando técnicas similares. Crearías adicionales`IllustrationElement` instancias para cada imagen etiquetada y personalizar sus propiedades según sea necesario.