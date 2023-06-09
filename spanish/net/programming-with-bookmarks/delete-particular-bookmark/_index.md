---
title: Eliminar marcador particular
linktitle: Eliminar marcador particular
second_title: Referencia de API de Aspose.PDF para .NET
description: Elimine fácilmente un marcador en particular de sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-bookmarks/delete-particular-bookmark/
---

Puede ser necesario eliminar un marcador en particular de un documento PDF. Con Aspose.PDF para .NET, puede eliminar fácilmente un marcador en particular siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea eliminar un marcador en particular. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora vamos a abrir el documento PDF del que queremos quitar un marcador usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
```

## Paso 4: eliminar un marcador en particular

 En este paso, eliminamos un marcador en particular usando el`Delete` metodo de la`Outlines` propiedad. Especificamos el título del marcador a eliminar. Aquí está el código correspondiente:

```csharp
pdfDocument.Outlines.Delete("Child Outline");
```

## Paso 5: Guarde el archivo actualizado

 Finalmente, guardamos el archivo PDF actualizado usando el`Save` metodo de la`pdfDocument` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Eliminar marcador particular usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
// Eliminar esquema particular por título
pdfDocument.Outlines.Delete("Child Outline");
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
// Guardar archivo actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para eliminar un marcador en particular con Aspose.PDF para .NET. Puede usar este código para apuntar y eliminar marcadores específicos de sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.