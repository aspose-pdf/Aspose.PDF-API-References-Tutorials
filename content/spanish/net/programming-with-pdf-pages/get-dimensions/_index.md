---
title: Obtener dimensiones de página en formato PDF
linktitle: Obtener dimensiones de página en formato PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: En este tutorial, explicamos cómo obtener las dimensiones de una página PDF y realizar manipulaciones con Aspose.PDF para .NET. Se proporcionan pasos detallados para guiarlo a través del proceso.
type: docs
weight: 60
url: /es/net/programming-with-pdf-pages/get-dimensions/
---
En este tutorial, le guiaremos paso a paso por el proceso de obtención de las dimensiones de una página en un archivo PDF con Aspose.PDF para .NET. Le explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo obtener las dimensiones de una página en un archivo PDF con Aspose.PDF para .NET.

## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: Definir el directorio del documento
En primer lugar, debe establecer la ruta de acceso a su directorio de documentos. Esta es la ubicación donde se encuentra su archivo PDF. Reemplace "DIRECTORIO DE DOCUMENTOS" por la ruta correspondiente.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Abra el documento PDF
 Luego puedes abrir el archivo PDF usando el`Document` Clase de Aspose.PDF. Asegúrese de especificar la ruta correcta al archivo PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Paso 3: Agrega una página en blanco (si es necesario)
 Si el documento PDF ya contiene páginas, puede saltar a una página existente utilizando el índice`1` (la primera página tiene un índice de 1). De lo contrario, puede agregar una nueva página al documento.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Paso 4: Obtener las dimensiones de la página
 Ahora puedes obtener las dimensiones de la página usando el`GetPageRect()` método de la`Page` objeto. Este método devuelve un`Rectangle` objeto que contiene las dimensiones de la página. Puede acceder al ancho y alto mediante el botón`Width` y`Height` propiedades.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Paso 5: Girar la página
 Si desea rotar la página, puede utilizar el`Rotate` propiedad de la`Page`objeto. En este ejemplo, la página está rotada 90 grados.

```csharp
page. Rotate = Rotate. on90;
```

## Paso 6: Obtenga nuevamente las dimensiones de la página
 Después de rotar la página, puede obtener nuevamente las dimensiones de la página usando el`GetPageRect()` método.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Código fuente de muestra para obtener dimensiones con Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Agrega una página en blanco al documento PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Obtener información sobre la altura y el ancho de la página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Girar la página en un ángulo de 90 grados
page.Rotate = Rotation.on90;
// Obtener información sobre la altura y el ancho de la página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusión
En este tutorial, aprendimos a obtener las dimensiones de una página en un archivo PDF utilizando Aspose.PDF para .NET. Si sigue los pasos indicados, podrá extraer fácilmente las dimensiones de una página y realizar otras operaciones de manipulación de PDF. Aspose.PDF para .NET ofrece una gran flexibilidad para trabajar con archivos PDF y le permite desarrollar soluciones potentes y personalizadas.

Siéntase libre de explorar más a fondo la documentación de Aspose.PDF para descubrir todas las características que ofrece esta biblioteca.

### Preguntas frecuentes sobre cómo obtener las dimensiones de una página PDF

#### P: ¿Cómo puedo obtener las dimensiones de una página específica en un archivo PDF?

A: Para obtener las dimensiones de una página específica en un archivo PDF, puede utilizar el`GetPageRect()` método de la`Page` objeto en Aspose.PDF para .NET. Este método devuelve un`Rectangle` objeto que contiene las dimensiones (ancho y alto) de la página.

####  P: ¿Qué significa el`GetPageRect(true)` method do in the provided C# source code?

 A: El`GetPageRect(true)` El método del código fuente de C# proporcionado devuelve las dimensiones de la página después de aplicar cualquier rotación. Si se rota la página, el método devolverá las dimensiones de la página rotada, que podrían ser diferentes de las dimensiones originales.

#### P: ¿Puedo obtener las dimensiones de todas las páginas del documento PDF usando Aspose.PDF para .NET?

 R: Sí, puede obtener las dimensiones de todas las páginas del documento PDF iterando a través de la`Pages` colección de la`Document` objeto y utilizando el`GetPageRect(true)` método para cada página.

#### P: ¿Cómo puedo determinar la orientación de una página (vertical u horizontal) en función de sus dimensiones?

R: Para determinar la orientación de una página en función de sus dimensiones, puede comparar el ancho y la altura de la página. Si el ancho es mayor que la altura, la página está en orientación horizontal y, si la altura es mayor que el ancho, la página está en orientación vertical.

#### P: ¿Puedo modificar las dimensiones de una página usando Aspose.PDF para .NET?

 R: Sí, puede modificar las dimensiones de una página en Aspose.PDF para .NET. Después de obtener el`Rectangle` objeto que representa las dimensiones de la página, puede ajustar el ancho y la altura según sus requisitos y luego aplicar los cambios a la página.