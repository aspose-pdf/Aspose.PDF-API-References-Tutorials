---
title: Obtener dimensiones de la página PDF
linktitle: Obtener dimensiones de la página PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: En este tutorial, explicamos cómo obtener las dimensiones de una página PDF y realizar manipulaciones con Aspose.PDF para .NET. Se proporcionan pasos detallados para guiarlo a través del proceso.
type: docs
weight: 60
url: /es/net/programming-with-pdf-pages/get-dimensions/
---
En este tutorial, lo guiaremos a través del proceso paso a paso para obtener las dimensiones de la página en un archivo PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo obtener las dimensiones de una página en un archivo PDF usando Aspose.PDF para .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde se encuentra su archivo PDF. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Abra el documento PDF
 Luego puede abrir el archivo PDF usando el`Document` clase de Aspose.PDF. Asegúrese de especificar la ruta correcta al archivo PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Paso 3: agregue una página en blanco (si es necesario)
 Si el documento PDF ya contiene páginas, puede saltar a una página existente usando el índice`1` (la primera página tiene un índice de 1). De lo contrario, puede agregar una nueva página al documento.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Paso 4: Obtenga las dimensiones de la página
 Ahora puede obtener las dimensiones de la página usando el`GetPageRect()` metodo de la`Page` objeto. Este método devuelve un`Rectangle` objeto que contiene las dimensiones de la página. Puede acceder al ancho y alto usando el`Width` y`Height` propiedades.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Paso 5: Girar la página
 Si desea rotar la página, puede utilizar el`Rotate` propiedad de la`Page`objeto. En este ejemplo, la página se gira 90 grados.

```csharp
page. Rotate = Rotate. on90;
```

## Paso 6: Obtenga las dimensiones de la página nuevamente
 Después de la rotación de la página, puede volver a obtener las dimensiones de la página usando el`GetPageRect()` método.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Ejemplo de código fuente para Obtener dimensiones usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Agrega una página en blanco al documento pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Obtener información sobre el alto y el ancho de la página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Girar la página en un ángulo de 90 grados
page.Rotate = Rotation.on90;
// Obtener información sobre el alto y el ancho de la página
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusión
En este tutorial, aprendimos cómo obtener las dimensiones de una página en un archivo PDF usando Aspose.PDF para .NET. Siguiendo los pasos proporcionados, puede extraer fácilmente las dimensiones de la página y realizar otras operaciones de manipulación de PDF. Aspose.PDF para .NET ofrece una gran flexibilidad para trabajar con archivos PDF y le permite desarrollar soluciones potentes y personalizadas.

Siéntase libre de explorar más a fondo la documentación de Aspose.PDF para descubrir todas las funciones que ofrece esta biblioteca.

### Preguntas frecuentes para obtener las dimensiones de la página PDF

#### P: ¿Cómo puedo obtener las dimensiones de una página específica en un archivo PDF?

R: Para obtener las dimensiones de una página específica en un archivo PDF, puede usar el`GetPageRect()` metodo de la`Page` objeto en Aspose.PDF para .NET. Este método devuelve un`Rectangle` objeto que contiene las dimensiones (ancho y alto) de la página.

####  P: ¿Qué significa el`GetPageRect(true)` method do in the provided C# source code?

 R: El`GetPageRect(true)` en el código fuente de C# proporcionado devuelve las dimensiones de la página después de aplicar cualquier rotación. Si se gira la página, el método devolverá las dimensiones de la página girada, que podrían ser diferentes de las dimensiones originales.

#### P: ¿Puedo obtener las dimensiones de todas las páginas del documento PDF usando Aspose.PDF para .NET?

 R: Sí, puede obtener las dimensiones de todas las páginas del documento PDF iterando a través de la`Pages` colección de la`Document` objeto y usando el`GetPageRect(true)` método para cada página.

#### P: ¿Cómo puedo determinar la orientación de una página (vertical u horizontal) en función de sus dimensiones?

R: Para determinar la orientación de una página en función de sus dimensiones, puede comparar el ancho y el alto de la página. Si el ancho es mayor que el alto, la página está en orientación horizontal y si el alto es mayor que el ancho, la página está en orientación vertical.

#### P: ¿Puedo modificar las dimensiones de una página usando Aspose.PDF para .NET?

 R: Sí, puede modificar las dimensiones de una página en Aspose.PDF para .NET. Después de obtener el`Rectangle` objeto que representa las dimensiones de la página, puede ajustar el ancho y la altura según sus requisitos y luego aplicar los cambios a la página.