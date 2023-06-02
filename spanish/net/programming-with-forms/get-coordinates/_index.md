---
title: Obtener coordenadas
linktitle: Obtener coordenadas
second_title: Referencia de API de Aspose.PDF para .NET
description: Obtenga fácilmente coordenadas de campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-forms/get-coordinates/
---

En este tutorial, le mostraremos cómo obtener coordenadas de campos de formulario utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento de salida

Cargue el documento PDF de salida:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Paso 3: Encuentra campos agregados

Busque los campos de formulario agregados (en este ejemplo, estamos usando los campos "Item1", "Item2" y "Item3"):

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

### Ejemplo de código fuente para Obtener coordenadas usando Aspose.Words para .NET 
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
	// Y muestra las posiciones de los elementos secundarios para cada uno de ellos.
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