---
title: Modificar campo de formulario
linktitle: Modificar campo de formulario
second_title: Referencia de API de Aspose.PDF para .NET
description: Edite fácilmente campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 190
url: /es/net/programming-with-forms/modify-form-field/
---

En este tutorial, le mostraremos cómo editar un campo de formulario en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento

Cargue el documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Paso 3: Obtener el campo de formulario

Obtenga el campo de formulario que desea editar:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Paso 4: cambie el valor del campo

Cambie el valor del campo de formulario:

```csharp
textBoxField.Value = "New Value";
```

## Paso 5: Editar propiedades de campo

Modifique propiedades de campo de formulario adicionales según sea necesario. Por ejemplo, puede hacer que sea de solo lectura:

```csharp
textBoxField.ReadOnly = true;
```

## Paso 6: Guarde el documento editado

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Modificar campo de formulario usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// obtener un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modificar valor de campo
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos a editar un campo de formulario en un documento PDF utilizando Aspose.PDF para .NET. Siguiendo estos pasos, puede navegar fácilmente a un campo específico, cambiar su valor y ajustar sus propiedades según sea necesario.