---
title: Obtener valor del campo
linktitle: Obtener valor del campo
second_title: Referencia de API de Aspose.PDF para .NET
description: Obtenga fácilmente el valor de un campo de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/programming-with-forms/get-value-from-field/
---

En este tutorial, le mostraremos cómo obtener el valor de un campo de formulario utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: abre el documento

Abra el documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Paso 3: obtener campo

Obtenga el campo de formulario deseado (en este ejemplo, estamos usando el campo "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Paso 4: Obtenga el valor del campo

 Obtenga el valor del campo usando el`Value` propiedad:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Ejemplo de código fuente para Obtener valor de campo usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// obtener un campo
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Obtener valor de campo
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Conclusión

En este tutorial, aprendimos cómo obtener el valor de un campo de formulario usando Aspose.PDF para .NET. Siguiendo estos pasos, puede extraer fácilmente el valor de un campo de formulario específico en sus documentos PDF utilizando Aspose.PDF.