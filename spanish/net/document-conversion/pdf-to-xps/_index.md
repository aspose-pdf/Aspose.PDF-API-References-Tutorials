---
title: PDF a XPS
linktitle: PDF a XPS
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a XPS utilizando Aspose.PDF para .NET.
type: docs
weight: 220
url: /es/net/document-conversion/pdf-to-xps/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDF a formato XPS (Especificación de papel XML) usando Aspose.PDF para .NET. El formato XPS es un formato de archivo basado en XML que se utiliza para representar documentos electrónicamente. Siguiendo los pasos a continuación, podrá convertir un archivo PDF a formato XPS.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Cargar el documento PDF
En este paso, cargaremos el archivo PDF de origen usando Aspose.PDF para .NET. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: crea una instancia de las opciones de guardado de XPS
Después de cargar el archivo PDF, crearemos una instancia de las opciones de guardado de XPS. Usa el siguiente código:

```csharp
// Crear una instancia de las opciones de guardado de XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Paso 3: Guardar el archivo XPS resultante
Ahora guardaremos el archivo PDF convertido en formato XPS. Usa el siguiente código:

```csharp
// Guarde el documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 El código anterior guarda el archivo PDF convertido en formato XPS con el nombre de archivo`"PDFToXPS_out.xps"`.


### Código fuente de ejemplo para PDF a XPS usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Crear una instancia de las opciones de guardado de XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Guarde el documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a formato XPS usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir un archivo PDF a formato XPS. Esta característica es útil cuando desea ver o imprimir documentos PDF en formato XPS.