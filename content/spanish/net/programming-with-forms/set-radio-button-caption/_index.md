---
title: Establecer título del botón de radio
linktitle: Establecer título del botón de radio
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a utilizar Aspose.PDF para .NET para configurar el título de un botón de opción en un formulario PDF.
type: docs
weight: 280
url: /es/net/programming-with-forms/set-radio-button-caption/
---
En esta guía, explicaremos paso a paso cómo utilizar la biblioteca Aspose.PDF para .NET para definir el título de un botón de opción en un formulario PDF. Le mostraremos cómo acceder al campo del botón de opción, crear una nueva opción de botón de opción y personalizar el título del botón.

## Paso 1: Configurar el directorio de documentos

 El primer paso es configurar el directorio de documentos donde se encuentra el formulario PDF en el que desea trabajar. Puedes usar el`dataDir` variable para especificar la ruta del directorio.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Asegúrate de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: cargar el formulario PDF de origen

 En este paso, cargaremos el formulario PDF de origen utilizando el`Aspose.Pdf.Facades.Form` clase de Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Asegúrese de que el archivo PDF que contiene el formulario esté presente en el directorio de documentos especificado.

## Paso 3: Editar el título del botón de opción

Recorreremos los nombres de los campos del formulario y buscaremos campos de botones de opción. Si se encuentra un campo coincidente, crearemos una nueva opción de botón de opción con un título personalizado y la agregaremos al campo existente.

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
// Especificar el modo de ajuste de palabras
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Agregue el nuevo TextFragment al párrafo
par.AppendLine(updatedFragment);
// Agregue el párrafo de texto usando TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Personalice el botón de opción de subtítulos y otras configuraciones según sea necesario.

## Paso 4: guardar el PDF resultante

 Ahora que hemos terminado de modificar el título del botón de opción, podemos guardar el PDF resultante usando el`Save` método de la`Document` clase.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Asegúrese de especificar la ruta completa y el nombre del archivo del PDF resultante.

### Código fuente de muestra para Establecer título de botón de opción usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario PDF fuente
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
		// Agregue el párrafo de texto usando TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusión

En esta guía, aprendimos cómo usar la biblioteca Aspose.PDF para .NET para configurar el título de un botón de opción en un formulario PDF. Siguiendo los pasos descritos, puede personalizar las opciones del botón de opción y cambiar el título según sea necesario. No dude en explorar más a fondo las funciones de Aspose.PDF para .NET para ampliar las posibilidades de manipulación de archivos PDF.

### Preguntas frecuentes

#### P: ¿Puedo usar Aspose.PDF para .NET para configurar títulos para botones de opción en un formulario PDF?

R: Sí, puede usar Aspose.PDF para .NET para configurar títulos para botones de opción en un formulario PDF. El código fuente de muestra proporcionado muestra cómo acceder al campo del botón de opción, crear una nueva opción de botón de opción con un título personalizado y actualizar el campo existente.

#### P: ¿Cómo puedo personalizar la apariencia del título del botón de opción, como el tamaño y el color de la fuente?

 R: Puede personalizar la apariencia del título del botón de opción ajustando las propiedades del`TextFragment` utilizado para el título. Por ejemplo, puede configurar la fuente, el tamaño de fuente, el color, el interlineado y otras opciones de formato de texto.

#### P: ¿Es posible agregar varias opciones de botones de opción con diferentes títulos a un solo grupo de botones de opción?

R: Sí, puede agregar varias opciones de botones de opción con diferentes títulos a un solo grupo de botones de opción. Cada opción representará una elección diferente y los usuarios pueden seleccionar solo una opción del grupo.

#### P: ¿Puedo usar Aspose.PDF para .NET para modificar otros campos de formulario en un documento PDF?

R: Sí, Aspose.PDF para .NET proporciona un conjunto completo de funciones para manipular varios campos de formulario en un documento PDF, como campos de texto, casillas de verificación, listas desplegables y más. Puede utilizar la biblioteca para establecer valores, modificar apariencias y agregar interactividad a los campos de formulario.

#### P: ¿Aspose.PDF para .NET admite el trabajo con archivos PDF generados a partir de otras fuentes, como documentos escaneados?

R: Sí, Aspose.PDF para .NET admite trabajar con archivos PDF generados a partir de diversas fuentes, incluidos documentos escaneados. La biblioteca proporciona capacidades de OCR (reconocimiento óptico de caracteres) para extraer texto de archivos PDF escaneados y manipular el contenido mediante programación.