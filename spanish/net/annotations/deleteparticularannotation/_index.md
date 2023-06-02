---
title: Eliminar anotación particular
linktitle: Eliminar anotación particular
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda cómo eliminar una anotación en particular de un documento PDF usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 50
url: /es/net/annotations/deleteparticularannotation/
---
En este tutorial, le mostraremos cómo usar Aspose.PDF para .NET para eliminar una anotación particular de un archivo PDF usando C#.

Siga los pasos a continuación para mostrar cómo eliminar una anotación particular con Aspose.PDF para .NET

## Paso 1: establecer la ruta del directorio

Declare una variable para contener la ruta al archivo PDF que contiene la anotación que se va a eliminar. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 Abra el archivo PDF usando el`Document` clase en Aspose.PDF para .NET.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");
```

## Paso 3: obtenga la página para eliminar la anotación en particular

Elimine la anotación particular especificando su índice y el índice de la página a la que pertenece. En este tutorial, eliminamos la anotación ubicada en el índice 1 en la segunda página del archivo PDF.

```csharp
pdfDocument.Pages[1].Annotations.Delete(1);
```
## Paso 4: Guarde el documento PDF actualizado

Guarde el archivo PDF actualizado en un nuevo archivo con un nombre diferente.

```csharp
dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```

## Paso 5: muestra un mensaje para eliminar una anotación particular

Imprima un mensaje que indique que la anotación en particular se eliminó y se guardó el archivo PDF actualizado.

```csharp
Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);
```

### Código fuente de ejemplo para eliminar una anotación en particular usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");

// Eliminar anotación particular
pdfDocument.Pages[1].Annotations.Delete(1);

dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);

Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);
```
