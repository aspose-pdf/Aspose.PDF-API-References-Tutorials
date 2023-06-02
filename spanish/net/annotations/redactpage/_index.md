---
title: Redactar página
linktitle: Redactar página
second_title: Referencia de API de Aspose.PDF para .NET
description: Este artículo explica cómo redactar una página PDF con Aspose.PDF para .NET, e incluye instrucciones paso a paso y código fuente de ejemplo.
type: docs
weight: 120
url: /es/net/annotations/redactpage/
---
Si está buscando redactar información confidencial de un documento PDF utilizando Aspose.PDF para .NET, ¡está de suerte! Aquí hay una guía paso a paso para comenzar:

## Paso 1: en el código, establezca la ruta al directorio donde se encuentra su documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 3: Cree una instancia de RedactionAnnotation para una región de página específica:

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## Paso 4: establezca el color de relleno, el color del borde y el color del texto de la anotación de redacción:

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## Paso 5: configure el texto que se imprimirá en la anotación de redacción y su alineación:

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Paso 6: repita el texto superpuesto sobre la anotación de redacción:

```csharp
annot.Repeat = true;
```

## Paso 7: agregue la anotación a la colección de anotaciones de la primera página:

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## Paso 8: acople la anotación y elimine el contenido de la página, es decir, elimine el texto y las imágenes debajo de la anotación redactada:

```csharp
annot.Redact();
```

## Paso 9: establezca la ruta y el nombre del archivo PDF de salida:

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## Paso 10: guarde el documento PDF con la página redactada:

```csharp
doc.Save(dataDir);
```

¡Eso es todo! Ha redactado con éxito una página de su documento PDF utilizando Aspose.PDF para .NET.

### Código fuente de ejemplo para Redact Page usando Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document doc = new Document(dataDir + "input.pdf");

// Crear una instancia de RedactionAnnotation para una región de página específica
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// Texto que se imprimirá en la anotación redactada
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Repat Texto superpuesto sobre anotación redactada
annot.Repeat = true;
// Agregar anotación a la colección de anotaciones de la primera página
doc.Pages[1].Annotations.Add(annot);
//Aplana la anotación y redacta el contenido de la página (es decir, elimina el texto y la imagen
// Bajo anotación redactada)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```