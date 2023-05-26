---
title: Eliminar flujos no utilizados
linktitle: Eliminar flujos no utilizados
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar secuencias no utilizadas de archivos PDF con Aspose.PDF para .NET. Nuestra guía paso a paso.
type: docs
weight: 270
url: /es/net/programming-with-document/removeunusedstreams/
---
En este ejemplo, analizaremos cómo eliminar secuencias no utilizadas de documentos PDF utilizando Aspose.PDF para .NET. Proporcionaremos una guía paso a paso sobre cómo hacer esto, incluido el código fuente completo con explicaciones.

## Paso 1: La ruta al directorio de documentos

La primera línea del código establece la ruta al directorio donde se encuentra su documento PDF. Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta del directorio real.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

La siguiente línea de código abre el documento PDF utilizando la biblioteca Aspose.PDF para .NET.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Paso 3: Establecer la opción RemoveUnusedStreams

El siguiente paso es establecer la opción RemoveUnusedStreams en verdadero. Esto eliminará las secuencias no utilizadas del documento PDF.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Paso 4: Optimice el documento PDF usando OptimizationOptions

Ahora que hemos configurado las opciones de optimización, podemos optimizar el documento PDF utilizando la siguiente línea de código.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Paso 5: Guardar documento actualizado

Finalmente, podemos guardar el documento actualizado utilizando el método Guardar de la clase Documento.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Eliminar secuencias no utilizadas usando Aspose.PDF para .NET

A continuación se muestra el código fuente de ejemplo para eliminar secuencias no utilizadas mediante Aspose.PDF para .NET.

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Abrir documento
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Establecer la opción RemoveUsedStreams
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedStreams = true
	};
	// Optimizar documento PDF usando OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Guardar documento actualizado
	pdfDocument.Save(dataDir);

```
