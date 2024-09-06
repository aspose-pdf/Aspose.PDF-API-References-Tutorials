---
title: Establecer título del botón de opción
linktitle: Establecer título del botón de opción
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a utilizar Aspose.PDF para .NET para establecer el título de un botón de opción en un formulario PDF.
type: docs
weight: 280
url: /es/net/programming-with-forms/set-radio-button-caption/
---
En esta guía, explicaremos paso a paso cómo utilizar la biblioteca Aspose.PDF para .NET para definir el título de un botón de opción en un formulario PDF. Le mostraremos cómo acceder al campo del botón de opción, crear una nueva opción de botón de opción y personalizar el título del botón.

## Paso 1: Configurar el directorio de documentos

 El primer paso es configurar el directorio del documento donde se encuentra el formulario PDF con el que desea trabajar. Puede utilizar el`dataDir` variable para especificar la ruta del directorio.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: Cargar el formulario PDF de origen

 En este paso, cargaremos el formulario PDF de origen utilizando el`Aspose.Pdf.Facades.Form` clase de Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Asegúrese de que el archivo PDF que contiene el formulario esté presente en el directorio de documentos especificado.

## Paso 3: Edición del título del botón de opción

Recorreremos los nombres de los campos del formulario y buscaremos campos de botón de opción. Si encontramos un campo coincidente, crearemos una nueva opción de botón de opción con un título personalizado y la agregaremos al campo existente.

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
// Añade el nuevo TextFragment al párrafo
par.AppendLine(updatedFragment);
// Agregue TextParagraph usando TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Personalice el botón de subtítulo y otras configuraciones según sea necesario.

## Paso 4: Guardar el PDF resultante

 Ahora que hemos terminado de modificar el título del botón de opción, podemos guardar el PDF resultante usando el`Save` método de la`Document` clase.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Asegúrese de especificar la ruta completa y el nombre del archivo PDF resultante.

### Código fuente de muestra para establecer el título del botón de opción con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar fuente de formato PDF
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
		// Especificar el modo de ajuste de línea
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Añadir nuevo TextFragment al párrafo
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

En esta guía, aprendimos a usar la biblioteca Aspose.PDF para .NET para configurar el título de un botón de opción en un formulario PDF. Si sigue los pasos descritos, puede personalizar las opciones del botón de opción y cambiar el título según sea necesario. No dude en explorar más a fondo las características de Aspose.PDF para .NET para ampliar las posibilidades de manipulación de archivos PDF.

### Preguntas frecuentes

#### P: ¿Puedo usar Aspose.PDF para .NET para configurar títulos para botones de opción en un formulario PDF?

R: Sí, puede utilizar Aspose.PDF para .NET para configurar títulos para botones de opción en un formulario PDF. El código fuente de muestra proporcionado demuestra cómo acceder al campo de botón de opción, crear una nueva opción de botón de opción con un título personalizado y actualizar el campo existente.

#### P: ¿Cómo puedo personalizar la apariencia del título del botón de opción, como el tamaño y el color de la fuente?

 A: Puede personalizar la apariencia del título del botón de opción ajustando las propiedades del mismo.`TextFragment` Se utiliza para el título. Por ejemplo, puede configurar la fuente, el tamaño de fuente, el color, el interlineado y otras opciones de formato de texto.

#### P: ¿Es posible agregar múltiples opciones de botones de opción con diferentes subtítulos a un solo grupo de botones de opción?

R: Sí, puedes agregar varias opciones de botones de opción con diferentes títulos a un solo grupo de botones de opción. Cada opción representará una elección diferente y los usuarios pueden seleccionar solo una opción del grupo.

#### P: ¿Puedo usar Aspose.PDF para .NET para modificar otros campos de formulario en un documento PDF?

R: Sí, Aspose.PDF para .NET ofrece un conjunto completo de funciones para manipular diversos campos de formulario en un documento PDF, como campos de texto, casillas de verificación, listas desplegables y más. Puede utilizar la biblioteca para establecer valores, modificar apariencias y agregar interactividad a los campos de formulario.

#### P: ¿Aspose.PDF para .NET admite el trabajo con archivos PDF generados a partir de otras fuentes, como documentos escaneados?

R: Sí, Aspose.PDF para .NET permite trabajar con archivos PDF generados a partir de diversas fuentes, incluidos documentos escaneados. La biblioteca ofrece funciones de OCR (reconocimiento óptico de caracteres) para extraer texto de archivos PDF escaneados y manipular el contenido mediante programación.