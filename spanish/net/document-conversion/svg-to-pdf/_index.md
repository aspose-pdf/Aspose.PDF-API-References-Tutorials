---
title: SVG a PDF
linktitle: SVG a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Conversión fácil y rápida de SVG a PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 280
url: /es/net/document-conversion/svg-to-pdf/
---

Este tutorial lo guiará a través de los pasos para convertir un archivo SVG a un archivo PDF usando Aspose.PDF para .NET. Aspose.PDF ofrece una solución simple y efectiva para convertir archivos SVG a PDF mientras conserva la calidad y el diseño del contenido. Siga los pasos a continuación para realizar esta conversión.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: cargando el archivo SVG
 El primer paso es cargar el archivo SVG en un`Document`objeto usando la opción de carga SVG (`SvgLoadOptions`). Usa el siguiente código:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear una instancia del objeto LoadOption usando la opción de carga SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Crear objeto de documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo SVG.

## Paso 2: Convertir a PDF
 El segundo paso es convertir el documento SVG a un documento PDF usando el`Save` metodo de la`Document` objeto. Usa el siguiente código:

```csharp
// Guarde el documento PDF resultante
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Asegúrese de especificar la ruta y el nombre de archivo deseados para el archivo PDF resultante.

### Código fuente de ejemplo para SVG a PDF usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear una instancia del objeto LoadOption usando la opción de carga SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Crear objeto de documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Guarde el documento PDF resultante
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo convertir un archivo SVG a un archivo PDF usando Aspose.PDF para .NET. Siguiendo los pasos dados anteriormente, puede realizar fácilmente esta conversión. Utilice este método para convertir sus archivos SVG a PDF y disfrute de la flexibilidad y calidad de Aspose.PDF.