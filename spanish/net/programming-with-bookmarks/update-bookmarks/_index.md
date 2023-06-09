---
title: Actualizar marcadores
linktitle: Actualizar marcadores
second_title: Referencia de API de Aspose.PDF para .NET
description: Actualice fácilmente los marcadores en sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-bookmarks/update-bookmarks/
---

A menudo, es necesario actualizar los marcadores en un documento PDF para reflejar cambios o actualizaciones en la estructura o el contenido del documento. Con Aspose.PDF para .NET, puede actualizar fácilmente los marcadores siguiendo el siguiente código fuente:

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
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
```

## Paso 4: Obtenga el objeto de marcador

En este paso, obtendremos el objeto de marcador específico que queremos actualizar. En el siguiente ejemplo, recuperamos el marcador en el índice 1 (el segundo marcador en la colección de marcadores). Puede ajustar el índice según sus necesidades. Aquí está el código correspondiente:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Paso 5: actualice las propiedades del marcador

Ahora actualicemos las propiedades del marcador, como el título, el estilo en cursiva y el estilo en negrita. Puede ajustar estas propiedades según sus necesidades. Aquí está el código correspondiente:

```csharp
pdfOutline.Title = "Updated Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Paso 6: Guarde el archivo actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`pdfDocument` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "UpdateBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Actualizar marcadores usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
// Obtener un objeto de marcador
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
pdfOutline.Title = "Updated Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
dataDir = dataDir + "UpdateBookmarks_out.pdf";
// Guardar salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para actualizar marcadores con Aspose.PDF para .NET. Puede usar este código para cambiar los títulos y estilos de los marcadores en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.