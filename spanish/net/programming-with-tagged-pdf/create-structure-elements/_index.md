---
title: Crear elementos de estructura
linktitle: Crear elementos de estructura
second_title: Referencia de API de Aspose.PDF para .NET
description: En este tutorial, aprenderá a usar Aspose.PDF para .NET para crear elementos estructurales en un documento PDF etiquetado.
type: docs
weight: 60
url: /es/net/programming-with-tagged-pdf/create-structure-elements/
---
El siguiente código fuente de C# usa Aspose.PDF para .NET para crear elementos de estructura. Siga los pasos a continuación para comprender cómo funciona el código.

## Paso 1: importa las bibliotecas necesarias

```csharp
using Aspose.Pdf;
```

## Paso 2: Define el directorio de tus documentos

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Asegúrese de especificar la ruta correcta a su directorio de documentos.

## Paso 3: Crea un documento PDF

```csharp
Document document = new Document();
```

Creamos un nuevo objeto Documento que representa el documento PDF.

## Paso 4: Obtenga contenido para trabajar con TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Recuperamos el contenido etiquetado del documento PDF. Esto nos permitirá manipular elementos estructurales.

## Paso 5: establecer el título y el idioma del documento

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Establecemos el título y el idioma del documento PDF etiquetado. Esto mejora la accesibilidad del documento.

## Paso 6: Crear elementos de agrupación

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Creamos diferentes elementos estructurales para agrupar contenidos en el documento PDF.

## Paso 7: Crear elementos de estructura de párrafo

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Creamos elementos estructurales a nivel de bloque para párrafos y encabezados. El ejemplo anterior muestra la creación de un encabezado de nivel 1.

## Paso 8: Crear elementos de estructura de nivel en línea

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Creamos elementos de estructura de nivel en línea para las partes del texto que aparecen dentro de un párrafo o encabezado.

## Paso 9: Crear elementos de estructura de ilustraciones

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Creamos elementos estructurales para las ilustraciones y fórmulas matemáticas presentes en el documento.

## Paso 10: Guarde el documento PDF etiquetado

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Guardamos el documento PDF etiquetado con los elementos de estructura creados.

### Ejemplo de código fuente para Crear elementos de estructura usando Aspose.PDF para .NET 

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
// Crear elementos de agrupación
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Crear elementos de estructura de nivel de bloque de texto
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Crear elementos de estructura de nivel de texto en línea
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Crear elementos de estructura de ilustración
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Los métodos están en desarrollo.
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Guardar documento PDF etiquetado
document.Save(dataDir + "StructureElements.pdf");

```

## Conclusión

En este tutorial, aprendimos a usar Aspose.PDF para .NET para crear elementos de estructura en un documento PDF etiquetado. Los elementos estructurales ayudan a mejorar la accesibilidad de los documentos y organizan el contenido de manera significativa. Ahora puede utilizar este conocimiento para crear documentos PDF estructurados y fáciles de navegar.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de crear elementos de estructura en un documento PDF utilizando Aspose.PDF para .NET?

R: La creación de elementos de estructura en un documento PDF con Aspose.PDF para .NET mejora la accesibilidad y la organización del contenido del documento. Los elementos de estructura proporcionan una estructura jerárquica que mejora la navegación, la semántica y la compatibilidad con las tecnologías de asistencia.

#### P: ¿Cómo crea el código C# proporcionado elementos de estructura en un documento PDF?

R: El ejemplo de código demuestra cómo crear varios tipos de elementos de estructura, incluidos elementos de agrupación (como partes, secciones y divisiones), elementos de nivel de bloque (como párrafos y encabezados), elementos de nivel en línea (intervalo, cita, nota ), y elementos de ilustraciones (como figuras y fórmulas). Estos elementos de estructura ayudan a organizar el contenido.

####  P: ¿Por qué es importante establecer el título y el idioma del documento mediante el`SetTitle` and `SetLanguage` methods?

 R: Establecer el título y el idioma del documento mediante el`SetTitle` y`SetLanguage`métodos mejora la accesibilidad y la semántica del documento. El título proporciona una breve descripción del propósito del documento, mientras que el atributo de idioma mejora la representación y la accesibilidad específicas del idioma.

####  P: ¿Cómo agrupar elementos, como`PartElement` and `SectElement`, contribute to the structure of the PDF document?

R: Los elementos de agrupación crean una estructura jerárquica dentro del documento PDF, lo que le permite organizar y agrupar lógicamente el contenido relacionado. Esto mejora la navegación y proporciona una estructura clara para los usuarios.

#### P: ¿Qué son los elementos de estructura de nivel de bloque y de nivel en línea, y en qué se diferencian?

R: Los elementos de estructura de nivel de bloque representan bloques de contenido más grandes, como párrafos y encabezados, mientras que los elementos de nivel en línea representan partes de texto dentro de un párrafo o encabezado, como espacios, comillas y notas. Ayudan a definir la jerarquía y las relaciones del contenido.

####  P: ¿Cómo estructuran los elementos de las ilustraciones, como`FigureElement` and `FormulaElement`, contribute to the document?

R: Los elementos de la estructura de ilustraciones le permiten agregar ilustraciones, figuras y fórmulas matemáticas al documento. Proporcionan una forma estructurada de incluir contenido visual y matemático.

#### P: ¿Puedo usar técnicas similares para crear otros tipos de elementos de estructura, como listas, tablas o anotaciones?

R: Sí, puede usar técnicas similares para crear otros tipos de elementos de estructura como listas, tablas, anotaciones, referencias y más. Aspose.PDF proporciona una amplia gama de métodos de creación de elementos de estructura.

####  P: ¿Cómo guarda el documento PDF etiquetado usando el`Save` method ensure the preservation of structure elements?

 R: El`Save` El método guarda el documento PDF junto con los elementos de estructura creados, lo que garantiza que la estructura jerárquica y semántica del documento se conserve para la accesibilidad y la navegación.

#### P: ¿Qué beneficios aportan los elementos de estructura a los documentos PDF en términos de accesibilidad y compatibilidad con las tecnologías de asistencia?

R: Los elementos de estructura mejoran la accesibilidad al proporcionar una estructura y una semántica significativas al documento. Esto permite que las tecnologías de asistencia, como los lectores de pantalla, interpreten y transmitan el contenido del documento de manera más efectiva a los usuarios con discapacidades.

#### P: ¿Cómo puedo personalizar y combinar más diferentes tipos de elementos de estructura en mis documentos PDF?

R: Puede combinar y personalizar elementos de estructura mediante el uso de métodos de creación adecuados proporcionados por Aspose.PDF. Experimente con diferentes elementos y sus propiedades para crear un documento PDF bien estructurado y organizado.