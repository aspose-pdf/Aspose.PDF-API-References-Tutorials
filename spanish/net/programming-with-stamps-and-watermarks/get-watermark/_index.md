---
title: Obtener marca de agua
linktitle: Obtener marca de agua
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer marcas de agua de sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-stamps-and-watermarks/get-watermark/
---
En este tutorial, lo guiaremos paso a paso sobre cómo obtener una marca de agua de un documento PDF utilizando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente de C# proporcionado para iterar a través de los artefactos de una página específica y obtener el tipo de marca de agua, el texto y la ubicación.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abre el documento PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Obtener la marca de agua

Ahora que ha cargado el documento PDF, puede recorrer los artefactos de página específicos para obtener la información de la marca de agua. Así es cómo:

```csharp
// Explore los artefactos y obtenga el subtipo, el texto y la ubicación de la marca de agua
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

El código anterior recorre todos los artefactos en la primera página del documento PDF y muestra el subtipo, el texto y el rectángulo (ubicación) de cada marca de agua encontrada.

### Ejemplo de código fuente para Obtener marca de agua con Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Repita y obtenga el tipo de bañera, el texto y la ubicación del artefacto
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Conclusión

¡Felicidades! Ha aprendido a obtener información de marcas de agua de un documento PDF utilizando Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para analizar y procesar marcas de agua en sus documentos PDF.
