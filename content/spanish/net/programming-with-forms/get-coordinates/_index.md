---
title: Obtener las coordenadas de los campos del formulario PDF
linktitle: Obtener las coordenadas de los campos del formulario PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Obtenga fácilmente las coordenadas de los campos de formulario PDF en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-forms/get-coordinates/
---
En este tutorial, le mostraremos cómo obtener las coordenadas de los campos de un formulario PDF con Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y de haber establecido la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento de salida

Cargar el documento PDF de salida:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Paso 3: Encuentra los campos añadidos

Busque los campos de formulario agregados (en este ejemplo, usamos los campos "Item1", "Item2" y "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Paso 4: Mostrar las posiciones de los subelementos para cada campo

Recorra las opciones de cada campo y visualice las coordenadas de cada subelemento:

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

### Código fuente de muestra para obtener coordenadas con Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargar el documento de salida
	Document doc1 = new Document( dataDir + "input.pdf");
	// Buscar campos añadidos
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Y mostrar las posiciones de los subelementos para cada uno de ellos.
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

En este tutorial, aprendimos a obtener las coordenadas de los campos de formulario con Aspose.PDF para .NET. Si sigue estos pasos, podrá recuperar fácilmente las coordenadas de los subelementos de los campos de formulario en sus documentos PDF con Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Puedo utilizar este método para obtener coordenadas de cualquier tipo de campo de formulario en Aspose.PDF para .NET?

R: Sí, puede utilizar este método para obtener coordenadas de varios tipos de campos de formulario en Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra cómo obtener coordenadas para campos RadioButton, pero puede adaptar el mismo enfoque para otros tipos de campos de formulario, como TextBox, CheckBox, ListBox y más.

#### P: ¿Cómo puedo modificar o ajustar las coordenadas del campo de formulario?

A: Las coordenadas del campo de formulario se basan en el sistema de coordenadas del documento PDF, donde el origen (0,0) se encuentra en la esquina inferior izquierda de la página. Para modificar o ajustar las coordenadas del campo de formulario, puede actualizar el`Rect` propiedad del campo de formulario respectivo o sus subelementos, como RadioButtonOptionField.

#### P: ¿Puedo obtener las coordenadas de los campos de formulario agregados programáticamente a un documento PDF?

R: Sí, puede obtener las coordenadas de los campos de formulario que se agregaron mediante programación a un documento PDF. Aspose.PDF para .NET le permite agregar campos de formulario de manera dinámica y, una vez agregados, puede recuperar sus coordenadas mediante el método que se muestra en este tutorial.

#### P: ¿Cuál es el propósito de recuperar las coordenadas del campo de formulario?

A: Recuperar las coordenadas de los campos de formulario puede ser útil cuando necesita realizar operaciones o validaciones específicas relacionadas con el diseño en los campos de formulario dentro de un documento PDF. Le permite posicionar y alinear con precisión los campos de formulario en función de sus coordenadas, lo que garantiza que aparezcan correctamente en el documento y brinden una experiencia de usuario perfecta.

#### P: ¿Las coordenadas del campo de formulario se expresan en puntos u otra unidad?

R: Las coordenadas de los campos de formulario en Aspose.PDF para .NET se expresan en puntos. Un punto equivale a 1/72 de pulgada, lo que lo convierte en una unidad de medida estándar en el formato PDF.