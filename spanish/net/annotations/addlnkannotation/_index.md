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

## Conclusión

En este tutorial, exploramos cómo agregar anotaciones de tinta a un documento PDF usando Aspose.PDF para .NET. Al seguir la guía paso a paso y el código fuente de C# proporcionado, los desarrolladores pueden implementar fácilmente la funcionalidad de anotación de tinta en sus aplicaciones de procesamiento de PDF.

### Preguntas frecuentes

#### P: ¿Qué es una anotación de tinta en un documento PDF?

R: Una anotación de tinta en un documento PDF permite a los usuarios dibujar anotaciones de tinta de forma libre con un lápiz óptico o un mouse. Se usa comúnmente para agregar bocetos, diagramas u otras anotaciones a mano alzada a un PDF.

#### P: ¿Puedo personalizar la apariencia de la anotación de tinta?

R: Sí, Aspose.PDF para .NET proporciona varias propiedades para personalizar la apariencia de la anotación de tinta, como el color, la opacidad, el estilo de tapa, el ancho del borde y más. Los desarrolladores pueden ajustar estas propiedades para cumplir con sus requisitos específicos.

#### P: ¿Es posible agregar múltiples anotaciones de tinta a una sola página PDF?

R: Sí, puede agregar múltiples anotaciones de tinta a una sola página PDF usando Aspose.PDF para .NET. Cada anotación de tinta puede tener su propio conjunto de puntos y apariencia personalizada.

#### P: ¿Puedo agregar anotaciones de tinta a documentos PDF existentes?

R: Sí, Aspose.PDF para .NET le permite agregar anotaciones de tinta tanto a documentos PDF recién creados como a archivos PDF existentes. Puede abrir un PDF existente, agregar anotaciones de tinta y guardar el documento actualizado.

#### P: ¿Cuáles son algunos casos de uso comunes para las anotaciones de tinta en documentos PDF?

R: Las anotaciones de tinta son útiles para una amplia gama de aplicaciones, incluida la adición de firmas o notas escritas a mano en formularios PDF, la anotación de planos arquitectónicos o dibujos de ingeniería y el marcado de documentos para revisión colaborativa.