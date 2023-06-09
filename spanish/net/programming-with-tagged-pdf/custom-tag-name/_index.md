---
title: Nombre de etiqueta personalizada
linktitle: Nombre de etiqueta personalizada
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para usar un nombre de etiqueta personalizado con Aspose.PDF para .NET. Mejore la estructura de sus archivos PDF con etiquetas personalizadas.
type: docs
weight: 90
url: /es/net/programming-with-tagged-pdf/custom-tag-name/
---
En esta guía paso a paso, lo guiaremos a través de cómo usar un nombre de etiqueta personalizado con Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite manipular documentos PDF mediante programación. El uso de etiquetas personalizadas le permite agregar información estructural específica a su documento PDF, lo que facilita su uso y acceso.

Profundicemos en el código y aprendamos a usar un nombre de etiqueta personalizado con Aspose.PDF para .NET.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Biblioteca Aspose.PDF para .NET instalada.
2. Un conocimiento básico del lenguaje de programación C#.

## Paso 1: Configuración del entorno

Para comenzar, abra su entorno de desarrollo C# y cree un nuevo proyecto. Asegúrese de haber agregado una referencia a la biblioteca Aspose.PDF para .NET en su proyecto.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear el documento

 El primer paso es crear un nuevo documento PDF usando el`Document` clase.

```csharp
// Crear el documento PDF
Document document = new Document();
```

## Paso 3: Trabajar con contenido etiquetado

Luego obtenemos el contenido etiquetado del documento para trabajar.

```csharp
// Obtener el contenido etiquetado del documento
ITaggedContent taggedContent = document.TaggedContent;
```

## Paso 4: establecer el título y el idioma del documento

Ahora podemos configurar el título del documento y el idioma.

```csharp
// Definir el título del documento y el idioma
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Paso 5: crear elementos de estructura lógica

Ahora vamos a crear algunos elementos de estructura lógica para organizar nuestro contenido.

```csharp
// Crear elementos de estructura lógica
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Aquí creamos elementos de párrafo y elementos de extensión para nuestro contenido, y les asignamos etiquetas personalizadas.

## Paso 6: Guarde el documento PDF etiquetado

Finalmente, guardamos el documento PDF etiquetado.

```csharp
// Guarde el documento PDF etiquetado
document.Save(dataDir + "CustomTag.pdf");
```

### Ejemplo de código fuente para el nombre de la etiqueta personalizada usando Aspose.PDF para .NET 
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

// Crear elementos de estructura lógica
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

// Guardar documento PDF etiquetado
document.Save(dataDir + "CustomTag.pdf");

```

## Conclusión

¡Felicidades! Aprendió a usar un nombre de etiqueta personalizado con Aspose.PDF para .NET. Ahora puede agregar información estructural específica a su documento PDF usando etiquetas personalizadas. Explore más características de Aspose.PDF para descubrir todo su potencial.
