---
title: Validar estándar PDF UA
linktitle: Validar estándar PDF UA
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para validar el estándar PDF/UA usando el código C#. Guía paso por paso.
type: docs
weight: 400
url: /es/net/programming-with-document/validatepdfuastandard/
---
Aspose.PDF para .NET es una potente biblioteca que proporciona varias funciones para trabajar con documentos PDF. Una de sus características es la capacidad de validar documentos PDF para el cumplimiento del estándar PDF/UA. En este artículo, proporcionaremos una guía paso a paso sobre cómo usar Aspose.PDF para .NET para obtener y validar el cumplimiento del estándar PDF/UA usando el código C#.

## Paso 1: Definición de la ruta del directorio de documentos

A continuación, debemos definir la ruta al directorio donde se encuentra nuestro documento PDF. Puede hacerlo agregando el siguiente fragmento de código:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos PDF.

## Paso 2: Abrir el documento PDF

Después de definir la ruta del directorio del documento, podemos abrir nuestro documento PDF usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");
```

 Este código crea un nuevo`Document` objeto de nuestro archivo PDF ubicado en el directorio especificado.

## Paso 3: Validación del PDF para PDF/UA

Ahora que hemos abierto el documento PDF, podemos usar Aspose.PDF para .NET para validar el documento para el cumplimiento de PDF/UA. El siguiente fragmento de código hará el trabajo:

```csharp
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
```

Este código valida el documento PDF para el cumplimiento del estándar PDF/UA y genera un informe de validación en el archivo XML especificado. El resultado de la validación se almacena en el`isValidPdfUa` variable, que es de tipo de datos booleano.

### Ejemplo de código fuente para Obtener Validar PDFUAstandard usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");

// Validar PDF para PDF/UA
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1); 
```
