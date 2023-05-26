---
title: Añadir anotación lnk
linktitle: Añadir anotación lnk
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar la función de anotación de tinta a documentos PDF en C# usando Aspose.PDF para .NET con una guía paso a paso y el código fuente completo.
type: docs
weight: 20
url: /es/net/annotations/addlnkannotation/
---
Aspose.PDF para .NET es una poderosa biblioteca que permite a los desarrolladores realizar varias operaciones de PDF. Una de esas operaciones es agregar anotaciones de tinta a los documentos PDF. En este artículo, proporcionaremos una guía paso a paso para explicar el código fuente de C# para agregar Ink Annotation usando Aspose.PDF para .NET. ¡Empecemos!

## Descripción de la función de anotación de tinta de Aspose.PDF para .NET

Antes de sumergirnos en el código fuente de C#, primero comprendamos qué es Ink Annotation y sus usos.

Ink Annotation es una forma de dibujar anotaciones de tinta de forma libre en documentos PDF. Le permite crear anotaciones con un lápiz óptico o un mouse. Esta función es útil en situaciones en las que necesita dibujar diagramas, bocetos u otros tipos de anotaciones.

## Paso 1: Creación de un nuevo documento

El primer paso para agregar Ink Annotation a un documento PDF es crear una nueva instancia de la clase Document. Esto se logra utilizando el siguiente fragmento de código:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Aquí, creamos una nueva instancia de la clase Document y le agregamos una nueva página.

## Paso 2: Creación de anotaciones de tinta

El siguiente paso es crear una instancia de la clase InkAnnotation. Esto se hace usando el siguiente fragmento de código:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Aquí, primero creamos un rectángulo usando la clase System.Drawing.Rectangle y lo convertimos a Aspose.Pdf.Rectangle usando el método FromRect. Luego creamos una instancia de la clase InkAnnotation usando el rectángulo, una lista de puntos y la página donde se agrega la anotación.

Luego establecemos varias propiedades de InkAnnotation, como el título, el color, el estilo de tapa, el borde y la opacidad. Finalmente, agregamos la anotación a la página usando el método Annotations.Add.

## Paso 3: Guardar el documento

El paso final es guardar el documento PDF con la anotación de tinta agregada. Esto se logra utilizando el siguiente fragmento de código:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Aquí, concatenamos el nombre del archivo de salida al directorio de datos y guardamos el documento usando el método Guardar.

### Ejemplo de código fuente para agregar anotaciones de tinta usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Guardar archivo de salida
doc.Save(dataDir);
```