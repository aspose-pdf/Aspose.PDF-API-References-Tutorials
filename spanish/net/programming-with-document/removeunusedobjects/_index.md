---
title: Eliminar objetos no utilizados
linktitle: Eliminar objetos no utilizados
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para eliminar objetos no utilizados de documentos PDF con esta guía paso a paso.
type: docs
weight: 260
url: /es/net/programming-with-document/removeunusedobjects/
---
Si está buscando una manera de eliminar objetos no utilizados en sus documentos PDF utilizando Aspose.PDF para .NET, está en el lugar correcto. Esta guía paso a paso le mostrará cómo utilizar el código fuente de C# proporcionado para realizar esta tarea.

## Paso 1: establecer la ruta del directorio

Primero, debe establecer la ruta a su directorio de documentos reemplazando "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

A continuación, debe abrir el documento PDF que desea optimizar utilizando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Paso 3: Establecer la opción RemoveUnusedObjects

Para eliminar objetos no utilizados en su documento PDF, debe configurar la opción RemoveUnusedObjects en "true" de la siguiente manera:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## Paso 4: Optimice el documento PDF usando OptimizationOptions

Ahora, puede optimizar su documento PDF utilizando el método OptimizeResources con las opciones de optimización que acaba de configurar:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Paso 5: Guarde el documento actualizado

Finalmente, puede guardar el documento actualizado con el siguiente código:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

¡Eso es todo! Ha eliminado con éxito los objetos no utilizados de su documento PDF utilizando Aspose.PDF para .NET.

### Ejemplo de código fuente para Eliminar objetos no utilizados usando Aspose.PDF para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Abrir documento
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Establecer la opción RemoveUsedObject
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedObjects = true
	};
	// Optimizar documento PDF usando OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Guardar documento actualizado
	pdfDocument.Save(dataDir);

```
