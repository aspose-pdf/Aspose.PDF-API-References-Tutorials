---
title: Crear PDF con imagen etiquetada
linktitle: Crear PDF con imagen etiquetada
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para crear PDF con imagen etiquetada usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo crear un documento PDF con una imagen etiquetada usando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Usando las funciones de estructura de contenido etiquetado de Aspose.PDF, puede agregar imágenes etiquetadas a su documento PDF.

## requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos en su lugar:

1. Visual Studio instalado con .NET framework.
2. La biblioteca Aspose.PDF para .NET.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto en Visual Studio y agregue una referencia a la biblioteca Aspose.PDF para .NET. Puede descargar la biblioteca del sitio web oficial de Aspose e instalarla en su máquina.

## Paso 2: importa los espacios de nombres necesarios

En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Paso 3: Crear el documento PDF con una imagen etiquetada

Use el siguiente código para crear un documento PDF con una imagen etiquetada:

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

## Paso 4: Guardar el documento PDF

Utilice el siguiente código para guardar el documento PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Este código guarda el documento PDF con la imagen etiquetada en un archivo específico.

### Ejemplo de código fuente para Crear PDF con imagen etiquetada usando Aspose.PDF para .NET 
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

En este tutorial, aprendió a crear un documento PDF con una imagen etiquetada usando Aspose.PDF para .NET. Las imágenes etiquetadas agregan información estructurada adicional a su documento PDF.
