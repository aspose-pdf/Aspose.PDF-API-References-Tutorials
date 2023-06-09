---
title: Agregar sello de fecha y hora
linktitle: Agregar sello de fecha y hora
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar fácilmente una marca de fecha y hora a sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 10
url: /es/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
En este artículo, lo guiaremos paso a paso sobre cómo agregar una marca de fecha y hora usando Aspose.PDF para .NET. Le mostraremos cómo usar el código fuente de C# provisto para agregar una marca de fecha y hora a un documento PDF existente.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 1: Configuración del entorno

Antes de que pueda agregar una marca de fecha y hora a un documento PDF, debe configurar su entorno de desarrollo. Estos son los pasos a seguir:

1. Abra su IDE (Entorno de desarrollo integrado) favorito.
2. Cree un nuevo proyecto de C#.
3. Asegúrese de haber agregado una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: agregar la biblioteca Aspose.PDF

Se requiere la biblioteca Aspose.PDF para .NET para trabajar con documentos PDF en su proyecto.

## Paso 3: Cargar el documento PDF

El primer paso para agregar una marca de fecha y hora es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abre el documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 4: Creación de la marca de fecha y hora

Ahora que ha subido el documento

  PDF, puede crear la marca de fecha y hora para agregar. Aquí está cómo hacerlo:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Crear un búfer de texto
TextStamp textStamp = new TextStamp(annotationText);
```

El código anterior crea un nuevo búfer de texto que contiene la fecha y la hora actuales.

## Paso 5: Configuración de las propiedades del sello

Antes de agregar el sello al documento PDF, puede configurar varias propiedades del sello, como el margen, la alineación horizontal y vertical, etc. Así es como se hace:

```csharp
// Establecer propiedades de búfer
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Puede ajustar estas propiedades según sus necesidades.

## Paso 6: Agregar sello a PDF

Ahora que la marca de fecha y hora está lista, puede agregarla a una página específica del documento PDF. Así es cómo:

```csharp
// Agregar el sello a la colección de sellos de la página
pdfDocument.Pages[1].AddStamp(textStamp);
```

El código anterior agrega el sello a la primera página del documento PDF. Puede especificar otra página si es necesario.

## Paso 7: Guarde el documento de salida

Una vez que haya agregado la marca de fecha y hora, puede guardar el documento PDF modificado. Así es cómo:

```csharp
// Guardar el documento de salida
pdfDocument.Save(dataDir);
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Ejemplo de código fuente para Agregar sello de fecha y hora usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Crear sello de texto
TextStamp textStamp = new TextStamp(annotationText);

// Establecer propiedades del sello
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Agregar sello en la colección de sellos
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Guardar documento de salida
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Conclusión

¡Felicidades! Aprendió a agregar una marca de fecha y hora usando Aspose.PDF para .NET. Ahora puede aplicar este conocimiento a sus propios proyectos para agregar marcas de fecha y hora a los documentos PDF.
