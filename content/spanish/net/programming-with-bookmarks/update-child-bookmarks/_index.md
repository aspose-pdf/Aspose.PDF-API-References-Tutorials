---
title: Actualizar marcadores secundarios en un archivo PDF
linktitle: Actualizar marcadores secundarios en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Actualice fácilmente los marcadores secundarios en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-bookmarks/update-child-bookmarks/
---
La actualización de marcadores secundarios en un archivo PDF le permite modificar las propiedades de marcadores específicos dentro de un marcador principal. Con Aspose.PDF para .NET, puede actualizar fácilmente los marcadores secundarios siguiendo el siguiente código fuente:

## Paso 1: importar las bibliotecas necesarias

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
```

## Paso 2: establezca la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que desea actualizar. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: abre el documento PDF

Ahora abriremos el documento PDF que queremos actualizar usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## Paso 4: obtener el objeto de marcador principal

En este paso, obtendremos el objeto de marcador principal específico desde el cual queremos actualizar los marcadores secundarios. En el siguiente ejemplo, recuperamos el marcador principal en el índice 1 (el segundo marcador de la colección de marcadores). Puede ajustar el índice según sus necesidades. Aquí está el código correspondiente:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Paso 5: Obtener el objeto de marcador secundario

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

## Paso 7: guarde el archivo actualizado

 Ahora guardemos el archivo PDF actualizado usando el`Save` método de la`pdfDocument` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Código fuente de muestra para actualizar marcadores secundarios usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Obtener un objeto de marcador
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
//Obtener objeto de marcador secundario
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

¡Enhorabuena! Ahora tiene una guía paso a paso para actualizar los marcadores secundarios con Aspose.PDF para .NET. Puede utilizar este código para modificar las propiedades de los marcadores secundarios en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.

### Preguntas frecuentes para actualizar marcadores secundarios en un archivo PDF

#### P: ¿Qué son los marcadores secundarios en un archivo PDF?

R: Los marcadores secundarios son marcadores anidados dentro de un marcador principal. Le permiten crear una estructura jerárquica para navegar por el contenido de un documento PDF.

#### P: ¿Por qué necesitaría actualizar los marcadores infantiles?

R: Actualizar los marcadores secundarios es útil cuando desea modificar las propiedades, títulos o estilos de marcadores específicos dentro de un marcador principal. Esto ayuda a personalizar la estructura de navegación del documento.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto C#?

R: Para importar las bibliotecas necesarias para su proyecto C#, incluya la siguiente directiva de importación:

```csharp
using Aspose.Pdf;
```

Esta directiva le permite acceder a las clases y métodos necesarios para trabajar con documentos y marcadores PDF.

#### P: ¿Cómo especifico la ruta a la carpeta de documentos?

 R: Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código fuente proporcionado con la ruta real a la carpeta que contiene el archivo PDF que desea actualizar.

#### P: ¿Cómo abro un documento PDF para actualizar los marcadores secundarios?

R: Para abrir un documento PDF y actualizar los marcadores secundarios, utilice el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

 Reemplazar`"UpdateChildBookmarks.pdf"` con el nombre del archivo real.

#### P: ¿Cómo obtengo el objeto de marcador principal desde el cual deseo actualizar los marcadores secundarios?

 R: Para recuperar un marcador principal específico y actualizar los marcadores secundarios, acceda al`Outlines` propiedad de la`pdfDocument` objeto. En el siguiente ejemplo, recuperamos el marcador principal en el índice 1:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

#### P: ¿Cómo obtengo el objeto de marcador secundario que deseo actualizar?

 R: Para recuperar un marcador infantil específico para actualizarlo, acceda al`OutlineItemCollection` del marcador principal. En el siguiente ejemplo, recuperamos el marcador secundario en el índice 1:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

#### P: ¿Qué propiedades de marcadores secundarios puedo actualizar?

R: Puede actualizar varias propiedades de un marcador secundario, como su título, estilo en cursiva y estilo en negrita. Personaliza estas propiedades según tus necesidades:

```csharp
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
```

#### P: ¿Puedo actualizar varios marcadores secundarios usando este método?

R: Sí, puedes repetir los pasos del 4 al 7 para cada marcador infantil que quieras actualizar. Modifique el índice principal y el índice secundario según sea necesario.

#### P: ¿Cómo guardo el archivo PDF actualizado?

 R: Guarde el archivo PDF actualizado usando el`Save` método de la`pdfDocument` objeto:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```