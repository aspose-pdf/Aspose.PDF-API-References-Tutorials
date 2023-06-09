---
title: Extraer texto de la anotación de sello
linktitle: Extraer texto de la anotación de sello
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda cómo extraer fácilmente texto de una anotación de sello en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
En este tutorial, lo guiaremos paso a paso sobre cómo extraer texto de una anotación de sello en un documento PDF utilizando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente de C# proporcionado para extraer el texto de una anotación de sello específica en una página determinada del documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento
Document doc = new Document(dataDir + "test.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: extraiga el texto de la anotación del sello

Ahora que ha cargado el documento PDF, puede extraer el texto de la anotación de sello específica. Así es cómo:

```csharp
// Recuperar anotación de búfer
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Crear un absorbente de texto
TextAbsorber ta = new TextAbsorber();

// Visita la apariencia de la anotación
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Mostrar el texto extraído
Console.WriteLine(ta.Text);
```

El código anterior recupera la anotación del sello de la página especificada del documento PDF y luego usa un absorbente de texto para extraer el texto de la apariencia de la anotación. El texto extraído se muestra en la salida.

### Ejemplo de código fuente para Extraer texto de anotación de sello con Aspose.PDF para .NET 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Conclusión

¡Felicidades! Ha aprendido a extraer texto de una anotación de sello en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede usar este método para extraer texto de otras anotaciones en sus documentos PDF.
