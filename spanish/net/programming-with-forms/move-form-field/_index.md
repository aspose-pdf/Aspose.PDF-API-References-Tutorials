---
title: Mover campo de formulario
linktitle: Mover campo de formulario
second_title: Referencia de API de Aspose.PDF para .NET
description: Mueva fácilmente los campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 200
url: /es/net/programming-with-forms/move-form-field/
---

En este tutorial, le mostraremos cómo mover un campo de formulario en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento

Cargue el documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Paso 3: Obtener el campo de formulario

Obtenga el campo de formulario que desea mover:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Paso 4: cambiar la ubicación del campo

Cambie la ubicación del campo de formulario definiendo una nueva área rectangular:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Paso 5: Guarda el documento editado

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Mover campo de formulario usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// obtener un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modificar la ubicación del campo
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Guardar documento modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo mover un campo de formulario en un documento PDF utilizando Aspose.PDF para .NET. Siguiendo estos pasos, puede navegar fácilmente a un campo específico y cambiar su ubicación según sea necesario.