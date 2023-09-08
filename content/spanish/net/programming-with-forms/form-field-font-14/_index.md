---
title: Fuente de campo de formulario 14
linktitle: Fuente de campo de formulario 14
second_title: Aspose.PDF para referencia de API .NET
description: Configure fácilmente la fuente de los campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-forms/form-field-font-14/
---
En este tutorial, le mostraremos cómo configurar la fuente de un campo de formulario usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establecer la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

Abra el documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Paso 3: obtenga un campo de formulario particular

Obtenga el campo de formulario deseado (en este ejemplo, usamos el campo "cuadro de texto1"):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Paso 4: crea un objeto de fuente

Cree un objeto de fuente para la nueva fuente que desea usar (por ejemplo, "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Paso 5: configurar la información de fuente para el campo del formulario

Configure la información de fuente para el campo del formulario usando la fuente creada anteriormente:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Paso 6: guarde el documento actualizado

Guarde el documento PDF actualizado:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Código fuente de muestra para Form Field Font 14 usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Obtener un campo de formulario particular del documento
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Crear objeto de fuente
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Establecer la información de fuente para el campo de formulario
// Field.DefaultAppearance = nuevo Aspose.Pdf.Forms.in.DefaultAppearance(fuente, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo configurar la fuente de un campo de formulario usando Aspose.PDF para .NET. Siguiendo estos pasos, puede especificar fácilmente la fuente y el tamaño de fuente para los campos de formulario en sus documentos PDF usando Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Puedo utilizar cualquier fuente para los campos de formulario en Aspose.PDF para .NET?

R: Sí, puede utilizar cualquier fuente TrueType u OpenType para los campos de formulario en Aspose.PDF para .NET. Siempre que la fuente esté disponible e instalada en el sistema o sea accesible a través de FontRepository, puede usarla para personalizar la apariencia del texto del campo del formulario.

#### P: ¿Cómo encuentro las fuentes disponibles en Aspose.PDF para .NET?

 R: Para encontrar las fuentes disponibles en Aspose.PDF para .NET, puede utilizar el`FontRepository.GetAvailableFonts()`método. Este método devuelve una variedad de fuentes disponibles que puede usar para campos de formulario o cualquier otra operación relacionada con el texto en su documento PDF.

#### P: ¿Puedo cambiar el tamaño de fuente de los campos del formulario a cualquier valor?

R: Sí, puede cambiar el tamaño de fuente de los campos del formulario a cualquier valor numérico positivo utilizando Aspose.PDF para .NET. Sin embargo, es esencial asegurarse de que el tamaño de fuente sea apropiado para el campo específico del formulario y no provoque el truncamiento del texto o la superposición con otros elementos del documento.

#### P: ¿Puedo cambiar el color de fuente de los campos del formulario?

R: Sí, puede cambiar el color de fuente de los campos del formulario usando Aspose.PDF para .NET. En el código fuente de C# proporcionado, el color de fuente está configurado en negro (`System.Drawing.Color.Black`), pero puede personalizarlo con cualquier otro valor de color válido.

#### P: ¿Cómo puedo alinear el texto dentro del campo del formulario?

 R: Para alinear el texto dentro del campo del formulario, puede utilizar el`Multiline`propiedad del campo del formulario y configúrelo en verdadero. Esta propiedad habilita texto de varias líneas dentro del campo del formulario, lo que le permite controlar la alineación del texto con saltos de línea y retornos de carro.