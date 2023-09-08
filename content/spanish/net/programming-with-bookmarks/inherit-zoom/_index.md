---
title: Heredar acercar archivo PDF
linktitle: Heredar acercar archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Herede fácilmente el zoom de marcadores en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-bookmarks/inherit-zoom/
---
La herencia de zoom en un archivo PDF le permite especificar un nivel de zoom predeterminado para los marcadores. Con Aspose.PDF para .NET, puede heredar fácilmente el zoom siguiendo el siguiente código fuente:

## Paso 1: importar las bibliotecas necesarias

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establezca la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea heredar el zoom. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: abre el documento PDF

Ahora vamos a abrir el documento PDF sobre el que queremos heredar el zoom usando el siguiente código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 4: obtenga la colección de marcadores

 En este paso, obtendremos la colección de marcadores o puntos de referencia del documento utilizando el`Outlines` propiedad de la`doc` objeto. Aquí está el código correspondiente:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Paso 5: Establecer el nivel de zoom

 Ahora estableceremos el nivel de zoom creando un`XYZExplicitDestination` objeto con las coordenadas x, y y z especificadas. Aquí usamos las coordenadas (100, 100, 0) con un zoom de 2. Aquí está el código correspondiente:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Paso 6: agregue nivel de zoom a marcadores

 En este paso agregamos el`XYZExplicitDestination` objeto como acción a los marcadores del`item` recopilación. Aquí está el código correspondiente:

```csharp
item. Action = new GoToAction(dest);
```

## Paso 7: agregue los marcadores actualizados al documento

 Finalmente, agregamos los marcadores actualizados a la colección de marcadores del documento usando el`Add` método de la`doc.Outlines` objeto. Aquí está el código correspondiente:

```csharp
doc. Outlines. Add(item);
```

## Paso 8: guarde el archivo actualizado

 Ahora guardemos el archivo PDF actualizado usando el`Save` método de la`doc` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para Inherit Zoom usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document doc = new Document(dataDir + "input.pdf");
// Obtenga una colección de esquemas/marcadores de archivos PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Establecer el nivel de zoom en 0
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

¡Enhorabuena! Ahora tiene una guía paso a paso para heredar Zoom con Aspose.PDF para .NET. Puede utilizar este código para especificar un nivel de zoom predeterminado para los marcadores en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.

### Preguntas frecuentes sobre heredar zoom en un archivo PDF

#### P: ¿Qué es la herencia de zoom en un archivo PDF?

R: La herencia de zoom se refiere a la capacidad de especificar un nivel de zoom predeterminado para los marcadores en un documento PDF. Esto permite una navegación consistente y fácil de usar cuando los usuarios interactúan con los marcadores.

#### P: ¿Por qué querría heredar los niveles de zoom de los marcadores?

R: Heredar niveles de zoom garantiza que los usuarios tengan una experiencia de visualización consistente al navegar a través de marcadores en un documento PDF. Puede resultar especialmente útil cuando desea proporcionar una vista específica para diferentes secciones de un documento.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto C#?

R: Para importar las bibliotecas necesarias para su proyecto C#, incluya las siguientes directivas de importación:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Estas directivas le permiten acceder a las clases y métodos necesarios para trabajar con documentos y marcadores PDF.

#### P: ¿Cómo especifico la ruta a la carpeta de documentos?

 R: En el código fuente proporcionado, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta real a la carpeta que contiene el archivo PDF para el cual desea heredar los niveles de zoom.

#### P: ¿Cómo abro un documento PDF para heredar los niveles de zoom?

R: Para abrir un documento PDF y heredar niveles de zoom, utilice el siguiente código:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Reemplazar`"input.pdf"` con el nombre del archivo real.

#### P: ¿Cómo configuro el nivel de zoom para los marcadores?

 R: Para establecer el nivel de zoom, cree un`XYZExplicitDestination` objeto con las coordenadas y el factor de zoom deseados. He aquí un ejemplo:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Esto establece el nivel de zoom en 2 en las coordenadas (100, 100).

#### P: ¿Cómo agrego el nivel de zoom a los marcadores?

 R: Añade el`XYZExplicitDestination` objeto como una acción para la colección de marcadores:

```csharp
item.Action = new GoToAction(dest);
```

 Dónde`item` es un`OutlineItemCollection` que representa un marcador.

#### P: ¿Cómo guardo el archivo PDF actualizado?

 R: Guarde el archivo PDF actualizado usando el`Save` método de la`doc` objeto:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### P: ¿Puedo personalizar los niveles de zoom para diferentes marcadores?

 R: Sí, puedes personalizar los niveles de zoom para diferentes marcadores creando múltiples`XYZExplicitDestination` objetos con diferentes coordenadas y factores de zoom.

#### P: ¿Existe un límite en la cantidad de marcadores a los que puedo aplicar la herencia de zoom?

R: Por lo general, no existe un límite estricto para la cantidad de marcadores a los que puede aplicar la herencia de zoom. Sin embargo, los documentos muy grandes con una cantidad excesiva de marcadores pueden requerir una gestión eficiente de la memoria.

#### P: ¿Cómo puedo confirmar que se ha aplicado la herencia de zoom?

R: Abra el archivo PDF generado para verificar que los marcadores hayan heredado los niveles de zoom especificados.