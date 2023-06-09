---
title: Rellenar campo de formulario
linktitle: Rellenar campo de formulario
second_title: Referencia de API de Aspose.PDF para .NET
description: Complete fácilmente los campos de formulario en sus documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-forms/fill-form-field/
---

En este tutorial, le mostraremos cómo completar un campo de formulario usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

Abra el documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Paso 3: obtener campo

Obtenga el campo de formulario deseado (en este ejemplo, estamos usando el campo "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Paso 4: cambie el valor del campo

Modifique el valor del campo con el valor deseado:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Paso 5: Guarde el documento actualizado

Guarde el documento PDF actualizado:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Rellenar campo de formulario con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// obtener un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modificar valor de campo
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo llenar un campo de formulario usando Aspose.PDF para .NET. Siguiendo estos pasos, puede cambiar fácilmente los valores de los campos de formulario en sus documentos PDF utilizando Aspose.PDF.