---
title: Agregar sello de fecha y hora en archivo PDF
linktitle: Agregar sello de fecha y hora en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda cómo agregar fácilmente una marca de fecha y hora en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 10
url: /es/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
En este artículo, le mostraremos paso a paso cómo agregar una marca de fecha y hora en un archivo PDF con Aspose.PDF para .NET. Le mostraremos cómo usar el código fuente de C# proporcionado para agregar una marca de fecha y hora a un archivo PDF existente.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 1: Configuración del entorno

Antes de poder agregar una marca de fecha y hora a un documento PDF, debe configurar su entorno de desarrollo. Estos son los pasos a seguir:

1. Abra su IDE (entorno de desarrollo integrado) favorito.
2. Crear un nuevo proyecto C#.
3. Asegúrese de haber agregado una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Agregar la biblioteca Aspose.PDF

La biblioteca Aspose.PDF para .NET es necesaria para trabajar con documentos PDF en su proyecto.

## Paso 3: Cargar el documento PDF

El primer paso para agregar una marca de fecha y hora es cargar el documento PDF existente en el proyecto. A continuación, le indicamos cómo hacerlo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Abrir el documento
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 4: Creación de la marca de fecha y hora

Ahora que has cargado el documento

  PDF, puedes crear la marca de fecha y hora para agregarla. Aquí te explicamos cómo hacerlo:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Crear un buffer de texto
TextStamp textStamp = new TextStamp(annotationText);
```

El código anterior crea un nuevo búfer de texto que contiene la fecha y hora actuales.

## Paso 5: Configuración de las propiedades del sello

Antes de agregar el sello al documento PDF, puede configurar varias propiedades del sello, como el margen, la alineación horizontal y vertical, etc. A continuación, le indicamos cómo hacerlo:

```csharp
// Establecer propiedades del buffer
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Puede ajustar estas propiedades según sus necesidades.

## Paso 6: Agregar sello al PDF

Ahora que la marca de fecha y hora está lista, puede agregarla a una página específica del documento PDF. A continuación, le indicamos cómo hacerlo:

```csharp
// Añade el sello a la colección de sellos de la página
pdfDocument.Pages[1].AddStamp(textStamp);
```

El código anterior agrega el sello a la primera página del documento PDF. Puede especificar otra página si es necesario.

## Paso 7: Guarde el documento de salida

Una vez que hayas añadido la fecha y la hora, puedes guardar el documento PDF modificado. A continuación te indicamos cómo hacerlo:

```csharp
// Guardar el documento de salida
pdfDocument.Save(dataDir);
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Código fuente de muestra para agregar una marca de fecha y hora mediante Aspose.PDF para .NET 
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

// Añadir sello a la colección de sellos
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

¡Felicitaciones! Aprendió a agregar una marca de fecha y hora con Aspose.PDF para .NET. Ahora puede aplicar este conocimiento a sus propios proyectos para agregar marcas de fecha y hora a documentos PDF.

### Preguntas frecuentes sobre cómo agregar una marca de fecha y hora en un archivo PDF

#### P: ¿Cuál es el propósito de agregar una marca de fecha y hora a un documento PDF usando Aspose.PDF para .NET?

A: Agregar una marca de fecha y hora a un documento PDF mejora su valor informativo al indicar cuándo se modificó o creó el documento. Esta función es útil para realizar un seguimiento de los cambios en el documento y proporcionar un punto de referencia para el historial del documento.

#### P: ¿Puedo personalizar el formato de la marca de fecha y hora para que coincida con requisitos específicos?

 R: Sí, puede personalizar el formato de la marca de fecha y hora según sus preferencias. El código fuente C# proporcionado utiliza el`DateTime.Now.ToString()` Método para generar la marca de tiempo en un formato específico. Puede modificar este código para formatear la marca de tiempo según sea necesario.

#### P: ¿Es posible agregar la fecha y la hora en una ubicación específica en una página PDF?

 R: Por supuesto, puede ajustar la ubicación de la marca de fecha y hora en la página PDF modificando las propiedades del`TextStamp` objeto. El código proporcionado en el tutorial demuestra cómo establecer propiedades como margen, alineación y posicionamiento vertical.

#### P: ¿Puedo agregar múltiples sellos de fecha y hora a diferentes páginas del mismo documento PDF?

 R: Sí, puede agregar varias marcas de fecha y hora a distintas páginas del mismo documento PDF. Simplemente repita el proceso de creación de una`TextStamp` objeto y configurar sus propiedades para cada página deseada.

#### P: ¿Cómo puedo cambiar la fuente, el tamaño o el color del texto del sello de fecha y hora?

 A: Para modificar la fuente, el tamaño o el color del texto del sello de fecha y hora, puede personalizar las propiedades del`DefaultAppearance` objeto utilizado para crear el`TextStamp`. Ajuste el nombre de la fuente, el tamaño y los valores de color para lograr la apariencia deseada.

#### P: ¿Es posible agregar otros tipos de anotaciones o sellos a un documento PDF usando Aspose.PDF para .NET?

R: Sí, Aspose.PDF para .NET ofrece una amplia variedad de tipos de anotaciones que puede agregar a documentos PDF, incluidas anotaciones de texto, sellos, líneas, formas y más. Puede explorar la documentación de Aspose.PDF para obtener más detalles sobre cómo trabajar con anotaciones.

#### P: ¿Existen limitaciones o consideraciones al agregar una marca de fecha y hora a un documento PDF?

R: Si bien agregar una marca de fecha y hora es sencillo, tenga en cuenta factores como el diseño del documento y el contenido existente. Asegúrese de que la ubicación de la marca no oculte información importante ni afecte la legibilidad del documento.

#### P: ¿Cómo puedo integrar este método en mis propios proyectos para agregar marcas de fecha y hora a los documentos PDF?

R: Para integrar este método, siga los pasos indicados y ajuste el código para que se adapte a la estructura de su proyecto. Puede agregar marcas de fecha y hora a los documentos PDF existentes para mejorar su utilidad y proporcionar una cronología clara de los cambios.

#### P: ¿Puedo automatizar el proceso de agregar marcas de fecha y hora a varios documentos PDF?

R: Sí, puede automatizar el proceso de agregar sellos de fecha y hora a varios documentos PDF creando un script o programa que recorra una lista de documentos y aplique el mismo proceso de sello a cada uno.