---
title: Etiquetar imagen en PDF existente
linktitle: Etiquetar imagen en PDF existente
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a etiquetar imágenes en archivos PDF existentes con Aspose.PDF para .NET. Guía paso a paso para mejorar la accesibilidad con compatibilidad con PDF/UA.
type: docs
weight: 210
url: /es/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Introducción

En este tutorial, le mostraremos cómo etiquetar una imagen en un PDF existente con Aspose.PDF para .NET. Al finalizar esta guía, podrá configurar texto alternativo para imágenes, ajustar atributos de diseño y asegurarse de que su PDF cumpla con los estándares de accesibilidad.

## Prerrequisitos

Antes de comenzar, repasemos lo que necesitarás para comenzar:

-  Aspose.PDF para .NET: asegúrese de haber descargado e instalado la última versión de Aspose.PDF para .NET.[Descarga aquí](https://releases.aspose.com/pdf/net/).
- .NET Framework: asegúrese de tener configurado un entorno de desarrollo .NET como Visual Studio.
- Comprensión básica de la estructura de PDF: familiaridad con los elementos de la estructura de PDF, como párrafos, espacios, tablas e imágenes.
-  Una licencia válida: puede comprar una licencia[aquí](https://purchase.aspose.com/buy) o utilizar uno temporal[aquí](https://purchase.aspose.com/temporary-license/).

## Importar paquetes

Para comenzar a codificar, debe importar los espacios de nombres esenciales de Aspose.PDF para .NET. Estos le brindarán acceso a las clases y métodos necesarios para manipular el documento PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ahora que hemos preparado el escenario, dividamos el proceso de etiquetado de una imagen en varios pasos.

## Paso 1: Cargue el documento PDF existente

El primer paso es cargar el archivo PDF con el que desea trabajar. Puede ser cualquier archivo PDF con una imagen que desee etiquetar.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Abrir el documento
Document document = new Document(inFile);
```

-  Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su archivo.
-  El`Document` La clase te permite cargar un PDF existente. Modificarás este PDF para etiquetar la imagen.

## Paso 2: Acceda al contenido etiquetado y al elemento de estructura raíz

Una vez que haya abierto el PDF, el siguiente paso es acceder al contenido etiquetado e identificar el elemento de estructura raíz. Esto es fundamental, ya que le permite navegar por los elementos del PDF y realizar modificaciones.

```csharp
// Obtener contenido etiquetado y elemento de estructura raíz
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` Proporciona acceso a los elementos estructurados en el PDF.
-  El`RootElement` es el elemento de estructura superior, desde el cual se puede pasar a otros elementos como párrafos, tablas e imágenes.

## Paso 3: Establezca el título para el documento PDF etiquetado

Agregar un título al documento PDF etiquetado garantiza que su documento esté etiquetado correctamente, lo que es útil para la accesibilidad y el cumplimiento de PDF/UA.

```csharp
// Establecer título para el documento PDF etiquetado
taggedContent.SetTitle("Document with images");
```

- Establecer un título para su PDF etiquetado mejora la accesibilidad y mejora la claridad del documento para los lectores de pantalla y las tecnologías de asistencia.

## Paso 4: Busque y etiquete la imagen

 Ahora, busquemos el elemento de imagen (al que se hace referencia como`FigureElement` en Aspose.PDF), establezca un texto alternativo para él y configure sus atributos de diseño.

```csharp
// Recorrer todos los elementos de la figura (imágenes) y establecer atributos de texto y diseño alternativos
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Establecer texto alternativo para la figura
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // Crear y configurar el atributo BBox (cuadro delimitador)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Establecer atributos de diseño para la figura
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Este código recorre todos los`FigureElement` objetos en la estructura raíz, que representan imágenes.
- Establece el texto alternativo para accesibilidad (los lectores de pantalla lo usarán para describir la imagen).
- El cuadro delimitador (`BBox`especifica las coordenadas para el diseño de la imagen, garantizando que se muestre correctamente en el documento.

## Paso 5: Modificar elementos de la tabla

 En algunos casos, es posible que necesites modificar elementos de extensión dentro de una tabla. Aquí, demostraremos cómo encontrar un elemento de extensión.`SpanElement` y moverlo a un párrafo.

```csharp
// Encuentre los elementos de tabla, lapso y párrafo
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Mueva el elemento span al párrafo
spanElement.ChangeParentElement(paragraph);
```

-  Aquí, localizamos el`TableElement`, `SpanElement` , y`ParagraphElement` dentro del PDF.
-  Usando el`ChangeParentElement` Método, movemos el espacio dentro del párrafo para garantizar una estructura y etiquetado adecuados.

## Paso 6: Guarde el documento y valide la conformidad con PDF/UA

Una vez realizados todos los cambios, el paso final es guardar el PDF actualizado y verificar si cumple con los estándares PDF/UA.

```csharp
// Guardar el documento PDF actualizado
document.Save(outFile);

// Validar la conformidad con PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  El`Validate` El método verifica el documento PDF con los estándares PDF/UA y registra los resultados.
- Garantizar el cumplimiento ayuda a mejorar la accesibilidad y cumplir con los requisitos reglamentarios para la publicación de documentos.

## Conclusión

En este tutorial, le mostramos cómo etiquetar imágenes en un PDF existente utilizando Aspose.PDF para .NET. Al configurar texto alternativo, ajustar atributos de diseño y validar el documento para que cumpla con los estándares PDF/UA, puede asegurarse de que sus archivos PDF sean accesibles y cumplan con los estándares modernos. Aspose.PDF facilita el trabajo con elementos estructurados, lo que le brinda control sobre el diseño y la accesibilidad de su documento.

## Preguntas frecuentes

### ¿Para qué se utiliza Aspose.PDF para .NET?
Aspose.PDF para .NET es una potente biblioteca que se utiliza para crear, editar y manipular documentos PDF mediante programación en un entorno .NET.

### ¿Cómo puedo garantizar la conformidad con PDF/UA?
 Puedes utilizar Aspose.PDF`Validate` Método para verificar la conformidad con PDF/UA después de realizar modificaciones en el documento.

### ¿Qué es el texto alternativo en archivos PDF?
El texto alternativo es una descripción que se agrega a las imágenes en archivos PDF para mejorar la accesibilidad, especialmente para los usuarios que dependen de lectores de pantalla.

### ¿Puedo manipular tablas y espacios en un PDF con Aspose.PDF?
Sí, Aspose.PDF le permite manipular tablas, intervalos y otros elementos estructurados dentro de un documento PDF.

### ¿Dónde puedo descargar Aspose.PDF para .NET?
 Puede descargar la última versión de Aspose.PDF para .NET[aquí](https://releases.aspose.com/pdf/net/).