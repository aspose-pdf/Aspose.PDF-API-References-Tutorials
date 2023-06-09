---
title: Agregar sello de página PDF
linktitle: Agregar sello de página PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar fácilmente un sello de página PDF a sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

En este tutorial, lo guiaremos paso a paso sobre cómo agregar un sello de página PDF a un documento PDF usando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente de C# proporcionado para agregar un sello personalizado a una página específica del documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abre el documento
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Crear el búfer de página

Ahora que ha cargado el documento PDF, puede crear el sello de página para agregar. Aquí está cómo hacerlo:

```csharp
// Crear el búfer de la página
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

El código anterior crea un nuevo búfer de página utilizando la primera página del documento PDF.

## Paso 4: Configuración de las propiedades del búfer de página

Antes de agregar el sello de página al documento PDF, puede configurar varias propiedades del sello, como el fondo, la posición, la rotación, etc. Así es como se hace:

```csharp
// Configurar las propiedades del búfer de la página
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

Puede ajustar estas propiedades según sus necesidades.

## Paso 5: agregar el sello de página al PDF

Ahora que el sello de página está listo, puede agregarlo a una página específica del documento PDF. Así es cómo:

```csharp
// Agregar búfer de página a una página específica
pdfDocument.Pages[1].AddStamp(pageStamp);
```

El código anterior agrega el sello de página a la primera página del documento PDF. Puede especificar otra página si es necesario.

## Paso 6: Guarde el documento de salida

Una vez que haya agregado el sello de página, puede guardar el documento PDF modificado. Así es cómo:

```csharp
// Guardar el documento de salida
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Agregar PDFPage Stamp usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

// Crear sello de página
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

// Agregar sello a una página en particular
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

El código anterior guarda el documento PDF editado en el directorio especificado.

## Conclusión

¡Felicidades! Aprendió a agregar un sello de página PDF usando Aspose.PDF para .NET. Ahora puede aplicar este conocimiento a sus propios proyectos para agregar sellos personalizados a páginas específicas de sus documentos PDF.
