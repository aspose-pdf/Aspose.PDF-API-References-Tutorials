---
title: Obtener coordenadas de campo de formulario PDF
linktitle: Obtener coordenadas de campo de formulario PDF
second_title: Aspose.PDF para referencia de API .NET
description: Obtenga fácilmente coordenadas de campos de formularios PDF en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-forms/get-coordinates/
---
En este tutorial, le mostraremos cómo obtener coordenadas de campo de formulario PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: preparación

Asegúrese de haber importado las bibliotecas necesarias y establecer la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento de salida

Cargue el documento PDF de salida:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Paso 3: busque campos agregados

Busque los campos de formulario agregados (en este ejemplo, usamos los campos "Elemento1", "Elemento2" y "Elemento3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Paso 4: Mostrar posiciones de subelementos para cada campo

Recorra las opciones de cada campo y vea las coordenadas de cada subelemento:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Código fuente de muestra para Obtener coordenadas usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargar el documento de salida
	Document doc1 = new Document( dataDir + "input.pdf");
	// Buscar campos agregados
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Y muestre las posiciones de los subelementos para cada uno de ellos.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos cómo obtener coordenadas de campos de formulario usando Aspose.PDF para .NET. Siguiendo estos pasos, puede recuperar fácilmente las coordenadas de los subelementos de los campos de su formulario en sus documentos PDF usando Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Puedo utilizar este método para obtener coordenadas para cualquier tipo de campo de formulario en Aspose.PDF para .NET?

R: Sí, puede utilizar este método para obtener coordenadas para varios tipos de campos de formulario en Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra cómo obtener coordenadas para los campos de RadioButton, pero puede adaptar el mismo enfoque para otros tipos de campos de formulario, como TextBox, CheckBox, ListBox y más.

#### P: ¿Cómo puedo modificar o ajustar las coordenadas del campo del formulario?

R: Las coordenadas del campo del formulario se basan en el sistema de coordenadas del documento PDF, donde el origen (0,0) se encuentra en la esquina inferior izquierda de la página. Para modificar o ajustar las coordenadas del campo del formulario, puede actualizar el`Rect` propiedad del campo de formulario respectivo o sus subelementos, como RadioButtonOptionField.

#### P: ¿Puedo agregar las coordenadas de los campos del formulario mediante programación a un documento PDF?

R: Sí, puede obtener las coordenadas de los campos del formulario que se agregaron mediante programación a un documento PDF. Aspose.PDF para .NET le permite agregar campos de formulario dinámicamente y, una vez agregados, puede recuperar sus coordenadas utilizando el enfoque demostrado en este tutorial.

#### P: ¿Cuál es el propósito de recuperar las coordenadas del campo del formulario?

R: Recuperar las coordenadas de los campos del formulario puede resultar útil cuando necesita realizar operaciones o validaciones específicas relacionadas con el diseño en campos de formulario dentro de un documento PDF. Le permite colocar y alinear con precisión los campos del formulario en función de sus coordenadas, lo que garantiza que aparezcan correctamente en el documento y brinde una experiencia de usuario perfecta.

#### P: ¿Las coordenadas del campo del formulario se expresan en puntos u otra unidad?

R: Las coordenadas del campo del formulario en Aspose.PDF para .NET se expresan en puntos. Un punto equivale a 1/72 de pulgada, lo que la convierte en una unidad de medida estándar en formato PDF.