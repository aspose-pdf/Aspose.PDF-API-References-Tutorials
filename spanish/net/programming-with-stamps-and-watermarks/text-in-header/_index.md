---
title: Texto en encabezado
linktitle: Texto en encabezado
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar texto en el encabezado de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 190
url: /es/net/programming-with-stamps-and-watermarks/text-in-header/
---
En este tutorial, vamos a aprender cómo agregar texto en el encabezado de un documento PDF utilizando Aspose.PDF para .NET. Siga los pasos a continuación:

## Paso 1: Preparación del proyecto

Asegúrese de haber instalado Aspose.PDF para .NET y creado un proyecto C#.

## Paso 2: Importación de espacios de nombres

Agregue los siguientes espacios de nombres a su archivo fuente de C#:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: Abrir el documento

Abra el documento PDF existente utilizando la ruta provista:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 4: Creación de texto de encabezado

Cree un nuevo sello de texto con el texto que desea agregar en el encabezado:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Puede personalizar el texto cambiando sus propiedades, como el margen superior, la alineación horizontal y la alineación vertical.

## Paso 5: agregue texto de encabezado a todas las páginas

Revise todas las páginas del documento PDF y agregue el sello de texto en el encabezado:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Paso 6: Guardar el documento PDF

Una vez que se haya agregado el texto del encabezado en todas las páginas, guarde el documento PDF actualizado:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde desea guardar el documento PDF.

### Ejemplo de código fuente para Textin Header usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Crear encabezado
TextStamp textStamp = new TextStamp("Header Text");

// Establecer propiedades del sello
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Agregar encabezado en todas las páginas
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Guardar documento actualizado
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Conclusión

¡Felicidades! Ha aprendido a agregar texto en el encabezado de un documento PDF utilizando Aspose.PDF para .NET. Ahora puede personalizar sus encabezados agregando texto adicional a sus documentos PDF.
