---
title: Texto en pie de página
linktitle: Texto en pie de página
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar texto en el pie de página de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 180
url: /es/net/programming-with-stamps-and-watermarks/text-in-footer/
---
En este tutorial, vamos a aprender cómo agregar texto en el pie de página de un documento PDF utilizando Aspose.PDF para .NET. Siga los pasos a continuación:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 4: Crear texto de pie de página

Cree un nuevo sello de texto con el texto que desea agregar en el pie de página:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Puede personalizar el texto cambiando sus propiedades, como el margen inferior, la alineación horizontal y la alineación vertical.

## Paso 5: agregue texto de pie de página a todas las páginas

Revise todas las páginas del documento PDF y agregue el sello de texto en el pie de página:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Paso 6: Guardar el documento PDF

Una vez que se haya agregado el texto de pie de página en todas las páginas, guarde el documento PDF actualizado:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde desea guardar el documento PDF.

### Ejemplo de código fuente para Textin Footer usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Crear pie de página
TextStamp textStamp = new TextStamp("Footer Text");

// Establecer propiedades del sello
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Agregar pie de página en todas las páginas
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Guardar archivo PDF actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Conclusión

¡Felicidades! Ha aprendido a agregar texto en el pie de página de un documento PDF utilizando Aspose.PDF para .NET. Ahora puede personalizar sus pies de página agregando texto adicional a sus documentos PDF.
