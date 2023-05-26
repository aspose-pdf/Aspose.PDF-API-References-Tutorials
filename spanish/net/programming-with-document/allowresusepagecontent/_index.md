---
title: Permitir reutilizar el contenido de la página
linktitle: Permitir reutilizar el contenido de la página
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a optimizar archivos PDF habilitando la función "Permitir reutilizar el contenido de la página" usando Aspose.PDF para .NET. Reduzca el tamaño del archivo y mejore el rendimiento.
type: docs
weight: 50
url: /es/net/programming-with-document/allowresusepagecontent/
---

En este tutorial, explicaremos cómo habilitar la función "Permitir reutilizar el contenido de la página" usando Aspose.PDF para .NET. Esta función optimiza el documento PDF al reutilizar el contenido de la página, reducir el tamaño del archivo y mejorar el rendimiento. Siga la guía paso a paso a continuación:

## Paso 1: Cargue el documento PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Paso 2: establezca la opción AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Paso 3: optimizar el documento PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Paso 4: Guarde el documento actualizado

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Paso 5: compruebe la reducción del tamaño del archivo

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

¡Felicidades! Ha permitido con éxito la reutilización del contenido de la página en su documento PDF.

### Ejemplo de código fuente para Permitir la reutilización del contenido de la página usando Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Establecer la opción AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
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

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Ahora puede optimizar de manera efectiva sus documentos PDF al permitir la reutilización del contenido de la página.
