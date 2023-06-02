---
title: Seleccionar botón de opción
linktitle: Seleccionar botón de opción
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a seleccionar un botón de opción en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 250
url: /es/net/programming-with-forms/select-radio-button/
---

Aquí hay un tutorial detallado sobre cómo seleccionar un botón de opción usando Aspose.PDF para .NET. Sigue estos pasos:

##  Paso 1: comience definiendo el directorio de sus documentos especificando la ruta en el`dataDir` variable.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Paso 2: Abra el documento PDF usando el`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Paso 3: obtenga el campo del botón de opción del formulario del documento.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Paso 4: Especifique el índice del botón de radio para seleccionar del grupo.

```csharp
radioField. Selected = 2;
```

## Paso 5: establezca la ruta de salida para el archivo PDF editado.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Paso 6: Guarde el archivo PDF modificado.

```csharp
pdfDocument.Save(dataDir);
```

## Paso 7: muestra un mensaje de confirmación y la ubicación del archivo guardado.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Ejemplo de código fuente para Seleccionar botón de radio usando Aspose.Words para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Abrir documento
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// obtener un campo
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Especifique el índice del botón de opción del grupo
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Guarde el archivo PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos cómo seleccionar un botón de radio usando Aspose.PDF para .NET. Siguiendo los pasos descritos anteriormente, puede manipular y modificar los botones de opción en sus documentos PDF utilizando Aspose.PDF para .NET.