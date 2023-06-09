---
title: Eliminar todos los marcadores
linktitle: Eliminar todos los marcadores
second_title: Referencia de API de Aspose.PDF para .NET
description: Elimine fácilmente todos los marcadores de sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-bookmarks/delete-all-bookmarks/
---

# Eliminar todos los marcadores con Aspose.PDF para .NET

En algunos casos, puede ser necesario eliminar los marcadores de un documento PDF. Con Aspose.PDF para .NET, puede eliminar fácilmente todos los marcadores siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea eliminar los marcadores. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora vamos a abrir el documento PDF del que queremos quitar los marcadores usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Paso 4: Elimina todos los marcadores

 En este paso, borramos todos los marcadores del documento usando el`Delete` metodo de la`Outlines` propiedad. Aquí está el código correspondiente:

```csharp
pdfDocument.Outlines.Delete();
```

## Paso 5: Guarde el archivo actualizado

 Finalmente, guardamos el archivo PDF actualizado usando el`Save` metodo de la`pdfDocument` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Eliminar todos los marcadores usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Eliminar todos los marcadores
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Guardar archivo actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para eliminar todos los marcadores con Aspose.PDF para .NET. Puede usar este código para limpiar sus documentos PDF eliminando todos los marcadores existentes.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.