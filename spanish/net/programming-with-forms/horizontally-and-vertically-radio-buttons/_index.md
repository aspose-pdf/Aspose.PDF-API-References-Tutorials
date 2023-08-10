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
formEditor. RadioHoriz = true; //Diseño horizontal de botones de opción
formEditor.RadioButtonItemSize = 20; // Tamaño de los botones de opción
formEditor.Facade.BorderWidth = 1; // Ancho del borde del botón de opción
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Color del borde del botón de opción
```

## Paso 4: agregue botones de radio horizontales

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

### Preguntas frecuentes

#### P: ¿Qué son los botones de radio dispuestos horizontal y verticalmente en un documento PDF?

R: Los botones de opción dispuestos horizontal y verticalmente en un documento PDF se refieren a la orientación del diseño de las opciones de los botones de opción. El diseño horizontal coloca las opciones del botón de radio una al lado de la otra, lo que permite a los usuarios realizar una selección de izquierda a derecha. El diseño vertical, por otro lado, apila las opciones de los botones de radio una encima de la otra, lo que permite a los usuarios hacer una selección de arriba a abajo.

#### P: ¿Cómo personalizo la apariencia de las opciones de los botones de radio en Aspose.PDF para .NET?

R: Puede personalizar la apariencia de las opciones de los botones de radio en Aspose.PDF para .NET ajustando varias propiedades. La API proporciona opciones para establecer la distancia entre dos opciones de botón de radio (`RadioGap`), la orientación del diseño (`RadioHoriz`), el tamaño de los elementos del botón de radio (`RadioButtonItemSize`), el ancho del borde y el color de los botones de opción, y más.

#### P: ¿Puedo agregar botones de opción horizontales y verticales al mismo documento PDF?

R: Sí, puede agregar botones de radio horizontales y verticales al mismo documento PDF utilizando Aspose.PDF para .NET. El código fuente de muestra proporcionado en el tutorial demuestra cómo agregar primero botones de opción dispuestos horizontalmente y luego agregar otro conjunto de botones de opción dispuestos verticalmente al mismo documento PDF.

#### P: ¿Puedo configurar diferentes opciones de botones de radio para cada grupo de botones de radio?

 R: Sí, puede configurar diferentes opciones de botones de radio para cada grupo de botones de radio. Cada grupo debe tener un único`RadioButtonField` objeto, y el`RadioButtonOptionField` los objetos dentro de cada grupo deben compartir la misma página y nombres únicos para sus opciones. Esto asegura que los botones de radio dentro de cada grupo funcionen correctamente y que las selecciones sean mutuamente excluyentes.

#### P: ¿La configuración de diseño y apariencia de los botones de opción es compatible con todos los visores y aplicaciones de PDF?

R: Sí, la configuración de diseño y apariencia de los botones de radio es compatible con todos los visores y aplicaciones de PDF que cumplen con los estándares. La especificación de PDF define los botones de opción y sus diversos atributos, lo que los hace universalmente reconocidos en el formato PDF. Sin embargo, es esencial probar la apariencia y el comportamiento de los botones de opción en diferentes visores de PDF para garantizar una representación uniforme en varias plataformas.