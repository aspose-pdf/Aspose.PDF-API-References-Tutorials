---
title: Crear PDF con texto etiquetado
linktitle: Crear PDF con texto etiquetado
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para crear un PDF con texto etiquetado usando Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo crear un documento PDF con texto etiquetado usando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Usando las funciones de estructura de contenido etiquetado de Aspose.PDF, puede agregar texto etiquetado a su documento PDF.

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

## Paso 3: Crear el documento PDF con texto etiquetado

Use el siguiente código para crear un documento PDF con texto etiquetado:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// Añadir más párrafos aquí

// Guardar el documento PDF
document.Save(dataDir + "PDFwithTagText.pdf");
```

Este código crea un documento PDF vacío y agrega texto etiquetado utilizando los métodos proporcionados por Aspose.PDF. Puede agregar otros elementos de texto etiquetados, como encabezados y párrafos, utilizando los métodos apropiados.

### Ejemplo de código fuente para Crear PDF con texto etiquetado usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear Documento PDF
Document document = new Document();
// Obtenga contenido para trabajar con TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Establecer título e idioma para Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Crear elementos de estructura de nivel de bloque de texto
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// Guardar documento PDF
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## Conclusión

En este tutorial, aprendió a crear un documento PDF con texto etiquetado usando Aspose.PDF para .NET. Las funciones de estructura de contenido marcado de Aspose.PDF le permiten estructurar y organizar su texto para una mejor accesibilidad y semántica.
