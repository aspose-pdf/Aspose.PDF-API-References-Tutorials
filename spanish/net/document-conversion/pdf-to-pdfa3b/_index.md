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

### Código fuente de ejemplo para PDF a PDFA3b usando Aspose.PDF para .NET

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

### Preguntas frecuentes

#### P: ¿Qué es PDF/A-3b y en qué se diferencia de otros estándares PDF/A?

R: PDF/A-3b es un estándar ISO que permite incrustar archivos y datos en un documento PDF, haciéndolo autónomo y asegurando la conservación a largo plazo. A diferencia de otros estándares PDF/A, como PDF/A-1 y PDF/A-2, PDF/A-3b permite la inclusión de archivos y datos adicionales dentro del documento PDF. Esta característica lo hace adecuado para archivar e intercambiar documentos complejos e interactivos.

#### P: ¿Puedo incluir varios archivos y datos en un documento PDF/A-3b?

R: Sí, una de las principales ventajas de PDF/A-3b es su capacidad para incluir múltiples archivos y datos dentro del documento PDF. Puede incrustar varios tipos de archivos, como XML, hojas de cálculo, imágenes u otros archivos PDF, junto con el contenido PDF principal. Como resultado, el documento PDF/A-3b se convierte en un paquete autónomo que contiene todos los elementos necesarios.

#### P: ¿Qué sucede si hay errores durante el proceso de conversión de PDF a PDF/A-3b?

 R: Al convertir un PDF a formato PDF/A-3b con Aspose.PDF para .NET, tiene control sobre cómo se manejan los errores. El`Convert` métodos`ConvertErrorAction` El parámetro determina la acción a tomar cuando se encuentran errores. En el ejemplo de código proporcionado, el`ConvertErrorAction.Delete` se utiliza el parámetro, lo que significa que cualquier error encontrado durante la conversión resultará en la eliminación de las páginas con errores.

#### P: ¿Es PDF/A-3b adecuado para la conservación de documentos a largo plazo?

R: Sí, PDF/A-3b está diseñado específicamente para la conservación a largo plazo de documentos electrónicos. Al incorporar archivos y datos adicionales, garantiza que todos los componentes necesarios se incluyan en el propio documento PDF, lo que reduce el riesgo de pérdida de información o dependencias externas con el tiempo. Esta característica lo hace adecuado para archivar documentos de una manera que garantiza la accesibilidad y la consistencia a largo plazo.