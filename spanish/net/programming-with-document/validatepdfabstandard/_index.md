---
title: Validar PDFABEstándar
linktitle: Validar PDFABEstándar
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para validar documentos PDF con PDFABStandard con nuestra guía paso a paso y código de ejemplo.
type: docs
weight: 380
url: /es/net/programming-with-document/validatepdfabstandard/
---
Si está trabajando con documentos PDF en .NET, es posible que deba validar el PDF con un estándar como PDF/A. Aspose.PDF para .NET proporciona un método fácil de usar para validar un documento PDF con el estándar PDF/A-1a. En este artículo, proporcionaremos una guía paso a paso para explicar el siguiente código fuente de C# para obtener y validar el estándar PDF/A-1a mediante Aspose.PDF para .NET.

## Paso 1: establezca la ruta al directorio del documento

Antes de comenzar, debemos establecer la ruta al directorio donde se encuentra nuestro documento PDF. Guardaremos esta ruta en una variable llamada "dataDir".

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 2: Abra el documento PDF

A continuación, debemos abrir el documento PDF utilizando la clase "Documento" de Aspose.PDF para .NET. Guardaremos el documento en una variable llamada "pdfDocument".

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "ValidatePDFAStandard.pdf");
```

Reemplace "ValidatePDFAStandard.pdf" con el nombre de su documento PDF.

### Paso 3: Valide el PDF para PDF/A-1a

Finalmente, podemos validar el documento PDF contra el estándar PDF/A-1a utilizando el método "Validar" de la clase "Documento". Guardaremos el resultado de la validación en un archivo llamado "validation-result-A1A.xml".

```csharp
// Validar PDF para PDF/A-1a
pdfDocument.Validate(dataDir + "validation-result-A1A.xml", PdfFormat.PDF_A_1B);
```

El segundo parámetro "PdfFormat.PDF_A_1B" especifica que queremos validar el PDF con el estándar PDF/A-1a.

## Conclusión

En este artículo, explicamos cómo usar Aspose.PDF para .NET para validar un documento PDF con el estándar PDF/A-1a. Siguiendo los pasos anteriores, puede validar fácilmente sus documentos PDF contra varios estándares usando Aspose.PDF para .NET.

### Ejemplo de código fuente para Obtener Validar PDFABStandard usando Aspose.PDF para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Abrir documento
	Document pdfDocument = new Document(dataDir + "ValidatePDFAStandard.pdf");

	// Validar PDF para PDF/A-1a
	pdfDocument.Validate(dataDir + "validation-result-A1A.xml", PdfFormat.PDF_A_1B);
	
```
