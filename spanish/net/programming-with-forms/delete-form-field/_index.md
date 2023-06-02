---
title: Eliminar campo de formulario
linktitle: Eliminar campo de formulario
second_title: Referencia de API de Aspose.PDF para .NET
description: Elimine fácilmente los campos de formulario no deseados de sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-forms/delete-form-field/
---

En este tutorial, le mostraremos cómo eliminar un campo de formulario usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

Abra el documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Paso 3: eliminar un campo en particular

Elimine un campo de formulario en particular usando su nombre:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Paso 4: Guarda el documento editado

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Eliminar campo de formulario usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Eliminar un campo en particular por nombre
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Guardar documento modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo eliminar un campo de formulario usando Aspose.PDF para .NET. Siguiendo estos pasos, puede eliminar fácilmente los campos de formulario no deseados de sus documentos PDF utilizando Aspose.PDF.