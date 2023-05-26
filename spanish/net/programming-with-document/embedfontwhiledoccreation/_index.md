---
title: Incrustar fuente durante la creación de documentos
linktitle: Incrustar fuente durante la creación de documentos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a incrustar una fuente mientras crea un documento PDF con Aspose.PDF para .NET. Asegurar la visualización correcta en diferentes dispositivos.
type: docs
weight: 140
url: /es/net/programming-with-document/embedfontwhiledoccreation/
---

En este tutorial, discutiremos cómo incrustar una fuente al crear un documento PDF usando Aspose.PDF para .NET. Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, editar y manipular documentos PDF mediante programación. Esta biblioteca proporciona una amplia gama de funciones para trabajar con documentos PDF, incluida la adición de texto, imágenes, tablas y mucho más. Incrustar fuentes al crear un documento PDF es un requisito común para los desarrolladores que desean asegurarse de que el documento PDF se muestre correctamente en diferentes dispositivos, independientemente de si las fuentes requeridas están instaladas en esos dispositivos o no.

## Paso 1: Cree una nueva aplicación de consola C#
Para comenzar, cree una nueva aplicación de consola C# en Visual Studio. Puedes nombrarlo como quieras. Una vez que se crea el proyecto, debe agregar una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importe el espacio de nombres Aspose.PDF
Agregue la siguiente línea de código en la parte superior de su archivo C# para importar el espacio de nombres Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Paso 3: Crea una instancia de un objeto PDF
Crea una instancia de un objeto Pdf llamando a su constructor vacío:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Paso 4: crea una sección en el objeto PDF
Cree una sección en el objeto Pdf:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Paso 5: agregue texto a la sección
Agregar texto a la sección:

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## Paso 6: Establece la fuente e insértala
Establece la fuente e insértala:

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## Paso 7: Guarde el documento PDF
Una vez que haya incrustado la fuente al crear el documento PDF, debe guardar el documento:

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);
```

### Código fuente de ejemplo para fuente incrustada durante la creación de documentos usando Aspose.PDF para .NET

```csharp

            
            // La ruta al directorio de documentos.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Crea una instancia del objeto Pdf llamando a su constructor vacío
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

            // Crear una sección en el objeto Pdf
            Aspose.Pdf.Page page = doc.Pages.Add();

            Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

            Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
            Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
            ts.Font = FontRepository.FindFont("Arial");
            ts.Font.IsEmbedded = true;
            segment.TextState = ts;
            fragment.Segments.Add(segment);
            page.Paragraphs.Add(fragment);

            dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
            // Guardar documento PDF
            doc.Save(dataDir);
            
            
        
```

## Conclusión
En este tutorial, hemos discutido cómo incrustar una fuente al crear un documento PDF usando Aspose.PDF para .NET. Aspose.PDF para .NET proporciona una API simple y fácil de usar para trabajar con documentos PDF, lo que incluye agregar e incrustar fuentes. Incrustar fuentes al crear un documento PDF es un paso importante para garantizar que el documento se muestre correctamente en diferentes dispositivos, independientemente de si las fuentes requeridas están instaladas en esos dispositivos o no.

