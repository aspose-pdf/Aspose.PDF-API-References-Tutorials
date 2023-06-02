---
title: Fuente de campo de formulario 14
linktitle: Fuente de campo de formulario 14
second_title: Referencia de API de Aspose.PDF para .NET
description: Configure fácilmente la fuente de los campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-forms/form-field-font-14/
---

En este tutorial, le mostraremos cómo configurar la fuente de un campo de formulario usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

Abra el documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Paso 3: Obtener un campo de formulario en particular

Obtenga el campo de formulario deseado (en este ejemplo, estamos usando el campo "textbox1"):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Paso 4: crea un objeto de fuente

Cree un objeto de fuente para la nueva fuente que desea usar (por ejemplo, "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Paso 5: Configure la información de fuente para el campo de formulario

Configure la información de fuente para el campo de formulario utilizando la fuente creada anteriormente:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Paso 6: Guarde el documento actualizado

Guarde el documento PDF actualizado:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Ejemplo de código fuente para Form Field Font 14 usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
//Obtener un campo de formulario particular del documento
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Crear objeto de fuente
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Establecer la información de fuente para el campo de formulario
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(font, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo configurar la fuente de un campo de formulario usando Aspose.PDF para .NET. Siguiendo estos pasos, puede especificar fácilmente la fuente y el tamaño de fuente para los campos de formulario en sus documentos PDF usando Aspose.PDF.