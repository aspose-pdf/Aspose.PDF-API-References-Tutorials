---
title: Heredar zoom
linktitle: Heredar zoom
second_title: Referencia de API de Aspose.PDF para .NET
description: Herede fácilmente el zoom de marcadores en sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-bookmarks/inherit-zoom/
---

La herencia de zoom en un documento PDF le permite especificar un nivel de zoom predeterminado para los marcadores. Con Aspose.PDF para .NET, puede heredar fácilmente el zoom siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establecer la ruta a la carpeta de documentos

En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea heredar el zoom. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora vamos a abrir el documento PDF sobre el que queremos heredar el zoom usando el siguiente código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 4: Obtenga la colección de marcadores

 En este paso, obtendremos la colección de marcadores o puntos de referencia del documento utilizando el`Outlines` propiedad de la`doc` objeto. Aquí está el código correspondiente:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Paso 5: establecer el nivel de zoom

 Ahora estableceremos el nivel de zoom creando un`XYZExplicitDestination` objeto con las coordenadas x, y y z especificadas. Aquí usamos las coordenadas (100, 100, 0) con un zoom de 2. Aquí está el código correspondiente:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Paso 6: agregue el nivel de zoom a los marcadores

 En este paso, agregamos el`XYZExplicitDestination` objeto como una acción a los marcadores de la`item` recopilación. Aquí está el código correspondiente:

```csharp
item. Action = new GoToAction(dest);
```

## Paso 7: agregue los marcadores actualizados al documento

 Finalmente, agregamos los marcadores actualizados a la colección de marcadores del documento usando el`Add` metodo de la`doc.Outlines` objeto. Aquí está el código correspondiente:

```csharp
doc. Outlines. Add(item);
```

## Paso 8: Guarde el archivo actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`doc` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para Inherit Zoom usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document doc = new Document(dataDir + "input.pdf");
// Obtenga una colección de esquemas/marcadores de un archivo PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Establecer el nivel de zoom como 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Agregue XYZExplicitDestination como acción a la colección de esquemas de PDF
item.Action = new GoToAction(dest);
// Agregar elemento a la colección de esquemas del archivo PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Guardar salida
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para Heredar Zoom con Aspose.PDF para .NET. Puede usar este código para especificar un nivel de zoom predeterminado para los marcadores en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.