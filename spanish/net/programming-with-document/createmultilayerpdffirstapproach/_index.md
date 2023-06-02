---
title: Crear primer enfoque de PDF multicapa
linktitle: Crear primer enfoque de PDF multicapa
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear documentos PDF multicapa utilizando el primer enfoque con Aspose.PDF para .NET. Agregue texto, imágenes y más para mejorar sus archivos PDF.
type: docs
weight: 70
url: /es/net/programming-with-document/createmultilayerpdffirstapproach/
---

En este tutorial, lo guiaremos a través del proceso de creación de un PDF multicapa utilizando el primer enfoque con Aspose.PDF para .NET. Este enfoque le permite agregar múltiples capas a su documento PDF. Siga la guía paso a paso a continuación:

## Paso 1: inicialice el documento PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## Paso 2: Agregar una nueva página al documento

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## Paso 3: Agrega un fragmento de texto a la página

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## Paso 4: personaliza el fragmento de texto

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## Paso 5: Agrega una imagen a la página

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## Paso 6: agregue un cuadro flotante a la página

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## Paso 7: Guarde el documento PDF resultante

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

¡Felicidades! Ha creado con éxito un documento PDF multicapa utilizando el primer enfoque con Aspose.PDF para .NET.

### Ejemplo de código fuente para crear un primer enfoque de PDF multicapa usando Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Ahora puede crear documentos PDF multicapa utilizando el primer enfoque con Aspose.PDF para .NET.
