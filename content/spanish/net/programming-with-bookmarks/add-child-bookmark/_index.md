---
title: Agregar marcador infantil en un archivo PDF
linktitle: Agregar marcador infantil en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Agregue fácilmente un marcador secundario en un archivo PDF para una navegación más organizada con Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-bookmarks/add-child-bookmark/
---
Agregar marcadores secundarios en un archivo PDF permite una organización y navegación más estructuradas. Con Aspose.PDF para .NET, puede agregar fácilmente un submarcador siguiendo el siguiente código fuente:

## Paso 1: importar las bibliotecas necesarias

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establezca la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un submarcador. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: abre el documento PDF

Ahora abriremos el documento PDF al que queremos agregar un submarcador usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Paso 4: crear un objeto de marcador principal

 En este paso, crearemos un objeto de marcador principal usando el`OutlineItemCollection` clase y establezca sus propiedades como título, atributo de cursiva y atributo de negrita. Aquí está el código correspondiente:

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

## Paso 6: agregue el submarcador al marcador principal

 Finalmente, agregamos el submarcador creado a la colección de submarcadores del marcador principal usando el`Add` método del objeto padre. Aquí está el código correspondiente:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Paso 7: agregue el marcador principal a la colección de marcadores del documento

 Finalmente, agregamos el marcador principal a la colección de marcadores del documento usando el`Add` método de la`Outlines` propiedad. Aquí está el código correspondiente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Código fuente de muestra para Agregar marcador secundario usando Aspose.PDF para .NET 
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
// Agregar marcador secundario en la colección de marcadores principales
pdfOutline.Add(pdfChildOutline);
// Agregue un marcador principal en la colección de esquemas del documento.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Guardar salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Enhorabuena! Ahora tiene una guía paso a paso para agregar un submarcador con Aspose.PDF para .NET. Puede utilizar este código para organizar y estructurar sus marcadores en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.

### Preguntas frecuentes para agregar un marcador infantil en un archivo PDF

#### P: ¿Qué son los marcadores secundarios en un archivo PDF?

R: Los marcadores secundarios, también conocidos como submarcadores, son elementos de navegación dentro de un documento PDF que están estructurados jerárquicamente bajo un marcador principal. Proporcionan una manera de crear una tabla de contenido más organizada y detallada para el documento.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto C#?

R: Para importar las bibliotecas necesarias para su proyecto C#, puede utilizar la siguiente directiva de importación:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Estas bibliotecas proporcionan las clases y funciones necesarias para trabajar con documentos PDF y funciones interactivas.

#### P: ¿Cómo especifico la ruta a la carpeta de documentos?

 R: En el código fuente proporcionado, debe reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a la carpeta que contiene el archivo PDF con el que desea trabajar. Esto garantiza que el código ubique correctamente el archivo PDF de destino.

#### P: ¿Puedo crear varios niveles de marcadores secundarios?

R: Sí, puedes crear múltiples niveles de marcadores secundarios ampliando el proceso descrito en el tutorial. Al crear marcadores principales con submarcadores y anidarlos aún más, puede crear una estructura jerárquica de marcadores para documentos PDF complejos.

####  P: ¿Cuál es el propósito de la`OutlineItemCollection` class?

 R: El`OutlineItemCollection` La clase en Aspose.PDF para .NET se utiliza para crear y administrar esquemas, que son esencialmente marcadores en un documento PDF. Esta clase le permite establecer propiedades como título, estilo de fuente y acciones para marcadores.

#### P: ¿Cómo agrego un submarcador a un marcador principal?

 R: Para agregar un submarcador a un marcador principal, crea un nuevo`OutlineItemCollection` objeto para el submarcador y establezca sus propiedades. Luego, usas el`Add` método del marcador principal`OutlineItemCollection` para agregar el submarcador a la colección de los padres.

#### P: ¿Puedo personalizar la apariencia de los marcadores infantiles?

R: Sí, de manera similar a los marcadores principales, puede personalizar la apariencia de los marcadores secundarios configurando propiedades como título, estilo de fuente y otros atributos. Esto le permite crear marcadores visualmente distintivos e informativos.

#### P: ¿Aspose.PDF para .NET es compatible con otros lenguajes de programación?

R: Aspose.PDF para .NET está diseñado específicamente para entornos C# y .NET. Sin embargo, Aspose ofrece bibliotecas similares para otros lenguajes de programación como Java y Android, cada una adaptada a sus respectivas plataformas.

#### P: ¿Cómo mejoran los marcadores secundarios la navegación en PDF?

R: Los marcadores secundarios mejoran la navegación del PDF al proporcionar una tabla de contenidos más estructurada y organizada. Los usuarios pueden acceder rápidamente a secciones específicas del documento a través de la estructura jerárquica de marcadores.