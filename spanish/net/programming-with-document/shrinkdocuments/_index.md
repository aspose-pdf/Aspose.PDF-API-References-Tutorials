---
title: Reducir documentos
linktitle: Reducir documentos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para reducir documentos PDF con esta guía paso a paso.
type: docs
weight: 350
url: /es/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, manipular y optimizar documentos PDF mediante C#. En este tutorial, veremos un ejemplo de cómo usar Aspose.PDF para reducir un documento PDF.

## Paso 1: Cargar el documento PDF

 Para reducir un documento PDF, primero debemos cargarlo en nuestra aplicación C# usando Aspose.PDF. En el siguiente código, especificamos la ruta a nuestro documento PDF y creamos una nueva instancia del`Document` clase.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## Paso 2: Reducir el documento PDF

 Una vez hayamos cargado el documento PDF, podemos utilizar el`OptimizeResources` metodo de la`Document`class para optimizar el documento y reducir potencialmente su tamaño. Tenga en cuenta que este método no puede garantizar la reducción del tamaño del documento, ya que algunos documentos PDF ya pueden estar muy optimizados.

```csharp
// Optimizar documento PDF. Tenga en cuenta, sin embargo, que este método no puede garantizar la reducción del documento
pdfDocument.OptimizeResources();
```

## Paso 3: Guardar el documento PDF actualizado

 Después de haber optimizado el documento PDF, podemos guardar la versión actualizada en un nuevo archivo usando el`Save` metodo de la`Document` clase. En el siguiente código, especificamos la ruta y el nombre del archivo de salida.

```csharp
// Especificar la ruta del archivo de salida
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(outputFilePath);
```

### Ejemplo de código fuente para reducir documentos usando Aspose.PDF para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Abrir documento
	Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
	// Optimizar documento PDF. Tenga en cuenta, sin embargo, que este método no puede garantizar la reducción del documento
	pdfDocument.OptimizeResources();
	dataDir = dataDir + "ShrinkDocument_out.pdf";
	// Guardar documento actualizado
	pdfDocument.Save(dataDir);
	
```
