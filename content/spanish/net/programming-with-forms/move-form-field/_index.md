---
title: Mover campo de formulario
linktitle: Mover campo de formulario
second_title: Referencia de API de Aspose.PDF para .NET
description: Mueva fácilmente los campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 200
url: /es/net/programming-with-forms/move-form-field/
---
En este tutorial, le mostraremos cómo mover un campo de formulario en un documento PDF con Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y de haber configurado la ruta al directorio de sus documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargar el documento

Cargar el documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Paso 3: Obtener el campo de formulario

Obtenga el campo de formulario que desea mover:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Paso 4: Cambiar la ubicación del campo

Cambie la ubicación del campo de formulario definiendo una nueva área rectangular:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Paso 5: Guarde el documento editado

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Código fuente de muestra para mover un campo de formulario con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Conseguir un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Modificar la ubicación del campo
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Guardar documento modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos a mover un campo de formulario en un documento PDF con Aspose.PDF para .NET. Si sigue estos pasos, podrá navegar fácilmente hasta un campo específico y cambiar su ubicación según sea necesario.


### Preguntas frecuentes

#### P: ¿Puedo mover varios campos de formulario dentro de un solo documento PDF usando Aspose.PDF para .NET?

R: Sí, puede mover varios campos de formulario dentro de un único documento PDF utilizando Aspose.PDF para .NET. Simplemente repita el proceso para cada campo de formulario que desee reubicar.

#### P: ¿Mover un campo de formulario afectará sus datos o funcionalidades asociadas?

R: No, mover un campo de formulario no afecta a sus datos asociados ni a su funcionalidad. El campo de formulario conserva todas sus propiedades y valores después de ser movido a una nueva ubicación.

#### P: ¿Cómo puedo determinar las coordenadas exactas para la nueva ubicación del campo de formulario?

 A: Puede especificar la nueva ubicación utilizando el`Aspose.Pdf.Rectangle` clase, donde se definen las coordenadas X e Y de la esquina superior izquierda y las coordenadas X e Y de la esquina inferior derecha del área rectangular.

#### P: ¿Aspose.PDF para .NET es compatible con entornos Windows y Linux?

R: Sí, Aspose.PDF para .NET es compatible con entornos Windows y Linux, lo que proporciona flexibilidad para que los desarrolladores trabajen en sus sistemas operativos preferidos.