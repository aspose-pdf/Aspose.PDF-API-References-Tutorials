---
title: Agregar anotación de enlace
linktitle: Agregar anotación de enlace
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo agregar la función Ink Annotation a documentos PDF en C# usando Aspose.PDF para .NET con una guía paso a paso y el código fuente completo.
type: docs
weight: 20
url: /es/net/annotations/addlnkannotation/
---
Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores realizar diversas operaciones de PDF. Una de esas operaciones es agregar anotaciones en tinta a documentos PDF. En este artículo, proporcionaremos una guía paso a paso para explicar el código fuente de C# para agregar Ink Annotation usando Aspose.PDF para .NET. ¡Empecemos!

## Comprensión de la función de anotación manuscrita de Aspose.PDF para .NET

Antes de profundizar en el código fuente de C#, primero comprendamos qué es Ink Annotation y sus usos.

Ink Annotation es una forma de dibujar anotaciones manuscritas de forma libre en documentos PDF. Le permite crear anotaciones con un lápiz óptico o un mouse. Esta función es útil en situaciones en las que necesita dibujar diagramas, bocetos u otros tipos de anotaciones.

## Paso 1: crear un nuevo documento

El primer paso para agregar Ink Annotation a un documento PDF es crear una nueva instancia de la clase Documento. Esto se logra utilizando el siguiente fragmento de código:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Aquí, creamos una nueva instancia de la clase Documento y le agregamos una nueva página.

## Paso 2: crear anotaciones manuscritas

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
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(trazo.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Aquí, primero creamos un rectángulo usando la clase System.Drawing.Rectangle y lo convertimos a Aspose.Pdf.Rectangle usando el método FromRect. Luego creamos una instancia de la clase InkAnnotation usando el rectángulo, una lista de puntos y la página donde se agrega la anotación.

Luego configuramos varias propiedades de InkAnnotation, como el título, el color, el estilo de tapa, el borde y la opacidad. Finalmente, agregamos la anotación a la página usando el método Annotations.Add.

## Paso 3: guardar el documento

El último paso es guardar el documento PDF con la anotación de tinta agregada. Esto se logra utilizando el siguiente fragmento de código:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Aquí, concatenamos el nombre del archivo de salida al directorio de datos y guardamos el documento usando el método Guardar.

### Código fuente de ejemplo para agregar anotaciones manuscritas usando Aspose.PDF para .NET

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
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(trazo.InkColor));
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

En este tutorial, exploramos cómo agregar anotaciones manuscritas a un documento PDF usando Aspose.PDF para .NET. Siguiendo la guía paso a paso y el código fuente C# proporcionado, los desarrolladores pueden implementar fácilmente la funcionalidad Ink Annotation en sus aplicaciones de procesamiento de PDF.

### Preguntas frecuentes

#### P: ¿Qué es una anotación manuscrita en un documento PDF?

R: Una anotación manuscrita en un documento PDF permite a los usuarios dibujar anotaciones manuscritas de forma libre utilizando un lápiz óptico o un mouse. Se utiliza comúnmente para agregar bocetos, diagramas u otras anotaciones a mano alzada a un PDF.

#### P: ¿Puedo personalizar la apariencia de Ink Annotation?

R: Sí, Aspose.PDF para .NET proporciona varias propiedades para personalizar la apariencia de Ink Annotation, como color, opacidad, estilo de tapa, ancho de borde y más. Los desarrolladores pueden ajustar estas propiedades para cumplir con sus requisitos específicos.

#### P: ¿Es posible agregar varias anotaciones manuscritas a una sola página PDF?

R: Sí, puede agregar varias anotaciones Ink a una sola página PDF usando Aspose.PDF para .NET. Cada anotación manuscrita puede tener su propio conjunto de puntos y una apariencia personalizada.

#### P: ¿Puedo agregar anotaciones manuscritas a documentos PDF existentes?

R: Sí, Aspose.PDF para .NET le permite agregar anotaciones manuscritas tanto a documentos PDF recién creados como a archivos PDF existentes. Puede abrir un PDF existente, agregar anotaciones manuscritas y guardar el documento actualizado.

#### P: ¿Cuáles son algunos casos de uso comunes de las anotaciones manuscritas en documentos PDF?

R: Las anotaciones manuscritas son útiles para una amplia gama de aplicaciones, incluida la adición de firmas o notas escritas a mano a formularios PDF, la anotación de planos arquitectónicos o dibujos de ingeniería y el marcado de documentos para revisión colaborativa.