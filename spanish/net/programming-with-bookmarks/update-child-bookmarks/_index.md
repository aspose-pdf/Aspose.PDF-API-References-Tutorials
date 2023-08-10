---
title: Actualizar marcadores secundarios en archivo PDF
linktitle: Actualizar marcadores secundarios en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Actualice fácilmente los marcadores secundarios en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-bookmarks/update-child-bookmarks/
---
La actualización de marcadores secundarios en un archivo PDF le permite modificar las propiedades de marcadores específicos dentro de un marcador principal. Con Aspose.PDF para .NET, puede actualizar fácilmente los marcadores secundarios siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF que desea actualizar. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

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

¡Felicidades! Ahora tiene una guía paso a paso para actualizar marcadores secundarios con Aspose.PDF para .NET. Puede usar este código para modificar las propiedades de los marcadores secundarios en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.

### Preguntas frecuentes sobre la actualización de marcadores secundarios en un archivo PDF

#### P: ¿Qué son los marcadores secundarios en un archivo PDF?

R: Los marcadores secundarios son marcadores anidados dentro de un marcador principal. Le permiten crear una estructura jerárquica para navegar por el contenido de un documento PDF.

#### P: ¿Por qué tendría que actualizar los marcadores de niños?

R: La actualización de marcadores secundarios es útil cuando desea modificar las propiedades, los títulos o los estilos de marcadores específicos dentro de un marcador principal. Esto ayuda a personalizar la estructura de navegación del documento.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto de C#?

R: Para importar las bibliotecas necesarias para su proyecto C#, incluya la siguiente directiva de importación:

```csharp
using Aspose.Pdf;
```

Esta directiva le permite acceder a las clases y métodos necesarios para trabajar con documentos PDF y marcadores.

#### P: ¿Cómo especifico la ruta a la carpeta de documentos?

 R: reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código fuente proporcionado con la ruta real a la carpeta que contiene el archivo PDF que desea actualizar.

#### P: ¿Cómo abro un documento PDF para actualizar los marcadores secundarios?

R: Para abrir un documento PDF y actualizar los marcadores secundarios, use el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

 Reemplazar`"UpdateChildBookmarks.pdf"` con el nombre real del archivo.

#### P: ¿Cómo obtengo el objeto de marcador principal desde el que quiero actualizar los marcadores secundarios?

 R: Para recuperar un marcador principal específico para actualizar los marcadores secundarios, acceda al`Outlines` propiedad de la`pdfDocument` objeto. En el siguiente ejemplo, recuperamos el marcador principal en el índice 1:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

#### P: ¿Cómo obtengo el objeto de marcador secundario que quiero actualizar?

 R: Para recuperar un marcador secundario específico para actualizarlo, acceda al`OutlineItemCollection` del marcador principal. En el siguiente ejemplo, recuperamos el marcador secundario en el índice 1:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

#### P: ¿Qué propiedades de marcadores secundarios puedo actualizar?

R: Puede actualizar varias propiedades de un marcador secundario, como el título, el estilo en cursiva y el estilo en negrita. Personaliza estas propiedades según tus necesidades:

```csharp
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
```

#### P: ¿Puedo actualizar varios marcadores secundarios con este método?

R: Sí, puede repetir los pasos 4 a 7 para cada marcador infantil que desee actualizar. Modifique el índice principal y el índice secundario según sea necesario.

#### P: ¿Cómo guardo el archivo PDF actualizado?

 R: Guarde el archivo PDF actualizado usando el`Save` metodo de la`pdfDocument` objeto:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```