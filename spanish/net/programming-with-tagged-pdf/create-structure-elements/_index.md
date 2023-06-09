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
//Crear elementos de estructura de nivel de texto en línea
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
