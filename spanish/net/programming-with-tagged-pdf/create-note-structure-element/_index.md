---
title: Crear elemento de estructura de nota
linktitle: Crear elemento de estructura de nota
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para crear elementos de notas estructuradas en un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-tagged-pdf/create-note-structure-element/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo crear un elemento de estructura de notas en un documento PDF utilizando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Usando las funciones de estructura de contenido marcado de Aspose.PDF, puede agregar notas estructuradas a su documento PDF.

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

## Paso 3: Crear el documento PDF y los elementos estructurados de la nota

Use el siguiente código para crear un documento PDF y agregar elementos estructurados de notas:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Este código crea un documento PDF vacío y agrega elementos de notas estructuradas a un párrafo. Cada nota se crea utilizando los métodos proporcionados por Aspose.PDF.

## Paso 4: Guardar el documento PDF

Utilice el siguiente código para guardar el documento PDF:

```csharp
document. Save(outFile);
```

Este código guarda el documento PDF con los elementos estructurados de la nota en un archivo específico.

### Ejemplo de código fuente para Crear elemento de estructura de nota usando Aspose.PDF para .NET 

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Crear Documento PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Agregar elemento de párrafo
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Añadir elemento de nota
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Añadir elemento de nota
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Añadir elemento de nota
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//Debe lanzar una excepción: Aspose.Pdf.Tagged.TaggedException: el elemento de estructura con ID = 'note_002' ya existe
//nota3.SetId("nota_002");
// El documento resultante no cumple con PDF/UA si se usa ClearId() para el elemento de estructura de nota
//nota3.ClearId();
// Guardar documento PDF etiquetado
document.Save(outFile);
// Comprobación del cumplimiento de PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendió a crear elementos de estructura de notas en un documento PDF usando Aspose.PDF para .NET. Los elementos de notas estructuradas le permiten agregar información estructurada adicional a su documento PDF.
