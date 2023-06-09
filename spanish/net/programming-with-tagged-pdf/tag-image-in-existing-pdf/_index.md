---
title: Etiquetar imagen en PDF existente
linktitle: Etiquetar imagen en PDF existente
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a marcar una imagen en un PDF existente con Aspose.PDF para .NET. Una guía paso a paso para agregar etiquetas a las imágenes.
type: docs
weight: 210
url: /es/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
En este tutorial detallado, lo guiaremos a través del código fuente de C# proporcionado paso a paso para marcar una imagen en un PDF existente usando Aspose.PDF para .NET. Siga las instrucciones a continuación para comprender cómo agregar etiquetas a una imagen en un PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para usar Aspose.PDF para .NET. Esto incluye instalar la biblioteca Aspose.PDF y configurar su proyecto para hacer referencia a él.

## Paso 2: Abra el documento PDF existente

En este paso, abriremos un documento PDF existente usando Aspose.PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Rutas de archivos de entrada y salida
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Abre el documento
Document document = new Document(inFile);
```

Abrimos el documento PDF existente usando Aspose.PDF.

## Paso 3: Obtenga contenido etiquetado y elemento de estructura raíz

Ahora obtendremos el contenido etiquetado del documento PDF y el elemento de estructura raíz correspondiente.

```csharp
// Obtener contenido etiquetado y elemento de estructura raíz
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Obtuvimos el contenido etiquetado del documento PDF y el elemento de estructura raíz correspondiente.

## Paso 4: Configurar el título del documento PDF etiquetado

Ahora configuremos el título para el documento PDF etiquetado.

```csharp
//Definir el título del documento PDF etiquetado
taggedContent.SetTitle("Document with images");
```

Hemos establecido el título para el documento PDF etiquetado.

## Paso 5: Asigne textos alternativos y cuadro delimitador a la imagen

Ahora, para cada elemento de imagen, asignaremos texto alternativo y un cuadro delimitador.

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

Ahora vamos a mover el elemento Span al párrafo.

```csharp
// Mueva el elemento Span al párrafo (encuentre el span y el párrafo incorrectos en el primer TD)
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

### Ejemplo de código fuente para etiquetar imagen en PDF existente usando Aspose.PDF para .NET 

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

// Establecer título para documento pdf etiquetado
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Establecer texto alternativo para la figura
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Crear y establecer el atributo BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Mueva el elemento de extensión al párrafo (encuentre la extensión y el párrafo incorrectos en el primer TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Mover elemento de extensión a párrafo
spanElement.ChangeParentElement(paragraph);

// Guardar documento
document.Save(outFile);

// Comprobación del cumplimiento de PDF/UA para nuestro documento
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusión

En este tutorial, aprendimos a marcar una imagen en un PDF existente usando Aspose.PDF para .NET. Ahora puede usar Aspose.PDF para agregar etiquetas y editar imágenes en sus documentos PDF.
