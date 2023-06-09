---
title: Obtener marcadores
linktitle: Obtener marcadores
second_title: Referencia de API de Aspose.PDF para .NET
description: Marque fácilmente sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-bookmarks/get-bookmarks/
---

Recuperar marcadores de un documento PDF puede ser útil para analizar la estructura del documento y la información de navegación. Con Aspose.PDF para .NET, puede obtener fácilmente los marcadores siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea extraer los marcadores. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora vamos a abrir el documento PDF del que queremos extraer los marcadores usando el siguiente código:

```csharp
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
```

## Paso 4: Examinar marcadores

En este paso, iteraremos sobre todos los marcadores en el documento usando un`foreach` bucle. Para cada marcador, mostraremos información como el título, el estilo en cursiva, el estilo en negrita y el color. Aquí está el código correspondiente:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
}
```

### Ejemplo de código fuente para Obtener marcadores usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
// Recorrer todos los marcadores
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
}
```

## Conclusión

¡Felicidades! Ahora tienes una guía paso a paso para obtener marcadores con Aspose.PDF para .NET. Puede usar este código para analizar marcadores y extraer información asociada con cada marcador en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.