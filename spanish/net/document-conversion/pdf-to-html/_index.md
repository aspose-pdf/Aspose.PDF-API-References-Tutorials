---
title: PDF a HTML
linktitle: PDF a HTML
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a HTML utilizando Aspose.PDF para .NET.
type: docs
weight: 130
url: /es/net/document-conversion/pdf-to-html/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDF a formato HTML usando Aspose.PDF para .NET. El formato PDF se usa comúnmente para ver y compartir documentos, mientras que el formato HTML se usa para crear páginas web. Siguiendo los pasos a continuación, podrá convertir archivos PDF a formato HTML.

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
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: conversión de PDF a HTML
Después de abrir el archivo PDF, podemos proceder con la conversión a formato HTML. Usa el siguiente código:

```csharp
// Guarda el archivo en formato HTML
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

 El código anterior convierte el archivo PDF a formato HTML y lo guarda como`"output_out.html"` archivo.

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"`con el directorio deseado donde desea guardar el archivo HTML de salida.

### Código fuente de ejemplo para PDF a HTML usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abra el documento PDF de origen
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

//Guarde el archivo en formato de documento MS
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a formato HTML usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir archivos PDF a formato HTML. Esta función es útil cuando desea incrustar contenido PDF en páginas web u otras aplicaciones compatibles con el formato HTML.

