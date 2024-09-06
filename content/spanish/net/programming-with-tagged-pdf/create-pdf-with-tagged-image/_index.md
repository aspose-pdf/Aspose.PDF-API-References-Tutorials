---
title: Crear PDF con imagen etiquetada
linktitle: Crear PDF con imagen etiquetada
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para crear un PDF con imágenes etiquetadas usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo crear un documento PDF con una imagen etiquetada utilizando Aspose.PDF para .NET. Aspose.PDF es una potente biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Con las funciones de estructura de contenido etiquetado de Aspose.PDF, puede agregar imágenes etiquetadas a su documento PDF.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio instalado con .NET framework.
2. La biblioteca Aspose.PDF para .NET.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto en Visual Studio y agregue una referencia a la biblioteca Aspose.PDF para .NET. Puede descargar la biblioteca desde el sitio web oficial de Aspose e instalarla en su equipo.

## Paso 2: Importar los espacios de nombres necesarios

En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Paso 3: Crear el documento PDF con una imagen etiquetada

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

Este código crea un documento PDF vacío y agrega una imagen etiquetada mediante los métodos proporcionados por Aspose.PDF. La imagen se especifica con texto alternativo, título y etiqueta.

## Paso 4: Guardar el documento PDF

Utilice el siguiente código para guardar el documento PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Este código guarda el documento PDF con la imagen etiquetada en un archivo específico.

### Código fuente de muestra para crear un PDF con imagen etiquetada utilizando Aspose.PDF para .NET 
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
// Añadir imagen con resolución 300 DPI (por defecto)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Guardar documento PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusión

En este tutorial, aprendió a crear un documento PDF con una imagen etiquetada mediante Aspose.PDF para .NET. Las imágenes etiquetadas agregan información adicional y estructurada a su documento PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de crear un documento PDF con una imagen etiquetada usando Aspose.PDF para .NET?

A: Crear un documento PDF con una imagen etiquetada mediante Aspose.PDF para .NET le permite agregar imágenes etiquetadas al contenido del documento. Las imágenes etiquetadas brindan información estructurada, como texto alternativo y títulos, lo que mejora la accesibilidad y la organización.

#### P: ¿Cómo ayuda la biblioteca Aspose.PDF a crear un documento PDF con una imagen etiquetada?

A: Aspose.PDF para .NET es una biblioteca sólida que ofrece funciones para crear, manipular y convertir documentos PDF mediante programación. En este tutorial, se utilizan las características de estructura de contenido etiquetado de la biblioteca para agregar una imagen etiquetada al documento PDF.

#### P: ¿Cuáles son los requisitos previos para crear un documento PDF con una imagen etiquetada utilizando Aspose.PDF para .NET?

R: Antes de comenzar, asegúrese de tener instalado Visual Studio con el marco .NET y de tener la biblioteca Aspose.PDF para .NET referenciada en su proyecto.

#### P: ¿Cómo crea el código C# proporcionado un documento PDF con una imagen etiquetada?

A: El código demuestra cómo crear un documento PDF, definir un elemento de imagen etiquetado y agregarlo al contenido del documento. La imagen etiquetada incluye texto alternativo, un título y una etiqueta mediante métodos proporcionados por Aspose.PDF.

#### P: ¿Puedo utilizar diferentes formatos de imagen para la imagen etiquetada?

R: Sí, puedes usar diferentes formatos de imagen para la imagen etiquetada, como JPEG, PNG, GIF, etc. El ejemplo de código proporcionado en el tutorial utiliza una imagen JPEG, pero puedes reemplazarlo con la ruta a un archivo de imagen en tu formato preferido.

#### P: ¿Cómo se utiliza el texto alternativo (alt text) en las imágenes etiquetadas?

 A: El texto alternativo proporciona una descripción textual de la imagen, que los lectores de pantalla leen en voz alta para usuarios con discapacidad visual. En el código proporcionado, el texto alternativo se configura mediante el`AlternativeText` propiedad de la`IllustrationElement` representando la imagen etiquetada.

####  P: ¿Cómo funciona el`SetTitle` method contribute to the PDF document's tagged image?

 A: El`SetTitle` El método establece el título del contenido etiquetado del documento PDF, lo que proporciona contexto adicional para la imagen etiquetada. Este título puede ayudar a identificar el propósito o el tema del contenido etiquetado.

#### P: ¿Puedo personalizar la etiqueta y el título de la imagen etiquetada?

 R: Sí, puedes personalizar la etiqueta y el título de la imagen etiquetada usando el`SetTag` y`Title` métodos de la`IllustrationElement`El ejemplo de código demuestra cómo establecer la etiqueta en "Fig" y el título en "Picture 1".

#### P: ¿Cómo puedo asegurarme de que la imagen etiquetada sea accesible y cumpla con los estándares de accesibilidad?

R: Al utilizar las funciones de estructura de contenido etiquetado de Aspose.PDF y proporcionar texto alternativo y otra información relevante, contribuye a la accesibilidad de la imagen etiquetada. Para garantizar el cumplimiento de los estándares de accesibilidad, es necesario seguir las mejores prácticas para el texto alternativo y la estructura del documento.

#### P: ¿Es posible agregar varias imágenes etiquetadas al mismo documento PDF utilizando técnicas similares?

 R: Sí, puedes agregar varias imágenes etiquetadas al mismo documento PDF utilizando técnicas similares. Debes crear imágenes adicionales`IllustrationElement` instancias para cada imagen etiquetada y personalizar sus propiedades según sea necesario.