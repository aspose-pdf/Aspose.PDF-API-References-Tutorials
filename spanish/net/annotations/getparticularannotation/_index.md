---
title: Obtener anotación particular
linktitle: Obtener anotación particular
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para obtener una anotación particular en un documento PDF con esta guía paso a paso.
type: docs
weight: 80
url: /es/net/annotations/getparticularannotation/
---
Si está trabajando con archivos PDF en .NET, es posible que necesite obtener una anotación particular de un documento PDF. En esta guía, le mostraremos cómo usar Aspose.PDF para .NET para obtener una anotación particular de un documento PDF usando C#.

Siga estos sencillos pasos para obtener una anotación particular de un documento PDF:

## Paso 1: Obtenga una anotación particular del documento PDF

Primero, asegúrese de tener la biblioteca Aspose.PDF para .NET instalada y referenciada en su proyecto.

continuación, cree una nueva instancia de la clase Documento y cargue su documento PDF usando la ruta al directorio del documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## Paso 2: puede obtener una anotación particular usando el siguiente código:

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

Este código recupera la segunda anotación en la segunda página del documento PDF.

## Paso 3: Finalmente, puedes obtener las propiedades de la anotación usando el siguiente código:

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

Este código muestra el título, el asunto y el contenido de la anotación en la consola.


### Ejemplo de código fuente para obtener una anotación particular usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

// Obtener anotación particular
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

// Obtener propiedades de anotación
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

