---
title: Caja de texto
linktitle: Caja de texto
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a crear un campo de texto en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 290
url: /es/net/programming-with-forms/text-box/
---
En esta guía, explicaremos paso a paso cómo utilizar la biblioteca Aspose.PDF para .NET para crear un campo de texto en un documento PDF. Le mostraremos cómo abrir el documento, crear el campo de texto, personalizar sus propiedades y guardar el PDF editado.

## Paso 1: Configurar el directorio de documentos

 El primer paso es configurar el directorio de documentos donde se encuentra el archivo PDF con el que desea trabajar. Puedes usar el`dataDir` variable para especificar la ruta del directorio.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Asegúrate de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: abrir el documento PDF

En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Asegúrese de que el archivo PDF esté presente en el directorio de documentos especificado.

## Paso 3: crear el campo de texto

 Crearemos un campo de texto usando el`TextBoxField` clase. Puede especificar las coordenadas de posición y el tamaño del campo utilizando el`Rectangle` clase.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Personalice las coordenadas, el tamaño, el nombre parcial y el valor del campo de texto según sea necesario.

## Paso 4: personaliza las propiedades del campo de texto

En este paso, personalizaremos las propiedades del campo de texto como borde, color, etc.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Personalice las propiedades del campo de texto según sus preferencias.

## Paso 5: Agregar el campo al documento

Ahora que hemos creado y configurado el campo de texto, podemos agregarlo al documento PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Paso 6: guardar el PDF modificado

 Finalmente, podemos guardar el PDF modificado usando el`Save` método de la`Document` clase.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Asegúrese de especificar la ruta completa y el nombre del archivo del PDF editado.

### Código fuente de muestra para Text Box usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Crear un campo
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = nuevo borde (
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Agregar campo al documento
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Guardar PDF modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Conclusión

En esta guía, aprendimos cómo utilizar la biblioteca Aspose.PDF para .NET para crear un campo de texto en un documento PDF. Siguiendo los pasos descritos, puede personalizar las propiedades del campo de texto y agregarlo al documento según sea necesario. No dude en explorar más a fondo las funciones de Aspose.PDF para .NET para ampliar las posibilidades de manipulación de archivos PDF.

### Preguntas frecuentes

#### P: ¿Puedo usar Aspose.PDF para .NET para crear múltiples campos de texto en un solo documento PDF?

R: Sí, puede crear varios campos de texto en un solo documento PDF utilizando Aspose.PDF para .NET. Simplemente repita el proceso de creación y personalización de campos de texto para cada ubicación deseada en el documento.

#### P: ¿Cómo puedo personalizar la apariencia del campo de texto, como el tamaño y el color de la fuente?

R: Puedes personalizar la apariencia del campo de texto ajustando sus propiedades, como tamaño de fuente, estilo de fuente, color, estilo de borde, color de fondo y más. En el código fuente de muestra proporcionado, se personalizan el ancho del borde, el patrón de guiones del borde y el color del texto.

#### P: ¿Es posible extraer el texto ingresado por el usuario del campo de texto creado?

R: Sí, puede extraer el texto ingresado por el usuario del campo de texto creado. Después de que los usuarios completen el campo de texto en el documento PDF, puede recuperar mediante programación el valor del campo usando Aspose.PDF para .NET.

#### P: ¿Puedo agregar campos de texto a un documento PDF existente sin crear uno nuevo?

R: Sí, puedes agregar campos de texto a un documento PDF existente sin crear uno nuevo. Aspose.PDF para .NET brinda la capacidad de modificar documentos PDF existentes, incluida la adición de campos de texto, casillas de verificación y otros elementos de formulario.

#### P: ¿Aspose.PDF para .NET admite otros tipos de campos de formulario, como casillas de verificación y botones de opción?

R: Sí, Aspose.PDF para .NET admite varios tipos de campos de formulario, incluidas casillas de verificación, botones de opción, listas desplegables y más. Puede utilizar la biblioteca para trabajar con diferentes tipos de elementos de formulario en documentos PDF.