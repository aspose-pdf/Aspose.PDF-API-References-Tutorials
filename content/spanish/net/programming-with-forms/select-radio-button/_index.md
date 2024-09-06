---
title: Seleccionar botón de opción en documento PDF
linktitle: Seleccionar botón de opción en documento PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a seleccionar un botón de opción en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 250
url: /es/net/programming-with-forms/select-radio-button/
---
Aquí encontrará un tutorial detallado sobre cómo seleccionar un botón de opción con Aspose.PDF para .NET. Siga estos pasos:

##  Paso 1: Comience por definir el directorio de sus documentos especificando la ruta en el`dataDir` variable.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Paso 2: Abra el documento PDF utilizando el`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Paso 3: Obtenga el campo de botón de opción del formulario del documento.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Paso 4: Especifique el índice del botón de opción para seleccionar del grupo.

```csharp
radioField. Selected = 2;
```

## Paso 5: Establezca la ruta de salida para el archivo PDF editado.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Paso 6: Guarde el archivo PDF modificado.

```csharp
pdfDocument.Save(dataDir);
```

## Paso 7: Muestra un mensaje de confirmación y la ubicación del archivo guardado.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Código fuente de muestra para el botón de opción Seleccionar con Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Abrir documento
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Conseguir un campo
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Especifique el índice del botón de opción del grupo
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Guardar el archivo PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos a seleccionar un botón de opción con Aspose.PDF para .NET. Si sigue los pasos descritos anteriormente, podrá manipular y modificar botones de opción en sus documentos PDF con Aspose.PDF para .NET.


### Preguntas frecuentes

#### P: ¿Puedo seleccionar varios botones de opción en un grupo usando Aspose.PDF para .NET?

R: No, los botones de opción de un grupo están diseñados para ser mutuamente excluyentes. Solo puede seleccionar un botón de opción a la vez dentro de un grupo y, al seleccionar uno, se deseleccionará automáticamente cualquier botón de opción seleccionado previamente en el mismo grupo.

#### P: ¿Cómo puedo recuperar el botón de opción seleccionado en un grupo usando Aspose.PDF para .NET?

 A: Para recuperar el botón de opción seleccionado en un grupo, puede utilizar el`Selected` propiedad de la`RadioButtonField` clase. Devolverá el índice del botón de opción seleccionado dentro del grupo.

#### P: ¿Puedo personalizar la apariencia del botón de opción seleccionado en el documento PDF?

R: Sí, puede personalizar la apariencia del botón de opción seleccionado mediante Aspose.PDF para .NET. Puede modificar su color, tamaño, estilo de borde y otros atributos visuales para que coincidan con la apariencia deseada.

#### P: ¿Es posible crear nuevos grupos de botones de opción mediante programación utilizando Aspose.PDF para .NET?

R: Sí, puede crear nuevos grupos de botones de opción mediante programación utilizando Aspose.PDF para .NET. Puede agregar nuevos botones de opción al formulario del documento y especificar el mismo nombre de grupo para cada botón de opción para crear un nuevo grupo.

#### P: ¿Aspose.PDF para .NET admite el trabajo con formularios PDF interactivos?

R: Sí, Aspose.PDF para .NET es totalmente compatible con formularios PDF interactivos, incluidos botones de opción, campos de texto, casillas de verificación y otros elementos de formulario. Puede leer, modificar y crear formularios PDF interactivos fácilmente utilizando la biblioteca.