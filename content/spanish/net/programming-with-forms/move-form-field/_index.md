---
title: Mover campo de formulario
linktitle: Mover campo de formulario
second_title: Aspose.PDF para referencia de API .NET
description: Mueva fácilmente los campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 200
url: /es/net/programming-with-forms/move-form-field/
---
En este tutorial, le mostraremos cómo mover un campo de formulario en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: preparación

Asegúrese de haber importado las bibliotecas necesarias y establecer la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento

Cargue el documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Paso 3: obtenga el campo del formulario

Obtenga el campo del formulario que desea mover:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Paso 4: cambiar la ubicación del campo

Cambie la ubicación del campo del formulario definiendo una nueva área rectangular:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Paso 5: guarde el documento editado

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Código fuente de muestra para mover campo de formulario usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// conseguir un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modificar la ubicación del campo
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Guardar documento modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo mover un campo de formulario en un documento PDF usando Aspose.PDF para .NET. Si sigue estos pasos, podrá navegar fácilmente a un campo específico y cambiar su ubicación según sea necesario.


### Preguntas frecuentes

#### P: ¿Puedo mover varios campos de formulario dentro de un solo documento PDF usando Aspose.PDF para .NET?

R: Sí, puede mover varios campos de formulario dentro de un solo documento PDF usando Aspose.PDF para .NET. Simplemente repita el proceso para cada campo del formulario que desee reubicar.

#### P: ¿Mover un campo de formulario afectará sus datos o funcionalidad asociados?

R: No, mover un campo de formulario no afecta sus datos ni su funcionalidad asociados. El campo del formulario conserva todas sus propiedades y valores después de ser movido a una nueva ubicación.

#### P: ¿Cómo puedo determinar las coordenadas exactas de la nueva ubicación del campo del formulario?

 R: Puede especificar la nueva ubicación usando el`Aspose.Pdf.Rectangle` clase, donde define las coordenadas X e Y de la esquina superior izquierda y las coordenadas X e Y de la esquina inferior derecha del área rectangular.

#### P: ¿Aspose.PDF para .NET es compatible con entornos Windows y Linux?

R: Sí, Aspose.PDF para .NET es compatible con entornos Windows y Linux, lo que brinda flexibilidad a los desarrolladores para trabajar en sus sistemas operativos preferidos.