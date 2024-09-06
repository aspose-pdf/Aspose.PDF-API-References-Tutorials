---
title: Cuadro combinado
linktitle: Cuadro combinado
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente listas de cuadros combinados en sus documentos PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-forms/combo-box/
---
En este tutorial, le mostraremos cómo crear una lista de cuadros combinados con Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y configure la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Crear un objeto de documento

Cree un objeto Documento para almacenar el formulario PDF:

```csharp
Document doc = new Document();
```

## Paso 3: Agregar una página

Añadir una página al documento:

```csharp
doc.Pages.Add();
```

## Paso 4: Crear una instancia de un objeto ComboBoxField

Cree una instancia de un objeto ComboBoxField con las dimensiones deseadas:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Paso 5: Agregar opciones a la lista desplegable

Añade las opciones deseadas a la lista desplegable:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Paso 6: Agregue la lista del cuadro combinado al formulario

Agregue el objeto ComboBoxField a la colección Campos de formulario de documento:

```csharp
doc.Form.Add(combo);
```

## Paso 7: Guardar el documento

Guardar el documento PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para cuadro combinado con Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Crear objeto de documento
	Document doc = new Document();
	// Agregar página al objeto de documento
	doc.Pages.Add();
	// Crear una instancia del objeto Campo ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Agregar opción a ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Agregar objeto de cuadro combinado a la colección de campos de formulario del objeto de documento
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Guardar el documento PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

En este tutorial, aprendimos a crear una lista de cuadros combinados con Aspose.PDF para .NET. Si sigue estos pasos, podrá agregar fácilmente una lista de cuadros combinados a sus documentos PDF con Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Puedo personalizar la apariencia de la lista del cuadro combinado usando Aspose.PDF para .NET?

R: Sí, puede personalizar la apariencia de la lista del cuadro combinado con Aspose.PDF para .NET. Puede configurar propiedades como el tamaño de fuente, el color, el color de fondo, el estilo del borde y más para que coincidan con el aspecto que desee.

#### P: ¿Puedo configurar opciones seleccionadas predeterminadas en la lista del cuadro combinado?

 R: Sí, puede configurar las opciones seleccionadas predeterminadas en la lista del cuadro combinado utilizando Aspose.PDF para .NET. Puede utilizar el`Selected` propiedad de la`ComboBoxField` objeto para marcar una o más opciones como seleccionadas por defecto.

#### P: ¿Cómo puedo recuperar el valor seleccionado de la lista del cuadro combinado después de que el usuario realiza una selección?

 A: Puede recuperar el valor seleccionado de la lista del cuadro combinado utilizando Aspose.PDF para .NET. Después de que el usuario realiza una selección, puede acceder a la lista de valores.`Value` propiedad de la`ComboBoxField`objeto para obtener el valor seleccionado.

#### P: ¿Es posible agregar controladores de eventos o acciones a la lista del cuadro combinado?

 R: Sí, Aspose.PDF para .NET le permite agregar controladores de eventos o acciones a la lista del cuadro combinado. Puede asociar acciones de JavaScript, como`OnValueChanged`, a la lista del cuadro combinado para realizar acciones específicas cuando el usuario selecciona una opción.

#### P: ¿Puedo agregar información sobre herramientas o descripciones a las opciones en la lista del cuadro combinado?

 R: Sí, puede agregar información sobre herramientas o descripciones a las opciones en la lista del cuadro combinado utilizando Aspose.PDF para .NET. Puede configurar`AlternateName` propiedad de cada opción para proporcionar una información sobre herramientas o una descripción que se mostrará cuando el usuario pase el cursor sobre la opción.