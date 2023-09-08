---
title: Agregar elemento de estructura a elemento
linktitle: Agregar elemento de estructura a elemento
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para agregar elemento de estructura a elemento en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
En este tutorial, le proporcionaremos una guía paso a paso sobre cómo agregar un elemento de estructura a un elemento en un documento PDF usando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir documentos PDF mediante programación. Utilizando las características de estructura de contenido marcadas de Aspose.PDF, puede crear una estructura jerárquica en su documento PDF.

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

## Paso 3: Crear el documento PDF y definir los elementos estructurados

Utilice el siguiente código para crear un documento PDF y definir los elementos estructurados:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Este código crea un documento PDF vacío y agrega elementos estructurados como párrafos y espacios. Cada elemento de la estructura se crea utilizando los métodos proporcionados por Aspose.PDF.

## Paso 4: guardar el documento PDF

Utilice el siguiente código para guardar el documento PDF:

```csharp
document. Save(outFile);
```

Este código guarda el documento PDF con los elementos estructurados en un archivo específico.

### Código fuente de muestra para agregar elemento de estructura a elemento usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Creación de documento y obtención de contenido PDF etiquetado
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Configuración del título y el idioma natural del documento
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Obtención del elemento de estructura raíz (elemento de estructura del documento)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Guardar documento PDF etiquetado
document.Save(outFile);
// Comprobación del cumplimiento de PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendió cómo agregar un elemento de estructura a un elemento en un documento PDF usando Aspose.PDF para .NET. Utilizando las funciones de estructura de contenido marcadas de Aspose.PDF, puede crear una estructura jerárquica en su documento PDF, lo que facilita la administración y navegación por el contenido.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de agregar un elemento de estructura a un elemento en un documento PDF usando Aspose.PDF para .NET?

R: Agregar un elemento de estructura a un elemento en un documento PDF usando Aspose.PDF para .NET le permite crear una estructura jerárquica dentro del contenido del documento. Esta estructura jerárquica mejora la organización y navegación del contenido, facilitando la gestión y el acceso a elementos específicos.

#### P: ¿Cómo ayuda la biblioteca Aspose.PDF a agregar elementos estructurales a un documento PDF?

R: Aspose.PDF para .NET es una poderosa biblioteca que brinda capacidades para crear, manipular y convertir documentos PDF mediante programación. En este tutorial, las características de estructura de contenido marcadas de la biblioteca se aprovechan para crear y agregar elementos de estructura al contenido del documento PDF.

#### P: ¿Cuáles son los requisitos previos para agregar elementos de estructura a un documento PDF usando Aspose.PDF para .NET?

R: Antes de comenzar, asegúrese de tener Visual Studio instalado con .NET framework y de tener referencia a la biblioteca Aspose.PDF para .NET en su proyecto.

#### P: ¿Cómo crea y agrega elementos de estructura el código C# proporcionado al contenido del documento PDF?

R: El código demuestra cómo crear un documento PDF, definir un elemento de estructura raíz y agregarle varios elementos estructurados, como párrafos y espacios. Cada elemento estructurado se crea utilizando los métodos proporcionados por Aspose.PDF, lo que le permite construir una estructura jerárquica.

#### P: ¿Puedo personalizar los tipos de elementos estructurales que agrego al documento PDF?

R: Sí, puede personalizar los tipos de elementos estructurales explorando diferentes métodos proporcionados por la biblioteca Aspose.PDF. El código muestra párrafos y espacios como ejemplos, pero puedes crear y agregar otros tipos de elementos estructurados según sea necesario.

#### P: ¿Cómo defino la relación jerárquica entre los elementos de estructura agregados?

 R: La relación jerárquica entre los elementos de la estructura se define por el orden en que los agrega a sus elementos principales. En el código, las relaciones padre-hijo se establecen utilizando el`AppendChild` método.

#### P: ¿Cuáles son los beneficios de crear una estructura jerárquica en un documento PDF?

R: Crear una estructura jerárquica en un documento PDF mejora su accesibilidad, navegación y organización. Permite que las tecnologías de asistencia interpreten y transmitan mejor el contenido del documento, haciéndolo más fácil de usar para las personas con discapacidades.

#### P: ¿Cómo puedo validar la conformidad con PDF/UA después de agregar elementos de estructura?

 R: El código proporcionado en el tutorial demuestra cómo validar el cumplimiento de PDF/UA utilizando el`Validate` método. Al validar el documento con el estándar PDF/UA, puede asegurarse de que los elementos de estructura agregados cumplan con las pautas de accesibilidad.

#### P: ¿Puedo utilizar este método para agregar elementos de estructura a un documento PDF existente?

R: Sí, puede modificar el método proporcionado para agregar elementos de estructura a un documento PDF existente. En lugar de crear un documento nuevo, cargaría el documento existente usando Aspose.PDF y luego seguiría pasos similares para agregar elementos de estructura.