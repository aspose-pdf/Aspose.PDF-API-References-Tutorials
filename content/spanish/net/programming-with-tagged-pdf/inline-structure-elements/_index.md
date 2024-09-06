---
title: Elementos de estructura en línea
linktitle: Elementos de estructura en línea
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para utilizar elementos estructurales en línea con Aspose.PDF para .NET. Organice sus archivos PDF con encabezados y párrafos.
type: docs
weight: 110
url: /es/net/programming-with-tagged-pdf/inline-structure-elements/
---
En esta guía paso a paso, le mostraremos cómo utilizar elementos de estructura en línea con Aspose.PDF para .NET. Aspose.PDF es una potente biblioteca que le permite manipular documentos PDF mediante programación. Los elementos de estructura en línea le permiten crear una estructura jerárquica en su documento PDF utilizando encabezados de diferentes niveles y párrafos.

Profundicemos en el código y aprendamos cómo usar elementos de estructura en línea con Aspose.PDF para .NET.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Biblioteca Aspose.PDF para .NET instalada.
2. Un conocimiento básico del lenguaje de programación C#.

## Paso 1: Configuración del entorno

Para comenzar, abra su entorno de desarrollo de C# y cree un nuevo proyecto. Asegúrese de haber agregado una referencia a la biblioteca Aspose.PDF para .NET en su proyecto.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Creación del documento

 El primer paso es crear un nuevo documento PDF utilizando el`Document` clase.

```csharp
// Crear el documento PDF
Document document = new Document();
```

## Paso 3: Trabajar con contenido etiquetado

Luego obtenemos el contenido etiquetado del documento para trabajar con él.

```csharp
// Obtener el contenido etiquetado del documento
ITaggedContent taggedContent = document.TaggedContent;
```

## Paso 4: Establezca el título y el idioma del documento

Ahora podemos configurar el título y el idioma del documento.

```csharp
// Definir el título y el idioma del documento
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Paso 5: Agregar elementos estructurales en línea

Ahora vamos a agregar elementos de estructura en línea como encabezados de diferentes niveles y párrafos a nuestro documento.

```csharp
// Obtener el elemento de estructura raíz
StructureElement rootElement = taggedContent.RootElement;

// Agregar encabezados de diferentes niveles
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Añadir contenido a cada encabezado
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Añadir un párrafo
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Añadir contenido al párrafo
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Aquí creamos elementos de estructura en línea, como encabezados de diferentes niveles y un párrafo, y les agregamos contenido.

## Paso 6: Guarde el documento PDF etiquetado

Finalmente, guardamos el documento PDF etiquetado.

```csharp
// Guardar el documento PDF etiquetado
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Código fuente de muestra para elementos de estructura en línea que utilizan Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear documento PDF
Document document = new Document();

// Obtenga contenido para trabajar con TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Establecer título e idioma para Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Obtener elemento de estructura raíz
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Guardar documento PDF etiquetado
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Conclusión

¡Enhorabuena! Has aprendido a utilizar elementos de estructura en línea con Aspose.PDF para .NET. Ahora puedes crear una estructura jerárquica en tu documento PDF utilizando encabezados de diferentes niveles y párrafos. Explora más funciones de Aspose.PDF para descubrir todo su potencial.

### Preguntas frecuentes

#### P: ¿Qué son los elementos de estructura en línea en un documento PDF y cómo contribuyen a crear una estructura jerárquica?

A: Los elementos de estructura en línea de un documento PDF, como los encabezados de diferentes niveles y los párrafos, se utilizan para crear una estructura jerárquica que organiza y presenta el contenido de manera estructurada. Estos elementos permiten establecer una jerarquía clara y un flujo de información dentro del documento.

#### P: ¿Cómo pueden los elementos de estructura en línea mejorar la legibilidad y la organización de un documento PDF?

A: Los elementos de estructura en línea, en particular los encabezados y los párrafos, ayudan a mejorar la legibilidad y la organización de un documento PDF al proporcionar una estructura lógica. Los encabezados indican diferentes niveles de importancia y ayudan a los lectores a navegar por el contenido, mientras que los párrafos agrupan la información relacionada.

#### P: ¿Cómo facilita Aspose.PDF para .NET el uso de elementos de estructura en línea?

A: Aspose.PDF para .NET ofrece clases y métodos para crear y manipular elementos de estructura en línea, como encabezados y párrafos. Estos elementos se pueden personalizar, organizar jerárquicamente y enriquecer con contenido para mejorar la presentación visual y la accesibilidad del documento.

####  P: ¿Cuál es el propósito de la`taggedContent` object in relation to inline structure elements?

 A: El`taggedContent` objeto, obtenido de la`TaggedContent` propiedad de un`Document`, le permite trabajar con elementos estructurados, incluidos elementos de estructura en línea. Le permite crear, personalizar y organizar encabezados y párrafos dentro del documento.

#### P: ¿Cómo ayudan los elementos de estructura en línea a crear una jerarquía de documentos clara?

A: Los elementos de la estructura en línea, como los títulos de distintos niveles, contribuyen a establecer una jerarquía clara y bien definida en el documento. Los lectores pueden identificar rápidamente los temas principales, los subtemas y el contenido relacionado, lo que hace que el documento sea más fácil de navegar y comprender.

#### P: ¿Puedo personalizar la apariencia y el formato de los elementos de estructura en línea usando Aspose.PDF para .NET?

R: Sí, puedes personalizar la apariencia y el formato de los elementos de la estructura en línea. Puedes configurar propiedades como estilos de fuente, tamaños, colores, alineación, sangría y espaciado para lograr la presentación visual deseada para los encabezados y párrafos.

#### P: ¿Cómo puedo crear y agregar encabezados de diferentes niveles a un documento PDF utilizando elementos de estructura en línea en Aspose.PDF para .NET?

 A: Puedes crear encabezados de diferentes niveles usando el`CreateHeaderElement` y luego añádalos al elemento de estructura raíz. Posteriormente, puede agregar contenido a cada elemento de encabezado utilizando el método`CreateSpanElement` Método para crear tramos de texto.

#### P: ¿Puedo utilizar elementos de estructura en línea para crear listas, viñetas u otros tipos de organización de contenido en un documento PDF?

R: Si bien los elementos de estructura en línea se utilizan principalmente para encabezados y párrafos, puede usarlos en combinación con otras características que ofrece Aspose.PDF para .NET para crear listas, viñetas, tablas y otros tipos de organización de contenido para una estructura de documento integral.

#### P: ¿Cómo contribuyen los elementos de estructura en línea a la accesibilidad del documento?

A: Los elementos de estructura en línea desempeñan un papel fundamental a la hora de mejorar la accesibilidad de los documentos. Los encabezados y párrafos correctamente estructurados proporcionan una jerarquía clara del documento que ayuda a los lectores de pantalla y otras tecnologías de asistencia a interpretar y transmitir con precisión el contenido a los usuarios con discapacidades.

#### P: ¿Puedo explorar usos más avanzados de los elementos de estructura en línea, como crear elementos interactivos o incrustar multimedia?

R: ¡Por supuesto! Si bien este tutorial se centra en la creación de encabezados y párrafos, Aspose.PDF para .NET ofrece funciones avanzadas para crear elementos interactivos, incrustar contenido multimedia, agregar hipervínculos y más. Consulte la documentación y los ejemplos de la biblioteca para profundizar en estas funciones avanzadas.