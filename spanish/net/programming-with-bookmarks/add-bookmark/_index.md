---
title: Añadir marcador
linktitle: Añadir marcador
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente marcadores a sus archivos PDF para mejorar la navegación con Aspose.PDF para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/add-bookmark/
---

Agregar marcadores en un documento PDF permite una navegación fácil y rápida. Con Aspose.PDF para .NET, puede agregar fácilmente un marcador siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un marcador. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora abriremos el documento PDF al que queremos añadir un marcador usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Paso 4: Crea un objeto marcador

 En este paso, crearemos un objeto marcador usando`OutlineItemCollection` class y establezca sus propiedades, como el título, el atributo en cursiva, el atributo en negrita y la acción que se realizará al hacer clic. Aquí está el código correspondiente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Paso 5: Agregar marcador al documento

 Finalmente, agregamos el marcador creado a la colección de marcadores del documento usando el`Add` metodo de la`Outlines` propiedad. Aquí está el código correspondiente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Ejemplo de código fuente para Agregar marcador usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Crear un objeto marcador
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Establecer el número de página de destino
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Agregue un marcador en la colección de esquemas del documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Guardar salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para agregar un marcador usando Aspose.PDF para .NET. Puede usar este código para mejorar la navegación en sus documentos PDF agregando marcadores personalizados.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.