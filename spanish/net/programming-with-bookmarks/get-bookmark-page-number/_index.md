---
title: Obtener número de página de marcador
linktitle: Obtener número de página de marcador
second_title: Referencia de API de Aspose.PDF para .NET
description: Obtenga fácilmente números de página de marcadores de sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-bookmarks/get-bookmark-page-number/
---

Recuperar números de página asociados con marcadores en un documento PDF puede ser útil para la navegación. Con Aspose.PDF para .NET, puede obtener fácilmente el número de página de los marcadores siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf.Facades;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea extraer los números de página del marcador. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: crea el editor de marcadores

 Ahora vamos a crear un`PdfBookmarkEditor` objeto para manipular los marcadores del documento. Usa el siguiente código:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Paso 4: Abra el archivo PDF

 En este paso, abrimos el archivo PDF usando el`BindPdf` método del editor de marcadores. Aquí está el código correspondiente:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Paso 5: Extraer marcadores

 Ahora vamos a extraer los marcadores del documento usando el`ExtractBookmarks` método del editor de marcadores. Aquí está el código correspondiente:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Paso 6: busque marcadores y obtenga números de página

 Finalmente, recorremos los marcadores extraídos y obtenemos los números de página asociados con cada marcador usando un`foreach` bucle. Aquí está el código correspondiente:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Ejemplo de código fuente para Obtener número de página de marcador usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear PDFEditor de marcadores
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Abrir archivo PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Extraer marcadores
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para obtener números de página de marcadores con Aspose.PDF para .NET. Puede usar este código para recuperar la información de navegación asociada con cada marcador en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de manipulación de marcadores.