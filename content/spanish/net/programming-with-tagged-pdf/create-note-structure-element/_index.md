---
title: Crear elemento de estructura de nota
linktitle: Crear elemento de estructura de nota
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para crear elementos de notas estructuradas en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-tagged-pdf/create-note-structure-element/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo crear un elemento de estructura de nota en un documento PDF usando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Utilizando las funciones de estructura de contenido marcadas de Aspose.PDF, puede agregar notas estructuradas a su documento PDF.

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

## Paso 3: Crear el documento PDF y los elementos estructurados de notas

Utilice el siguiente código para crear un documento PDF y agregar elementos estructurados de notas:

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

## Paso 4: guardar el documento PDF

Utilice el siguiente código para guardar el documento PDF:

```csharp
document. Save(outFile);
```

Este código guarda el documento PDF con los elementos estructurados de notas en un archivo específico.

### Código fuente de muestra para crear un elemento de estructura de notas usando Aspose.PDF para .NET 

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Crear documento PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Agregar elemento de párrafo
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Agregar elemento de nota
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Agregar elemento de nota
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Agregar elemento de nota
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Debe lanzar una excepción: Aspose.Pdf.Tagged.TaggedException: el elemento de estructura con ID='note_002' ya existe
//note3.SetId("nota_002");
// El documento resultante no cumple con PDF/UA si se utiliza ClearId() para el elemento de estructura de nota
//nota3.ClearId();
// Guardar documento PDF etiquetado
document.Save(outFile);
// Comprobación del cumplimiento de PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendió cómo crear elementos de estructura de notas en un documento PDF usando Aspose.PDF para .NET. Los elementos de notas estructuradas le permiten agregar información estructurada adicional a su documento PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de crear elementos de estructura de notas en un documento PDF usando Aspose.PDF para .NET?

R: Crear elementos de estructura de notas en un documento PDF usando Aspose.PDF para .NET le permite agregar notas estructuradas al contenido del documento. Estas notas pueden proporcionar contexto adicional, explicaciones o referencias a partes específicas del contenido.

#### P: ¿Cómo ayuda la biblioteca Aspose.PDF a crear elementos de estructura de notas en un documento PDF?

R: Aspose.PDF para .NET es una poderosa biblioteca que proporciona funcionalidades para crear, manipular y convertir documentos PDF mediante programación. En este tutorial, las funciones de estructura de contenido marcadas de la biblioteca se utilizan para crear elementos de notas estructuradas dentro del contenido del documento PDF.

#### P: ¿Cuáles son los requisitos previos para crear elementos de estructura de notas en un documento PDF usando Aspose.PDF para .NET?

R: Antes de comenzar, asegúrese de tener Visual Studio instalado con .NET framework y de tener referencia a la biblioteca Aspose.PDF para .NET en su proyecto.

#### P: ¿Cómo crea el código C# proporcionado elementos de estructura de notas en el contenido del documento PDF?

R: El código demuestra cómo crear un documento PDF, definir elementos estructurados de notas y agregarlos a un párrafo. Cada nota se crea utilizando métodos proporcionados por Aspose.PDF, lo que le permite incorporar notas estructuradas en el contenido.

#### P: ¿Puedo personalizar el contenido y las propiedades de los elementos de la estructura de notas que creo?

R: Sí, puede personalizar el contenido y las propiedades de los elementos de la estructura de notas utilizando los métodos y propiedades proporcionados por la biblioteca Aspose.PDF. El código muestra cómo configurar el texto y la identificación de los elementos de la nota, pero puedes personalizarlos aún más según sea necesario.

#### P: ¿Cómo se establece la relación jerárquica entre los elementos de la estructura de la nota y el contenido del documento?

 R: La relación jerárquica se establece agregando elementos de estructura de notas como hijos de otros elementos estructurados, como párrafos. En el código, los elementos de nota se agregan a un elemento de párrafo usando el`AppendChild` método.

#### P: ¿Puedo asignar identificaciones únicas a elementos de la estructura de notas?

R: Sí, puede asignar identificaciones únicas a los elementos de la estructura de notas usando el`SetId` método. El código demuestra cómo establecer los ID de los elementos de nota en valores únicos.

#### P: ¿Qué sucede si intento asignar una identificación duplicada a un elemento de la estructura de una nota?

R: Intentar asignar una identificación duplicada a un elemento de estructura de nota resultará en una excepción. El código proporcionado en el tutorial incluye un comentario que ilustra este escenario.

#### P: ¿Cómo puedo garantizar la compatibilidad con PDF/UA al crear elementos de estructura de notas?

 R: El código proporcionado en el tutorial demuestra cómo validar el cumplimiento de PDF/UA utilizando el`Validate` método. Al validar el documento con el estándar PDF/UA, puede asegurarse de que los elementos agregados de la estructura de notas cumplan con las pautas de accesibilidad.

#### P: ¿Puedo utilizar este método para agregar elementos de estructura de notas a un documento PDF existente?

R: Sí, puede modificar el método proporcionado para agregar elementos de estructura de notas a un documento PDF existente. En lugar de crear un documento nuevo, cargaría el documento existente usando Aspose.PDF y luego seguiría pasos similares para agregar elementos de nota.
