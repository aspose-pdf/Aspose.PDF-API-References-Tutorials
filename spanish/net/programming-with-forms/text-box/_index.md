---
title: Caja de texto
linktitle: Caja de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear un campo de texto en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 290
url: /es/net/programming-with-forms/text-box/
---

En esta guía, explicaremos paso a paso cómo usar la biblioteca Aspose.PDF para .NET para crear un campo de texto en un documento PDF. Le mostraremos cómo abrir el documento, crear el campo de texto, personalizar sus propiedades y guardar el PDF editado.

## Paso 1: Configuración del directorio de documentos

 El primer paso es configurar el directorio del documento donde se encuentra el archivo PDF en el que desea trabajar. Puedes usar el`dataDir`variable para especificar la ruta del directorio.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: Abrir el documento PDF

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Asegúrese de que el archivo PDF esté presente en el directorio de documentos especificado.

## Paso 3: Crear el campo de texto

 Crearemos un campo de texto usando el`TextBoxField` clase. Puede especificar las coordenadas de posición y el tamaño del campo utilizando el`Rectangle` clase.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Personalice las coordenadas, el tamaño, el nombre parcial y el valor del campo de texto según sea necesario.

## Paso 4: Personaliza las propiedades del campo de texto

En este paso, personalizaremos las propiedades del campo de texto, como borde, color, etc.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Personaliza las propiedades del campo de texto según tus preferencias.

## Paso 5: agregar el campo al documento

Ahora que hemos creado y configurado el campo de texto, podemos agregarlo al documento PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Paso 6: Guardar el PDF modificado

 Finalmente, podemos guardar el PDF modificado usando el`Save` metodo de la`Document` clase.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Asegúrese de especificar la ruta completa y el nombre de archivo del PDF editado.

### Ejemplo de código fuente para Text Box usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// crear un campo
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = nuevo borde (
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

En esta guía, aprendimos a usar la biblioteca Aspose.PDF para .NET para crear un campo de texto en un documento PDF. Siguiendo los pasos descritos, puede personalizar las propiedades del campo de texto y agregarlo al documento según sea necesario. Siéntase libre de explorar más a fondo las funciones de Aspose.PDF para .NET para ampliar las posibilidades de manipular archivos PDF.