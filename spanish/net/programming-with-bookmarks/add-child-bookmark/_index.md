---
title: Agregar marcador secundario
linktitle: Agregar marcador secundario
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente marcadores secundarios a sus archivos PDF para una navegación más organizada con Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-bookmarks/add-child-bookmark/
---

Agregar marcadores secundarios a un documento PDF permite una organización y navegación más estructuradas. Con Aspose.PDF para .NET, puede agregar fácilmente un submarcador siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un marcador secundario. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora abriremos el documento PDF al que queremos añadir un submarcador usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Paso 4: crear un objeto de marcador principal

 En este paso, crearemos un objeto de marcador principal usando el`OutlineItemCollection` class y establezca sus propiedades, como el título, el atributo en cursiva y el atributo en negrita. Aquí está el código correspondiente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Paso 5: crear un objeto de marcador secundario

En este paso, crearemos un objeto de submarcador nuevamente usando el`OutlineItemCollection` clase y establecer sus propiedades. Aquí está el código correspondiente:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Paso 6: agregue el marcador secundario al marcador principal

 Finalmente, agregamos el submarcador creado a la colección de submarcadores del marcador principal usando el`Add` método del objeto principal. Aquí está el código correspondiente:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Paso 7: agregue el marcador principal a la colección de marcadores del documento

 Finalmente, agregamos el marcador principal a la colección de marcadores del documento usando el`Add` metodo de la`Outlines` propiedad. Aquí está el código correspondiente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Ejemplo de código fuente para Agregar marcador secundario usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Crear un objeto de marcador principal
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Crear un objeto de marcador secundario
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Agregue un marcador secundario en la colección de marcadores principales
pdfOutline.Add(pdfChildOutline);
// Agregue un marcador principal en la colección de esquemas del documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Guardar salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para agregar un marcador secundario con Aspose.PDF para .NET. Puede usar este código para organizar y estructurar sus marcadores en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.