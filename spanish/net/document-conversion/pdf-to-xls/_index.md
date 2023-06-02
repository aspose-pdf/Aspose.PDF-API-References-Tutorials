---
title: PDF a XLS
linktitle: PDF a XLS
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para convertir PDF a XLS usando Aspose.PDF para .NET.
type: docs
weight: 200
url: /es/net/document-conversion/pdf-to-xls/
---

En este tutorial, lo guiaremos a través del proceso de conversión de un archivo PDF a formato XLS (Microsoft Excel) usando Aspose.PDF para .NET. Siguiendo los pasos a continuación, podrá convertir un archivo PDF a formato XLS.

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

## Paso 2: crear una instancia de las opciones de copia de seguridad de Excel
Después de cargar el archivo PDF, crearemos una instancia de las opciones de guardado de Excel. Usa el siguiente código:

```csharp
// Crear una instancia de un objeto ExcelSaveOptions
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Paso 3: Guardar el archivo XLS resultante
Ahora guardaremos el archivo PDF convertido en formato XLS. Usa el siguiente código:

```csharp
// Guarde la salida en formato XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 El código anterior guarda el archivo PDF convertido en formato XLS con el nombre de archivo`"PDFToXLS_out.xls"`.

### Código fuente de ejemplo para PDF a XLS usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Crear una instancia del objeto de opción ExcelSave
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Guarde la salida en formato XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de convertir un archivo PDF a formato XLS usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder convertir un archivo PDF a formato XLS. Esta característica es útil cuando desea extraer datos tabulares de un archivo PDF y usarlos en Microsoft Excel.