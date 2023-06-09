---
title: Actualizar marcadores secundarios
linktitle: Actualizar marcadores secundarios
second_title: Referencia de API de Aspose.PDF para .NET
description: Actualice fácilmente los marcadores secundarios en sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-bookmarks/update-child-bookmarks/
---

La actualización de marcadores secundarios en un documento PDF le permite modificar las propiedades de marcadores específicos dentro de un marcador principal. Con Aspose.PDF para .NET, puede actualizar fácilmente los marcadores secundarios siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que desea actualizar. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora abriremos el documento PDF que queremos actualizar usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## Paso 4: Obtenga el objeto de marcador principal

En este paso, obtendremos el objeto de marcador principal específico del que queremos actualizar los marcadores secundarios. En el siguiente ejemplo, recuperamos el marcador principal en el índice 1 (el segundo marcador en la colección de marcadores). Puede ajustar el índice según sus necesidades. Aquí está el código correspondiente:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Paso 5: Obtener objeto de marcador secundario

Ahora obtengamos el objeto de marcador secundario específico que queremos actualizar. En el siguiente ejemplo, recuperamos el marcador secundario en el índice 1 (el segundo marcador secundario en la colección de marcadores secundarios del marcador principal). Puede ajustar el índice según sus necesidades. Aquí está el código correspondiente:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## Paso 6: actualice las propiedades del marcador secundario

Ahora actualicemos las propiedades del marcador secundario, como el título, el estilo en cursiva y el estilo en negrita. Puede ajustar estas propiedades según sus necesidades. Aquí está el código correspondiente:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## Paso 7: Guarde el archivo actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`pdfDocument` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Actualizar marcadores secundarios mediante Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Obtener un objeto de marcador
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
// Obtener objeto de marcador secundario
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// Guardar salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para actualizar marcadores secundarios con Aspose.PDF para .NET. Puede usar este código para modificar las propiedades de los marcadores secundarios en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.