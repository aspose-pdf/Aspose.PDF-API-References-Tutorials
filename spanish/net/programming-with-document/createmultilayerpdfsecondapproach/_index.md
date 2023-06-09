---
title: Crear segundo enfoque de PDF multicapa
linktitle: Crear segundo enfoque de PDF multicapa
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear un PDF multicapa con Aspose.PDF para .NET. Guía paso a paso con código fuente para crear PDF dinámicos con texto e imágenes.
type: docs
weight: 80
url: /es/net/programming-with-document/createmultilayerpdfsecondapproach/
---

En este tutorial, exploraremos cómo crear un PDF multicapa utilizando el segundo enfoque en Aspose.PDF para .NET. Proporcionaremos una guía paso a paso con explicaciones detalladas e incluiremos el código fuente completo. Siguiendo este tutorial, podrá generar documentos PDF con múltiples capas utilizando la biblioteca Aspose.PDF en sus aplicaciones .NET.

Ahora, comencemos con la guía paso a paso.

## Paso 1: configurar el entorno

Para empezar, abra Visual Studio y cree un nuevo proyecto de C#. Asegúrese de haber hecho referencia a la biblioteca Aspose.PDF en su proyecto. Una vez que haya configurado el entorno, estará listo para continuar con el siguiente paso.

## Paso 2: inicializar variables

En este paso, inicializaremos las variables necesarias. Necesitamos establecer la ruta al directorio del documento y definir las variables de color para las capas PDF. Aquí está el fragmento de código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## Paso 3: crea un documento PDF

A continuación, crearemos una nueva instancia de la clase Aspose.Pdf.Document, que representa un documento PDF. Aquí está el fragmento de código:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Paso 4: agregue una página al documento

En este paso, agregaremos una nueva página al documento PDF. Aquí está el fragmento de código:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Paso 5: agregue texto a la página

Ahora, agregaremos un fragmento de texto a la página. El texto se mostrará como un segmento de párrafo 3 con un color rojo. Aquí está el fragmento de código:

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## Paso 6: agrega una imagen a la página

En este paso, agregaremos una imagen a la página. La imagen se posicionará como un cuadro flotante con un tamaño específico. Aquí está el fragmento de código:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## Paso 7: Guarda el PDF

En este paso, guardaremos el PDF en un archivo.

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### Código fuente de ejemplo para crear un segundo enfoque de PDF multicapa utilizando Aspose.PDF para .NET.

```csharp   
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

## Conclusión

En este artículo, hemos aprendido a crear un PDF multicapa utilizando el segundo enfoque de Aspose.PDF para .NET. Le proporcionamos instrucciones paso a paso y el código fuente completo necesario para crear un PDF multicapa.