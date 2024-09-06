---
title: Crear elemento de estructura de nota
linktitle: Crear elemento de estructura de nota
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para crear elementos de notas estructurados en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-tagged-pdf/create-note-structure-element/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo crear un elemento de estructura de notas en un documento PDF utilizando Aspose.PDF para .NET. Aspose.PDF es una potente biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Con las funciones de estructura de contenido marcado de Aspose.PDF, puede agregar notas estructuradas a su documento PDF.

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

## Paso 3: Creación del documento PDF y elementos estructurados de notas

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

Este código crea un documento PDF vacío y agrega elementos de nota estructurada a un párrafo. Cada nota se crea utilizando los métodos proporcionados por Aspose.PDF.

## Paso 4: Guardar el documento PDF

Utilice el siguiente código para guardar el documento PDF:

```csharp
document. Save(outFile);
```

Este código guarda el documento PDF con los elementos estructurados de la nota en un archivo específico.

### Código fuente de muestra para crear un elemento de estructura de nota con Aspose.PDF para .NET 

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
// Se debe lanzar una excepción - Aspose.Pdf.Tagged.TaggedException: El elemento de estructura con ID='note_002' ya existe
//nota3.SetId("nota_002");
// El documento resultante no cumple con los requisitos de PDF/UA si se utiliza ClearId() para el elemento de estructura de nota
//nota3.ClearId();
// Guardar documento PDF etiquetado
document.Save(outFile);
// Comprobación de la conformidad con PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendió a crear elementos de estructura de notas en un documento PDF con Aspose.PDF para .NET. Los elementos de notas estructuradas le permiten agregar información estructurada adicional a su documento PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de crear elementos de estructura de notas en un documento PDF utilizando Aspose.PDF para .NET?

A: La creación de elementos de estructura de notas en un documento PDF mediante Aspose.PDF para .NET le permite agregar notas estructuradas al contenido del documento. Estas notas pueden proporcionar contexto adicional, explicaciones o referencias a partes específicas del contenido.

#### P: ¿Cómo ayuda la biblioteca Aspose.PDF a crear elementos de estructura de notas en un documento PDF?

A: Aspose.PDF para .NET es una potente biblioteca que ofrece funciones para crear, manipular y convertir documentos PDF mediante programación. En este tutorial, se utilizan las características de estructura de contenido marcado de la biblioteca para crear elementos de nota estructurados dentro del contenido del documento PDF.

#### P: ¿Cuáles son los requisitos previos para crear elementos de estructura de notas en un documento PDF utilizando Aspose.PDF para .NET?

R: Antes de comenzar, asegúrese de tener instalado Visual Studio con el marco .NET y de tener la biblioteca Aspose.PDF para .NET referenciada en su proyecto.

#### P: ¿Cómo crea el código C# proporcionado elementos de estructura de notas en el contenido del documento PDF?

A: El código demuestra cómo crear un documento PDF, definir elementos estructurados de notas y agregarlos a un párrafo. Cada nota se crea utilizando métodos proporcionados por Aspose.PDF, lo que le permite incorporar notas estructuradas al contenido.

#### P: ¿Puedo personalizar el contenido y las propiedades de los elementos de estructura de notas que creo?

R: Sí, puedes personalizar el contenido y las propiedades de los elementos de la estructura de notas mediante los métodos y las propiedades que ofrece la biblioteca Aspose.PDF. El código muestra cómo configurar el texto y el ID de los elementos de notas, pero puedes personalizarlos aún más según sea necesario.

#### P: ¿Cómo se establece la relación jerárquica entre los elementos de la estructura de la nota y el contenido del documento?

 A: La relación jerárquica se establece agregando elementos de estructura de notas como elementos secundarios de otros elementos estructurados, como párrafos. En el código, los elementos de notas se agregan a un elemento de párrafo utilizando el`AppendChild` método.

#### P: ¿Puedo asignar identificadores únicos a los elementos de la estructura de notas?

R: Sí, puede asignar identificaciones únicas a los elementos de la estructura de notas utilizando el`SetId` método. El código demuestra cómo establecer los identificadores de los elementos de nota en valores únicos.

#### P: ¿Qué sucede si intento asignar una ID duplicada a un elemento de estructura de nota?

A: Intentar asignar un ID duplicado a un elemento de la estructura de una nota generará una excepción. El código proporcionado en el tutorial incluye un comentario que ilustra esta situación.

#### P: ¿Cómo puedo garantizar la conformidad con PDF/UA al crear elementos de estructura de notas?

 A: El código proporcionado en el tutorial demuestra cómo validar la conformidad con PDF/UA utilizando el`Validate` Método. Al validar el documento con el estándar PDF/UA, puede asegurarse de que los elementos de estructura de notas agregados cumplan con las pautas de accesibilidad.

#### P: ¿Puedo utilizar este enfoque para agregar elementos de estructura de notas a un documento PDF existente?

R: Sí, puede modificar el enfoque proporcionado para agregar elementos de estructura de notas a un documento PDF existente. En lugar de crear un documento nuevo, debe cargar el documento existente mediante Aspose.PDF y luego seguir pasos similares para agregar elementos de notas.
