---
title: Etiquetar imagen en PDF existente
linktitle: Etiquetar imagen en PDF existente
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a marcar una imagen en un PDF existente con Aspose.PDF para .NET. Guía paso a paso para agregar etiquetas a imágenes.
type: docs
weight: 210
url: /es/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
En este tutorial detallado, lo guiaremos paso a paso a través del código fuente de C# proporcionado para marcar una imagen en un PDF existente utilizando Aspose.PDF para .NET. Siga las instrucciones a continuación para comprender cómo agregar etiquetas a una imagen en un PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para utilizar Aspose.PDF para .NET. Esto incluye instalar la biblioteca Aspose.PDF y configurar su proyecto para hacer referencia a ella.

## Paso 2: Abra el documento PDF existente

En este paso, abriremos un documento PDF existente usando Aspose.PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Rutas de archivos de entrada y salida
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Abrir el documento
Document document = new Document(inFile);
```

Abrimos el documento PDF existente usando Aspose.PDF.

## Paso 3: Obtener contenido etiquetado y elemento de estructura raíz

Ahora obtendremos el contenido etiquetado del documento PDF y el elemento de estructura raíz correspondiente.

```csharp
// Obtener contenido etiquetado y elemento de estructura raíz
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Obtuvimos el contenido etiquetado del documento PDF y el elemento de estructura raíz correspondiente.

## Paso 4: Establecer el título para el documento PDF etiquetado

Ahora vamos a establecer el título para el documento PDF etiquetado.

```csharp
// Definir el título del documento PDF etiquetado
taggedContent.SetTitle("Document with images");
```

Hemos establecido el título para el documento PDF etiquetado.

## Paso 5: Asignar textos alternativos y cuadros delimitadores a la imagen

Ahora, para cada elemento de imagen, asignaremos un texto alternativo y un cuadro delimitador.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Asignar texto alternativo a la imagen
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Crear y asignar el cuadro delimitador (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Hemos asignado texto alternativo y un cuadro delimitador a cada elemento de imagen en el documento PDF.

## Paso 6: mover el elemento Span al párrafo

Ahora movamos el elemento Span al párrafo.

```csharp
// Mueva el elemento Span al párrafo (busque el span y el párrafo incorrectos en el primer TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Mover el elemento Span en el párrafo
spanElement.ChangeParentElement(paragraph);
```

Movimos el elemento Span al párrafo especificado.

## Paso 7: Guardar el documento PDF modificado

Ahora que hemos realizado los cambios necesarios, guardaremos el documento PDF modificado.

```csharp
// Guardar el documento PDF
document. Save(outFile);
```

Guardamos el documento PDF modificado en el directorio especificado.

### Código fuente de muestra para etiquetar imágenes en PDF existentes con Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Abrir documento
Document document = new Document(inFile);

// Obtiene contenido etiquetado y elemento de estructura raíz
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Establecer título para el documento PDF etiquetado
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Establecer texto alternativo para la figura
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Crear y configurar el atributo BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Mueva el elemento Span al párrafo (busque el elemento Span y el párrafo incorrectos en el primer TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Mover el elemento Span al párrafo
spanElement.ChangeParentElement(paragraph);

// Guardar documento
document.Save(outFile);

//Comprobación de la conformidad con PDF/UA para nuestro documento
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendimos a marcar una imagen en un PDF existente con Aspose.PDF para .NET. Ahora puede usar Aspose.PDF para agregar etiquetas y realizar modificaciones a las imágenes en sus documentos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el objetivo principal de este tutorial sobre cómo etiquetar imágenes en un PDF existente usando Aspose.PDF para .NET?

R: El objetivo principal de este tutorial es guiarlo a través del proceso de marcado de una imagen dentro de un documento PDF existente utilizando Aspose.PDF para .NET. El tutorial proporciona instrucciones paso a paso y ejemplos de código fuente de C# para ayudarlo a comprender cómo asignar texto alternativo y cuadros delimitadores a imágenes, mover elementos dentro del documento y agregar etiquetas a imágenes.

#### P: ¿Cuáles son los requisitos previos para seguir este tutorial sobre cómo etiquetar imágenes en un PDF usando Aspose.PDF para .NET?

R: Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para utilizar Aspose.PDF para .NET. Esto implica instalar la biblioteca Aspose.PDF y configurar su proyecto para que haga referencia a ella.

#### P: ¿Cómo puedo abrir un documento PDF existente y acceder a su contenido etiquetado usando Aspose.PDF para .NET?

R: El tutorial proporciona ejemplos de código fuente de C# que demuestran cómo abrir un documento PDF existente utilizando Aspose.PDF para .NET y acceder a su contenido etiquetado para una mayor manipulación.

#### P: ¿Cuál es el propósito de asignar texto alternativo y cuadros delimitadores a las imágenes en un documento PDF?

R: Asignar texto alternativo y cuadros delimitadores a las imágenes mejora la accesibilidad al proporcionar texto descriptivo para las imágenes y definir su diseño y posición dentro del documento. Esta información es crucial para los lectores de pantalla y otras tecnologías de asistencia.

#### P: ¿Cómo puedo configurar el título de un documento PDF etiquetado usando Aspose.PDF para .NET?

R: El tutorial incluye ejemplos de código fuente de C# que ilustran cómo establecer el título de un documento PDF etiquetado usando Aspose.PDF para .NET.

#### P: ¿En qué consiste el proceso de mover elementos dentro de un documento PDF?

R: Mover elementos dentro de un documento PDF implica cambiar el elemento principal de un elemento en particular. En este tutorial, aprenderá a mover un elemento Span a un elemento Paragraph específico dentro de una tabla.

#### P: ¿Cómo puedo guardar el documento PDF modificado después de agregar etiquetas y realizar modificaciones a las imágenes?

 A: Una vez que haya agregado etiquetas, asignado texto alternativo, establecido cuadros delimitadores y realizado modificaciones al documento PDF, puede usar los ejemplos de código fuente C# proporcionados para guardar el documento PDF modificado usando`Save()` método.

#### P: ¿Cuál es el propósito del código fuente de muestra proporcionado en el tutorial?

A: El código fuente de muestra sirve como referencia práctica para implementar el etiquetado y la manipulación de imágenes mediante Aspose.PDF para .NET. Puede utilizar este código como punto de partida y modificarlo para adaptarlo a sus requisitos específicos.

#### P: ¿Puedo aplicar estas técnicas a otros tipos de elementos en un documento PDF, no solo a imágenes?

R: Sí, las técnicas que se muestran en este tutorial se pueden adaptar para trabajar con distintos tipos de elementos dentro de un documento PDF. Puedes aplicar principios similares para etiquetar y manipular otros elementos, como texto, tablas y más.

#### P: ¿Cómo puedo validar la conformidad con PDF/UA del documento PDF modificado?

 A: El tutorial proporciona ejemplos de código fuente de C# que muestran cómo validar la conformidad con PDF/UA del documento PDF modificado mediante el uso de`Validate()` método y generar un informe XML.

#### P: ¿Qué otras características ofrece Aspose.PDF para .NET para trabajar con documentos PDF?

R: Aspose.PDF para .NET ofrece una amplia gama de funciones para trabajar con documentos PDF, incluidas la manipulación de texto, la inserción de imágenes, la creación de tablas, la gestión de campos de formulario, las firmas digitales, las anotaciones y mucho más. Consulta la documentación y los recursos oficiales para obtener más información.