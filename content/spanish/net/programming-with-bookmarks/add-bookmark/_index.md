---
title: Agregar marcador en archivo PDF
linktitle: Agregar marcador en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Agregue fácilmente un marcador en un archivo PDF para mejorar la navegación con Aspose.PDF para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/add-bookmark/
---
Agregar marcadores en un archivo PDF permite una navegación fácil y rápida. Con Aspose.PDF para .NET, puede agregar fácilmente un marcador en un archivo PDF siguiendo el siguiente código fuente:

## Paso 1: importar las bibliotecas necesarias

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establezca la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un marcador. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: abre el documento PDF

Ahora abriremos el documento PDF al que queremos agregar un marcador usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Paso 4: crear un objeto de marcador

 En este paso, crearemos un objeto marcador usando`OutlineItemCollection` clase y establezca sus propiedades como título, atributo de cursiva, atributo de negrita y acción a realizar al hacer clic. Aquí está el código correspondiente:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Paso 5: agregar marcador al documento

 Finalmente, agregamos el marcador creado a la colección de marcadores del documento usando el`Add` método de la`Outlines` propiedad. Aquí está el código correspondiente:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Código fuente de muestra para Agregar marcador usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Crear un objeto de marcador
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

¡Enhorabuena! Ahora tiene una guía paso a paso para agregar un marcador usando Aspose.PDF para .NET. Puede utilizar este código para mejorar la navegación en sus documentos PDF agregando marcadores personalizados.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.


### Preguntas frecuentes para agregar un marcador en un archivo PDF

#### P: ¿Qué son los marcadores en un archivo PDF?

R: Los marcadores, también conocidos como esquemas, son elementos interactivos que proporcionan navegación y estructura dentro de un documento PDF. Permiten a los usuarios saltar rápidamente a secciones o páginas específicas.

#### P: ¿Por qué necesitaría agregar marcadores a un archivo PDF?

R: Agregar marcadores a un archivo PDF mejora la experiencia del usuario y facilita a los lectores la navegación por el contenido del documento. Los marcadores pueden servir como tabla de contenido o proporcionar acceso rápido a secciones importantes.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto C#?

R: Para importar las bibliotecas necesarias para su proyecto C#, incluya las siguientes directivas de importación:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Estas directivas le permiten acceder a las clases y métodos necesarios para trabajar con documentos y marcadores PDF.

#### P: ¿Cómo especifico la ruta a la carpeta de documentos?

 R: Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código fuente proporcionado con la ruta real a la carpeta que contiene el archivo PDF al que desea agregar un marcador.

#### P: ¿Cómo abro un documento PDF para agregar marcadores?

R: Para abrir un documento PDF y agregar marcadores, use el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Reemplazar`"AddBookmark.pdf"` con el nombre del archivo real.

#### P: ¿Cómo creo un objeto marcador?

 R: Para crear un objeto marcador, utilice el`OutlineItemCollection` clase. Personalice sus propiedades, como título, estilo en cursiva, estilo en negrita y acción para realizar al hacer clic.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  P: ¿Cuál es el propósito de la`Action` property in a bookmark?

 R: El`Action` La propiedad especifica la acción que se realizará cuando se haga clic en el marcador. En este ejemplo, utilizamos el`GoToAction`clase para navegar a una página específica (página 2 en este caso).

#### P: ¿Cómo agrego el marcador al documento?

 R: Utilice el`Add` método de la`Outlines` propiedad para agregar el marcador creado a la colección de marcadores del documento.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### P: ¿Puedo agregar varios marcadores usando este método?

R: Sí, puede repetir los pasos del 4 al 8 para agregar varios marcadores al documento. Personalice las propiedades y acciones de cada marcador según sea necesario.

#### P: ¿Cómo guardo el archivo PDF actualizado?

 R: Guarde el archivo PDF actualizado usando el`Save` método de la`pdfDocument` objeto:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### P: ¿Cómo puedo confirmar que se han agregado los marcadores?

R: Abra el archivo PDF generado para verificar que los marcadores especificados se hayan agregado al documento.

#### P: ¿Existe un límite en la cantidad de marcadores que puedo agregar?

R: Generalmente no existe un límite estricto para la cantidad de marcadores que puede agregar, pero considere el tamaño y la complejidad del documento para un rendimiento óptimo.

#### P: ¿Puedo personalizar la apariencia de los marcadores?

R: Sí, puede personalizar aún más la apariencia, el color, el estilo y otros atributos de los marcadores utilizando las funciones de Aspose.PDF.