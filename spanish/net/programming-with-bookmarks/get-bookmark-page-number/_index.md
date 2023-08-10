---
title: Obtener el número de página del marcador en un archivo PDF
linktitle: Obtener el número de página del marcador en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Obtenga fácilmente el número de página del marcador en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-bookmarks/get-bookmark-page-number/
---
La recuperación de números de página asociados con marcadores en un archivo PDF puede ser útil para la navegación. Con Aspose.PDF para .NET, puede obtener fácilmente el número de página de los marcadores siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf.Facades;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea extraer los números de página del marcador. Reemplazar`"YOUR DOCUMENT DIRECTORY"`en el siguiente código con la ruta real a su carpeta de documentos:

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

### Preguntas frecuentes para obtener el número de página del marcador en un archivo PDF

#### P: ¿Qué son los marcadores en un archivo PDF?

R: Los marcadores en un archivo PDF son ayudas de navegación que permiten a los usuarios saltar rápidamente a secciones o páginas específicas dentro del documento. Mejoran la experiencia del usuario al proporcionar accesos directos a contenido relevante.

#### P: ¿Por qué querría recuperar números de página de marcadores de un archivo PDF?

R: La recuperación de los números de página de los marcadores ayuda a los usuarios a navegar por un documento de manera más efectiva, proporcionando una indicación clara de adónde conduce cada marcador. Esto es particularmente útil para documentos más largos con múltiples secciones.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto de C#?

R: Para importar la biblioteca necesaria para su proyecto de C#, use la siguiente directiva de importación:

```csharp
using Aspose.Pdf.Facades;
```

Esta directiva le permite utilizar las clases y métodos proporcionados por Aspose.PDF para .NET.

#### P: ¿Cómo especifico la ruta a la carpeta de documentos?

 R: En el código fuente provisto, reemplace`"YOUR DOCUMENT DIRECTORY"`con la ruta real a la carpeta que contiene el archivo PDF del que desea extraer los números de página del marcador. Esto garantiza que el código pueda localizar el archivo PDF de destino.

#### P: ¿Cómo creo un editor de marcadores?

R: Para crear un editor de marcadores, use el siguiente código:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### P: ¿Cómo abro un archivo PDF para manipular marcadores?

R: Para abrir un archivo PDF para extraer información de marcadores, use el siguiente código:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Reemplazar`"GetBookmarks.pdf"` con el nombre real del archivo.

#### P: ¿Cómo extraigo marcadores del archivo PDF?

 R: Para extraer marcadores del archivo PDF, utilice el`ExtractBookmarks` método del editor de marcadores:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### P: ¿Cómo recupero y visualizo los números de página de marcadores?

 R: Recorra los marcadores extraídos usando un`foreach` bucle y acceder a la`PageNumber` propiedad de cada marcador para recuperar y mostrar su número de página asociado:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### P: ¿Puedo modificar las propiedades de los marcadores usando este enfoque?

 R: Si bien este tutorial se enfoca en recuperar números de página de marcadores, puede modificar otras propiedades de marcadores usando el mismo`Bookmark`objeto y propiedades asociadas.

#### P: ¿Cómo guardo el archivo PDF actualizado después de extraer la información del marcador?

R: La extracción de marcadores no modifica el archivo PDF original. Si desea guardar los cambios, puede hacerlo utilizando otros métodos proporcionados por Aspose.PDF para .NET.