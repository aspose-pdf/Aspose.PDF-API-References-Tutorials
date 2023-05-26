---
title: Determinar el progreso
linktitle: Determinar el progreso
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a determinar el progreso del proceso de conversión de un documento PDF utilizando Aspose.PDF para .NET con esta guía paso a paso y código de ejemplo.
type: docs
weight: 110
url: /es/net/programming-with-document/determineprogress/
---

Aspose.PDF para .NET proporciona una función que le permite determinar el progreso del proceso de conversión de un documento PDF. En este tutorial, proporcionaremos una guía paso a paso sobre cómo implementar esta característica usando C# y Aspose.PDF para .NET.

## Paso 1: Cargar el documento PDF

El primer paso es cargar el documento PDF que desea convertir. Para este tutorial, utilizaremos el archivo "AddTOC.pdf". Reemplace la ruta a este archivo con la ruta a su propio documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
```

## Paso 2: configurar el controlador de progreso personalizado

 A continuación, debemos configurar el controlador de progreso personalizado que se llamará durante el proceso de conversión. En este tutorial, usaremos el`ConversionProgressEventHandler` delegado proporcionado por Aspose.PDF para .NET.

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);
```

## Paso 3: Guardar el documento PDF

 Finalmente, necesitamos guardar el documento PDF usando el`Save()` metodo de la`Document`objeto. Pasaremos el controlador de progreso personalizado que configuramos en el paso anterior como parámetro.

```csharp
dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
```

## Paso 4: Implementando el controlador de progreso

 Para implementar el controlador de progreso, necesitamos definir un método que tome un solo parámetro de tipo`ConversionProgressEventArgs`. Este método se llamará durante el proceso de conversión para informar el progreso de la conversión.

```csharp
private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

### Ejemplo de código fuente para determinar el progreso usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);

dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
Console.ReadLine();

private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

## Conclusión

En este tutorial, proporcionamos una guía paso a paso sobre cómo determinar el progreso del proceso de conversión de un documento PDF utilizando Aspose.PDF para .NET. También proporcionamos un ejemplo de código que puede usar como referencia al implementar esta característica en su propia aplicación.