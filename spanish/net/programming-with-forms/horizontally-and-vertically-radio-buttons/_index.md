---
title: Botones de radio horizontales y verticales
linktitle: Botones de radio horizontales y verticales
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente botones de opción horizontales y verticales en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 180
url: /es/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

En este tutorial, le mostraremos cómo crear botones de radio dispuestos horizontal y verticalmente en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento

Cargue el documento PDF existente:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Paso 3: personaliza las opciones de los botones de opción

Personalice las opciones de los botones de radio configurando las siguientes propiedades:

```csharp
formEditor. RadioGap = 4; // Distancia entre dos opciones de botón de opción
formEditor. RadioHoriz = true; // Diseño horizontal de botones de opción
formEditor.RadioButtonItemSize = 20; // Tamaño de los botones de opción
formEditor.Facade.BorderWidth = 1; // Ancho del borde del botón de opción
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Color del borde del botón de opción
```

## Paso 4: agregue botones de opción horizontales

Agregue botones de radio dispuestos horizontalmente especificando las opciones y la posición del campo:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Paso 5: agregue botones de radio verticales

Agregue botones de radio dispuestos verticalmente especificando las opciones y la posición del campo:

```csharp
formEditor. RadioHoriz = false; // Diseño vertical de botones de opción
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Paso 6: Guarde el documento

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Ejemplo de código fuente para botones de radio horizontales y verticales usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargar el documento previamente guardado
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap es la distancia entre dos opciones de botón de opción.
	formEditor.RadioGap = 4;
	// Agregar botón de opción horizontal
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize si el tamaño del elemento del botón de opción.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Agregar otro botón de radio situado verticalmente
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Guardar el documento PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos cómo crear botones de radio dispuestos horizontal y verticalmente en un documento PDF utilizando Aspose.PDF para .NET. Siguiendo estos pasos, puede personalizar fácilmente el diseño de los botones de opción y agregarlos a sus documentos PDF usando Aspose.PDF.