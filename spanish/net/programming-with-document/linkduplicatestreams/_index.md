---
title: Vincular secuencias duplicadas
linktitle: Vincular secuencias duplicadas
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para la función .NET Link Duplicate Streams para optimizar sus documentos PDF con esta guía paso a paso.
type: docs
weight: 230
url: /es/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF para .NET es una biblioteca completa y potente que proporciona una variedad de características para trabajar con archivos PDF. Una de sus características clave es la capacidad de optimizar archivos PDF. En este artículo, explicaremos cómo usar la función Vincular flujos duplicados de Aspose.PDF para .NET para optimizar archivos PDF. Proporcionaremos instrucciones paso a paso e incluiremos un ejemplo de código fuente completo para que los desarrolladores puedan seguirlo fácilmente.

## Paso 1: Abrir el documento PDF

Para abrir el documento PDF usando Aspose.PDF para .NET, siga estos pasos:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

En el código anterior, reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta al directorio de su proyecto.

## Paso 2: Configuración de la opción LinkDuplicateStreams

Para configurar la opción LinkDuplicateStreams, siga estos pasos:

```csharp
// Establecer la opción LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

En el código anterior, creamos una nueva instancia de OptimizationOptions y configuramos la opción LinkDuplicateStreams en verdadero.

## Paso 3: Optimización del documento PDF

Para optimizar el documento PDF, siga estos pasos:

```csharp
// Optimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

En el código anterior, usamos el método OptimizeResources del objeto pdfDocument para optimizar el documento PDF usando OptimizationOptions que creamos anteriormente.

## Paso 4: guardar el documento actualizado

Para guardar el documento actualizado, siga estos pasos:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
```

En el código anterior, usamos el método Guardar del objeto pdfDocument para guardar el documento actualizado en un nuevo archivo llamado "OptimizeDocument_out.pdf" en el directorio del proyecto.

### Ejemplo de código fuente para secuencias duplicadas de enlaces usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Establecer la opción LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// Optimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
```
