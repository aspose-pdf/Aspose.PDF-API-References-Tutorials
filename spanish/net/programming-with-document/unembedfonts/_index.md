---
title: Fuentes desincrustadas
linktitle: Fuentes desincrustadas
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para obtener fuentes no incrustadas y optimizar archivos PDF. Una guía paso a paso.
type: docs
weight: 370
url: /es/net/programming-with-document/unembedfonts/
---
Aspose.PDF para .NET es una potente biblioteca que proporciona una amplia gama de funciones para trabajar con documentos PDF. Una de sus funciones es la de obtener fuentes incrustadas de un documento PDF. Esto puede ser útil si necesita extraer fuentes de un documento PDF y usarlas en otras aplicaciones.

proporcionaremos una guía paso a paso para explicar el siguiente código fuente de C# de la función de obtención de fuentes no incrustadas de Aspose.PDF para .NET.

## Paso 1: establezca la ruta al directorio del documento

Antes de comenzar, debemos establecer la ruta al directorio donde se encuentra nuestro documento PDF. Guardaremos esta ruta en una variable llamada "dataDir".

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 2: Abra el documento PDF

El primer paso es cargar el documento PDF que deseas para ello, utiliza el`Document` clase de Aspose.PDF para .NET. El siguiente fragmento de código muestra cómo cargar el documento PDF:

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Paso 3: Configure la opción UnembedFonts

 Para obtener fuentes desincrustadas del documento PDF, debe configurar el`UnembedFonts` opción a`true` . Esta opción está disponible en el`OptimizationOptions` clase. El siguiente fragmento de código muestra cómo configurar el`UnembedFonts` opción:

```csharp
// Establecer la opción UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Paso 4: Optimice el documento PDF

 Después de configurar el`UnembedFonts` opción, puede optimizar el documento PDF utilizando la`OptimizeResources` metodo de la`Document` clase. El siguiente fragmento de código muestra cómo optimizar el documento PDF:

```csharp
// Optimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Paso 5: Guarde el documento actualizado

 Una vez que el documento PDF está optimizado, puede guardar el documento actualizado usando el`Save` metodo de la`Document` clase. El siguiente fragmento de código muestra cómo guardar el documento actualizado:

```csharp
// Guardar documento actualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Paso 6: obtenga el tamaño de archivo original y reducido

 Finalmente, puede obtener el tamaño de archivo original y reducido del documento PDF usando el`FileInfo`clase de System.IO. El siguiente fragmento de código muestra cómo obtener el tamaño de archivo original y reducido:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Ejemplo de código fuente para obtener fuentes no incrustadas usando Aspose.PDF para .NET

Aquí está el código fuente de ejemplo completo para obtener fuentes incrustadas de un documento PDF usando Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Establecer la opción UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Optimizar documento PDF usando OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Guardar documento actualizado
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```
