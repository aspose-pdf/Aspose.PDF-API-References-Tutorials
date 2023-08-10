---
title: Agregar marcador secundario en archivo PDF
linktitle: Agregar marcador secundario en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente un marcador secundario en un archivo PDF para una navegación más organizada con Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-bookmarks/add-child-bookmark/
---
Agregar marcadores secundarios en un archivo PDF permite una organización y navegación más estructuradas. Con Aspose.PDF para .NET, puede agregar fácilmente un submarcador siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un marcador secundario. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

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

### Preguntas frecuentes para agregar un marcador secundario en un archivo PDF

#### P: ¿Qué son los marcadores secundarios en un archivo PDF?

R: Los marcadores secundarios, también conocidos como marcadores secundarios, son elementos de navegación dentro de un documento PDF que están estructurados jerárquicamente bajo un marcador principal. Proporcionan una forma de crear una tabla de contenido más organizada y detallada para el documento.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto de C#?

R: Para importar las bibliotecas requeridas para su proyecto C#, puede usar la siguiente directiva de importación:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Estas bibliotecas proporcionan las clases y funciones necesarias para trabajar con documentos PDF y funciones interactivas.

#### P: ¿Cómo especifico la ruta a la carpeta de documentos?

 R: En el código fuente provisto, debe reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a la carpeta que contiene el archivo PDF con el que desea trabajar. Esto garantiza que el código localice correctamente el archivo PDF de destino.

#### P: ¿Puedo crear varios niveles de marcadores secundarios?

R: Sí, puede crear varios niveles de marcadores secundarios ampliando el proceso descrito en el tutorial. Al crear marcadores principales con marcadores secundarios y anidarlos aún más, puede crear una estructura jerárquica de marcadores para documentos PDF complejos.

####  P: ¿Cuál es el propósito de la`OutlineItemCollection` class?

 R: El`OutlineItemCollection` La clase en Aspose.PDF para .NET se usa para crear y administrar esquemas, que son esencialmente marcadores en un documento PDF. Esta clase le permite establecer propiedades como título, estilo de fuente y acciones para marcadores.

#### P: ¿Cómo agrego un marcador secundario a un marcador principal?

 R: Para agregar un marcador secundario a un marcador principal, debe crear un nuevo`OutlineItemCollection` objeto para el submarcador y establecer sus propiedades. Entonces, usas el`Add` método del marcador principal`OutlineItemCollection` para agregar el marcador secundario a la colección principal.

#### P: ¿Puedo personalizar la apariencia de los marcadores secundarios?

R: Sí, al igual que los marcadores principales, puede personalizar la apariencia de los marcadores secundarios configurando propiedades como el título, el estilo de fuente y otros atributos. Esto le permite crear marcadores visualmente distintivos e informativos.

#### P: ¿Es Aspose.PDF para .NET compatible con otros lenguajes de programación?

R: Aspose.PDF para .NET está diseñado específicamente para entornos C# y .NET. Sin embargo, Aspose ofrece bibliotecas similares para otros lenguajes de programación como Java y Android, cada uno adaptado a sus respectivas plataformas.

#### P: ¿Cómo mejoran los marcadores infantiles la navegación en PDF?

R: Los marcadores secundarios mejoran la navegación en PDF al proporcionar una tabla de contenido más estructurada y organizada. Los usuarios pueden acceder rápidamente a secciones específicas del documento a través de la estructura jerárquica de marcadores.