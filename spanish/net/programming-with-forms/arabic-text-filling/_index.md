---
title: Relleno de texto árabe
linktitle: Relleno de texto árabe
second_title: Referencia de API de Aspose.PDF para .NET
description: Rellene fácilmente los campos de formulario PDF con texto en árabe utilizando Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-forms/arabic-text-filling/
---

En este tutorial, aprenderemos cómo llenar un campo de formulario PDF con texto en árabe usando Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que permite a los desarrolladores manipular documentos PDF mediante programación. Lo guiaremos a través del proceso paso a paso, explicando el código fuente de C# necesario para realizar esta tarea.

## Paso 1: Cargue el contenido del formulario PDF

Primero, necesitamos cargar el formulario PDF que contiene el campo que queremos llenar. Comenzamos definiendo la ruta al directorio donde se encuentra el formulario:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 A continuación, creamos un`FileStream` objeto para leer y escribir el archivo de formulario:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 A continuación, instanciamos un`Document` objeto usando la secuencia que contiene el archivo de formulario:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Paso 2: Accede al campo TextBoxField

 Para llenar el campo del formulario con texto en árabe, necesitamos acceder al`TextBoxField` campo que queremos llenar. En este ejemplo, asumimos que el nombre del campo es "textbox1". Podemos recuperar la referencia de campo usando el`Form` propiedad de la`pdfDocument` objeto:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Paso 3: Complete el campo del formulario con texto en árabe

 Ahora que tenemos la`TextBoxField` referencia, podemos asignar el texto árabe a su`Value` propiedad:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## Paso 4: Guarde el documento actualizado

Finalmente, guardamos el documento actualizado en un nuevo archivo:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

También mostramos un mensaje para indicar el éxito de completar el texto en árabe:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### Ejemplo de código fuente para el relleno de texto en árabe con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar contenido del formulario PDF
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
//Crear una instancia de documento con un archivo de formulario de retención de flujo
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Obtener la referencia de un TextBoxField particular
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// Rellenar campo de formulario con texto en árabe
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, exploramos cómo llenar un campo de formulario PDF con texto en árabe usando Aspose.PDF para .NET. Recorrimos el proceso paso a paso y explicamos el código fuente de C# relevante. Siguiendo estas instrucciones, puede integrar fácilmente la funcionalidad de relleno de texto en árabe en sus aplicaciones .NET. Si tiene más preguntas o necesita más información, no dude en ponerse en contacto con el equipo de soporte de Aspose.PDF o consulte los recursos adicionales a continuación.