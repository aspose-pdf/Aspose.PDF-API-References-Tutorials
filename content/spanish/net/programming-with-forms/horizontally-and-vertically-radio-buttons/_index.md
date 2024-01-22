---
title: Botones de opción horizontal y vertical
linktitle: Botones de opción horizontal y vertical
second_title: Aspose.PDF para referencia de API .NET
description: Cree fácilmente botones de opción horizontales y verticales en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 180
url: /es/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
En este tutorial, le mostraremos cómo crear botones de opción dispuestos horizontal y verticalmente en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: preparación

Asegúrese de haber importado las bibliotecas necesarias y establecer la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento

Cargue el documento PDF existente:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Paso 3: personaliza las opciones del botón de opción

Personalice las opciones del botón de opción configurando las siguientes propiedades:

```csharp
formEditor. RadioGap = 4; // Distancia entre dos opciones de botón de radio
formEditor. RadioHoriz = true; //Diseño horizontal de botones de opción.
formEditor.RadioButtonItemSize = 20; // Tamaño de los botones de opción
formEditor.Facade.BorderWidth = 1; // Ancho del borde del botón de radio
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Color del borde del botón de radio
```

## Paso 4: agregue botones de opción horizontales

Agregue botones de opción dispuestos horizontalmente especificando las opciones y la posición del campo:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Paso 5: agregue botones de opción verticales

Agregue botones de opción dispuestos verticalmente especificando las opciones y la posición del campo:

```csharp
formEditor. RadioHoriz = false; // Diseño vertical de botones de opción.
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Paso 6: guarde el documento

Guarde el documento PDF modificado:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Código fuente de muestra para botones de radio horizontal y verticalmente usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargar el documento previamente guardado
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap es la distancia entre dos opciones de botones de opción.
	formEditor.RadioGap = 4;
	// Agregar botón de opción horizontal
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize si es el tamaño del elemento del botón de opción.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Agregar otro botón de opción situado verticalmente
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Guarde el documento PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos cómo crear botones de opción dispuestos horizontal y verticalmente en un documento PDF usando Aspose.PDF para .NET. Siguiendo estos pasos, puede personalizar fácilmente el diseño de los botones de opción y agregarlos a sus documentos PDF usando Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Qué son los botones de opción dispuestos horizontal y verticalmente en un documento PDF?

R: Los botones de opción dispuestos horizontal y verticalmente en un documento PDF se refieren a la orientación del diseño de las opciones de los botones de opción. El diseño horizontal coloca las opciones del botón de opción una al lado de la otra, lo que permite a los usuarios realizar una selección de izquierda a derecha. El diseño vertical, por otro lado, apila las opciones de los botones de opción una encima de la otra, lo que permite a los usuarios realizar una selección de arriba a abajo.

#### P: ¿Cómo personalizo la apariencia de las opciones de los botones de opción en Aspose.PDF para .NET?

R: Puede personalizar la apariencia de las opciones de los botones de opción en Aspose.PDF para .NET ajustando varias propiedades. La API proporciona opciones para establecer la distancia entre dos opciones de botón de opción (`RadioGap`), la orientación del diseño (`RadioHoriz`), el tamaño de los elementos del botón de opción (`RadioButtonItemSize`), el ancho del borde y el color de los botones de opción, y más.

#### P: ¿Puedo agregar botones de opción horizontales y verticales al mismo documento PDF?

R: Sí, puede agregar botones de opción horizontales y verticales al mismo documento PDF usando Aspose.PDF para .NET. El código fuente de muestra proporcionado en el tutorial demuestra cómo agregar primero botones de opción dispuestos horizontalmente y luego agregar otro conjunto de botones de opción dispuestos verticalmente al mismo documento PDF.

#### P: ¿Puedo configurar diferentes opciones de botones de opción para cada grupo de botones de opción?

 R: Sí, puede configurar diferentes opciones de botones de opción para cada grupo de botones de opción. Cada grupo debe tener un único`RadioButtonField` objeto, y el`RadioButtonOptionField` Los objetos dentro de cada grupo deben compartir la misma página y nombres únicos para sus opciones. Esto garantiza que los botones de opción dentro de cada grupo funcionen correctamente y que las selecciones sean mutuamente excluyentes.

#### P: ¿Las configuraciones de diseño y apariencia de los botones de opción son compatibles con todos los visores y aplicaciones de PDF?

R: Sí, la configuración de diseño y apariencia de los botones de opción es compatible con todos los visores y aplicaciones de PDF compatibles con los estándares. La especificación PDF define los botones de opción y sus diversos atributos, haciéndolos universalmente reconocidos en el formato PDF. Sin embargo, es esencial probar la apariencia y el comportamiento de los botones de opción en diferentes visores de PDF para garantizar una representación consistente en varias plataformas.