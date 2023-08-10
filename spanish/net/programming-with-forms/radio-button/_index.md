---
title: Boton de radio
linktitle: Boton de radio
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente botones de opción a sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 220
url: /es/net/programming-with-forms/radio-button/
---
En este tutorial, le mostraremos cómo agregar un botón de opción en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: crear una instancia de un objeto de documento

Cree una instancia de un objeto Documento para crear un nuevo documento PDF:

```csharp
Document pdfDocument = new Document();
```

## Paso 3: Agrega una página

Agregue una página al documento PDF:

```csharp
pdfDocument.Pages.Add();
```

## Paso 4: crear una instancia de un objeto RadioButtonField

Cree una instancia de un objeto RadioButtonField especificando el número de página como argumento:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Paso 5: Agregar opciones de botón de opción

Agregue opciones de botón de opción al objeto RadioButtonField especificando las coordenadas de cada opción con un objeto Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Paso 6: agregue el botón de opción al formulario

Agregue el botón de opción al objeto Formulario del documento:

```csharp
pdfDocument.Form.Add(radio);
```

## Paso 7: Guarde el documento PDF

Guarde el documento PDF creado:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Radio Button usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instanciar objeto de documento
	Document pdfDocument = new Document();
	// Agregar una página a un archivo PDF
	pdfDocument.Pages.Add();
	// Instate el objeto RadioButtonField con el número de página como argumento
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Agregue la primera opción de botón de opción y también especifique su origen usando el objeto Rectangle
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Agregar segunda opción de botón de radio
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Agregar botón de opción para formar objeto de objeto Documento
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	//Guarde el archivo PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos cómo agregar un botón de opción en un documento PDF usando Aspose.PDF para .NET. Siguiendo estos pasos, puede crear fácilmente un botón de opción y colocarlo en una página específica de su documento PDF.


### Preguntas frecuentes

#### P: ¿Puedo personalizar la apariencia del botón de radio, como su tamaño y color?

 R: Sí, puede personalizar la apariencia del botón de radio usando el`Rectangle` coordenadas del objeto para definir su tamaño y posición. Aspose.PDF para .NET le permite ajustar la apariencia del botón de opción para satisfacer sus necesidades.

#### P: ¿Puedo agregar varios botones de radio con diferentes grupos en la misma página?

R: Sí, puede agregar varios botones de radio con diferentes grupos en la misma página. Cada grupo de botones de radio puede tener un nombre único y solo se puede seleccionar una opción dentro de cada grupo a la vez.

#### P: ¿Cómo puedo agregar una etiqueta o una descripción de texto a las opciones del botón de opción?

 R: Para agregar una etiqueta o una descripción de texto a las opciones del botón de opción, puede usar el`TextStamp`class de Aspose.PDF para .NET para superponer texto en el documento PDF en coordenadas específicas.

#### P: ¿Es Aspose.PDF para .NET compatible con todas las versiones de .NET Framework?

R: Sí, Aspose.PDF para .NET es compatible con todas las versiones de .NET Framework, incluidos .NET Core y .NET Standard.

#### P: ¿Puedo controlar mediante programación la selección de una opción de botón de radio en el documento PDF?

 R: Sí, puede controlar mediante programación la selección de una opción de botón de radio usando el`IsSelected` propiedad de la`RadioButtonOption` clase. Esta propiedad le permite establecer una opción específica como seleccionada.