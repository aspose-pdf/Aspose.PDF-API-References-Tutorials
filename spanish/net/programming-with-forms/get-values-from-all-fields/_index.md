---
title: Obtener valores de todos los campos
linktitle: Obtener valores de todos los campos
second_title: Referencia de API de Aspose.PDF para .NET
description: Obtenga fácilmente los valores de todos los campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 150
url: /es/net/programming-with-forms/get-values-from-all-fields/
---

En este tutorial, le mostraremos cómo obtener los valores de todos los campos de formulario en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: abre el documento

Abra el documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Paso 3: Obtener valores para todos los campos

Recorra todos los campos del formulario en el documento y obtenga sus nombres y valores:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Ejemplo de código fuente para Obtener valores de todos los campos usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Obtener valores de todos los campos
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusión

En este tutorial, aprendimos cómo obtener los valores de todos los campos de formulario en un documento PDF usando Aspose.PDF para .NET. Siguiendo estos pasos, puede extraer fácilmente los valores de todos los campos de formulario de sus documentos PDF utilizando Aspose.PDF.