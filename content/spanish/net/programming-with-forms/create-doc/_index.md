---
title: Crear documento
linktitle: Crear documento
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente un documento con botones de opción utilizando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-forms/create-doc/
---
En este tutorial, le mostraremos cómo crear un documento con botones de opción utilizando Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

##Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y configure la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Crear un nuevo documento

Cree un nuevo objeto Documento para almacenar el documento PDF:

```csharp
Document doc = new Document();
```

## Paso 3: Agregar una página

Agregar una nueva página al documento:

```csharp
Page page = doc.Pages.Add();
```

## Paso 4: Agregar un campo de botón de opción

Cree un campo de botón de opción y establezca su posición y tamaño:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Paso 5: Agregar opciones de botón de opción

Agregue las opciones deseadas al campo del botón de opción. Puede configurar las coordenadas y el tamaño de cada opción según sea necesario:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Paso 6: Agregue el campo de botón de opción al formulario

Agregue el campo de botón de opción a la colección Campos de formulario de documento:

```csharp
doc.Form.Add(field);
```

## Paso 7: Guardar el documento

Guardar el documento PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para crear un documento con Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crear un nuevo documento
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Agregar campo de botón de opción
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Agregue opciones de botón de opción. Tenga en cuenta que estas opciones están ubicadas
	// Ni horizontal ni verticalmente.
	// Puedes intentar establecer cualquier coordenada (e incluso tamaño) para ellos.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Guardar el documento PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos a crear un documento con botones de opción usando Aspose.PDF para .NET. Si sigue estos pasos, podrá agregar fácilmente botones de opción a sus documentos PDF usando Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Puedo personalizar la apariencia de los botones de opción en el documento usando Aspose.PDF para .NET?

R: Sí, puede personalizar la apariencia de los botones de opción en el documento mediante Aspose.PDF para .NET. Puede configurar propiedades como tamaño, color, estilo de borde y más para personalizar la apariencia de los botones de opción.

#### P: ¿Cómo puedo agregar grupos de botones de opción con opciones mutuamente excluyentes?

R: Para crear opciones mutuamente excluyentes, puede agregar varios campos de botón de opción con el mismo nombre. Esto garantizará que cuando se seleccione una opción, las otras opciones con el mismo nombre se deseleccionen automáticamente.

#### P: ¿Es posible establecer una opción seleccionada predeterminada para los botones de opción?

R: Sí, puede establecer una opción seleccionada predeterminada para los botones de opción utilizando Aspose.PDF para .NET. Puede utilizar el`Selected` propiedad de la`RadioButtonOptionField` objeto para marcar una opción como seleccionada por defecto.

#### P: ¿Puedo agregar controladores de eventos a los botones de opción?

 R: Sí, puede agregar controladores de eventos a los botones de opción mediante Aspose.PDF para .NET. Puede asociar acciones de JavaScript, como`OnValueChanged`, a los botones de opción para realizar acciones específicas cuando el usuario selecciona una opción.

#### P: ¿Cómo puedo recuperar la opción seleccionada del grupo de botones de opción después de que el usuario realiza una selección?

 A: Puede recuperar la opción seleccionada del grupo de botones de opción mediante Aspose.PDF para .NET. Una vez que el usuario realiza una selección, puede acceder a la`Selected` propiedad de la`RadioButtonOptionField` objeto para comprobar qué opción está seleccionada.