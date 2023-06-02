---
title: Agregar capas
linktitle: Agregar capas
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar capas a archivos PDF usando Aspose.PDF para .NET. Guía paso a paso con tutoriales de código para crear y guardar archivos PDF en capas.
type: docs
weight: 20
url: /es/net/programming-with-document/addlayers/
---

Para agregar capas a un archivo PDF, utilizaremos Aspose.PDF para .NET. Esta biblioteca nos permite trabajar con archivos PDF en aplicaciones .NET de manera efectiva. Siga las instrucciones paso a paso a continuación para agregar capas usando Aspose.PDF para .NET.

## Paso 1: cree un nuevo documento PDF

 Comience por crear una nueva instancia de la`Document` clase proporcionada por Aspose.PDF para .NET. Esto servirá como el documento PDF donde agregaremos las capas.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Paso 2: agregue una página al documento

 A continuación, agregue una página al documento usando el`Add` metodo de la`Pages` colección en el`Document` clase.

```csharp
Page page = doc.Pages.Add();
```

## Paso 3: crear y agregar capas a la página

 Crear instancias de la`Layer` class para cada capa que desee agregar al archivo PDF. Especifique un identificador único y un nombre para cada capa.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

En este tutorial, hemos agregado tres capas con diferentes colores y nombres a la página.

## Paso 4: Guarde el archivo PDF

Guarde el archivo PDF modificado usando el`Save` metodo de la`Document` clase.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Este código guardará el archivo PDF modificado en el directorio especificado.

### Ejemplo de código fuente para agregar capas a páginas PDF usando Aspose.PDF para .NET

```csharp            
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Conclusión

En este artículo, proporcionamos una guía paso a paso para agregar capas a archivos PDF usando Aspose.PDF para .NET. Siguiendo las instrucciones y utilizando los tutoriales de código proporcionados, puede incorporar fácilmente capas en sus documentos PDF. Las capas le permiten organizar y controlar la visibilidad del contenido, proporcionando una experiencia más interactiva y personalizable para sus usuarios.