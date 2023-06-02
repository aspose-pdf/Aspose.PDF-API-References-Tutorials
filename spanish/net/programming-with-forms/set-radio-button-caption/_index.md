---
title: Establecer título de botón de opción
linktitle: Establecer título de botón de opción
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para configurar el título de un botón de opción en un formulario PDF.
type: docs
weight: 280
url: /es/net/programming-with-forms/set-radio-button-caption/
---

En esta guía, explicaremos paso a paso cómo usar la biblioteca Aspose.PDF para .NET para definir el título de un botón de opción en un formulario PDF. Le mostraremos cómo acceder al campo del botón de opción, crear una nueva opción de botón de opción y personalizar el título del botón.

## Paso 1: Configuración del directorio de documentos

 El primer paso es configurar el directorio del documento donde se encuentra el formulario PDF en el que desea trabajar. Puedes usar el`dataDir`variable para especificar la ruta del directorio.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: Cargar el formulario PDF de origen

 En este paso, cargaremos el formulario PDF de origen usando el`Aspose.Pdf.Facades.Form` clase de Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Asegúrese de que el archivo PDF que contiene el formulario esté presente en el directorio de documentos especificado.

## Paso 3: Edición del título del botón de opción

Recorreremos los nombres de los campos de formulario y buscaremos campos de botones de opción. Si se encuentra un campo coincidente, crearemos una nueva opción de botón de radio con un título personalizado y lo agregaremos al campo existente.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Crear un objeto TextParagraph
TextParagraph par = new TextParagraph();
// Establecer la posición del párrafo
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Especificar el modo de ajuste de línea
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Agregue el nuevo TextFragment al párrafo
par.AppendLine(updatedFragment);
// Agregue TextParagraph usando TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Personalice el botón de opción de subtítulos y otras configuraciones según sea necesario.

## Paso 4: Guardar el PDF resultante

 Ahora que hemos terminado de modificar el título del botón de opción, podemos guardar el PDF resultante usando el`Save` metodo de la`Document` clase.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Asegúrese de especificar la ruta completa y el nombre de archivo del PDF resultante.

### Ejemplo de código fuente para Establecer título de botón de radio usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario PDF de origen
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Crear objeto TextParagraph
		TextParagraph par = new TextParagraph();
		// Establecer la posición del párrafo
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Especificar el modo de ajuste de palabras
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Agregar nuevo TextFragment al párrafo
		par.AppendLine(updatedFragment);
		// Agregue TextParagraph usando TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusión

En esta guía, aprendimos a usar la biblioteca Aspose.PDF para .NET para configurar el título de un botón de opción en un formulario PDF. Siguiendo los pasos descritos, puede personalizar las opciones del botón de radio y cambiar el título según sea necesario. Siéntase libre de explorar más a fondo las funciones de Aspose.PDF para .NET para ampliar las posibilidades de manipular archivos PDF.