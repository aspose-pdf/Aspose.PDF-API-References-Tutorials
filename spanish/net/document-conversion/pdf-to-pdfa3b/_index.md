---
title: PDF a PDFA3b
linktitle: PDF a PDFA3b
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a PDF/A-3b usando Aspose.PDF para .NET.
type: docs
weight: 150
url: /es/net/document-conversion/pdf-to-pdfa3b/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDF a formato PDF/A-3b usando Aspose.PDF para .NET. PDF/A-3b es un estándar ISO para incrustar archivos y datos en un documento PDF. Siguiendo los pasos a continuación, podrá convertir archivos PDF a formato PDF/A-3b.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: abrir el documento PDF de origen
En este paso, abriremos el archivo PDF de origen usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abra el documento PDF de origen
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: Convertir a PDF/A-3b
Después de abrir el archivo PDF, podemos proceder con la conversión al formato PDF/A-3b. Usa el siguiente código:

```csharp
// Convertir a formato PDF/A-3b
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

El código anterior convierte el archivo PDF a formato PDF/A-3b y elimina cualquier error de conversión.

## Paso 3: Guardar el archivo PDF/A-3b resultante
Una vez completada la conversión, debemos guardar el archivo PDF/A-3b resultante. Aquí está el último paso:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Guardar el documento de salida
pdfDocument.Save(dataDir);
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio deseado donde desea guardar el archivo de salida PDF/A-3b.

### Código fuente de ejemplo para PDF a PDFA3b usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Guardar documento de salida
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a formato PDF/A-3b usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir archivos PDF a formato PDF/A-3b. Esta característica es útil cuando desea incrustar archivos y datos adicionales en un documento PDF que cumple con el estándar PDF/A-3b.