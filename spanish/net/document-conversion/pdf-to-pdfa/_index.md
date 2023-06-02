---
title: PDF a PDFA
linktitle: PDF a PDFA
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a PDFA usando Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/document-conversion/pdf-to-pdfa/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDF a formato PDF/A usando Aspose.PDF para .NET. El formato PDF/A es un estándar ISO que garantiza la conservación a largo plazo de los documentos electrónicos. Siguiendo los pasos a continuación, podrá convertir archivos PDF a formato PDF/A.

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
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: Conversión a formato PDF/A
Después de abrir el archivo PDF, podemos proceder con la conversión al formato PDF/A. Usa el siguiente código:

```csharp
// Convertir a documento compatible con PDF/A
// Durante el proceso de conversión, también se realiza la validación.
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

 El código anterior convierte el archivo PDF a formato PDF/A-1b y también realiza la validación durante el proceso de conversión. Cualquier error se registra en el`"log.xml"` archivo.

## Paso 3: Guardar el archivo PDF/A resultante
Una vez completada la conversión, debemos guardar el archivo PDF/A resultante. Aquí está el último paso:

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Guardar el documento de salida
pdfDocument.Save(dataDir);
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio deseado donde desea guardar el archivo PDF/A de salida.

### Código fuente de ejemplo para PDF a HTML usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// Convertir a documento compatible con PDF/A
// Durante el proceso de conversión, también se realiza la validación.
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Guardar documento de salida
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a formato PDF/A usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir archivos PDF a formato PDF/A. Esta característica es útil cuando desea garantizar el cumplimiento a largo plazo de sus documentos electrónicos.