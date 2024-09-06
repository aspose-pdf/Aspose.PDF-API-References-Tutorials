---
title: Aplicar estilo de número en archivo PDF
linktitle: Aplicar estilo de número en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a aplicar un estilo de numeración a los encabezados de un archivo PDF con Aspose.PDF para .NET. Guía paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-headings/apply-number-style/
---
En este tutorial, lo guiaremos a través del siguiente código fuente de C# paso a paso para aplicar el estilo de numeración en un archivo PDF usando Aspose.PDF para .NET.

Asegúrese de haber instalado la biblioteca Aspose.PDF y de haber configurado su entorno de desarrollo antes de comenzar. Además, debe tener conocimientos básicos de programación en C#.

### Paso 1: Configuración del directorio de documentos

En el código fuente proporcionado, debe especificar el directorio en el que desea guardar el archivo PDF generado. Cambie la variable "dataDir" al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Paso 2: Creación del documento PDF

Creamos un nuevo documento PDF con dimensiones y márgenes especificados.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Paso 3: Creación de una página y un contenedor flotante

Agregamos una página al documento y creamos un contenedor flotante para organizar el contenido.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Paso 4: Agregar encabezados con numeración

Creamos encabezados con numeraciones específicas y los agregamos al contenedor flotante.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Paso 5: Guardar el documento PDF

Guardamos el documento PDF generado en el directorio especificado.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Código fuente de muestra para aplicar estilo de número con Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Conclusión

En este tutorial, explicamos cómo aplicar un estilo de numeración a los encabezados de un documento PDF mediante Aspose.PDF para .NET. Ahora puede utilizar este conocimiento para crear documentos PDF con numeraciones personalizadas para los encabezados.

### Preguntas frecuentes sobre cómo aplicar estilos de números en archivos PDF

#### P: ¿Qué es el estilo de numeración en un documento PDF?

R: El estilo de numeración se refiere al formato en el que se numeran los encabezados o las secciones en un documento PDF. Puede incluir números, letras u otros caracteres para proporcionar una estructura jerárquica.

#### P: ¿Por qué necesitaría aplicar un estilo de numeración a los encabezados de un documento PDF?

R: La aplicación de un estilo de numeración a los encabezados mejora la legibilidad y la organización del documento PDF. Ayuda a los lectores a navegar fácilmente y a comprender la estructura jerárquica del contenido.

#### P: ¿Qué es Aspose.PDF para .NET?

A: Aspose.PDF para .NET es una biblioteca que permite a los desarrolladores trabajar con archivos PDF de forma programada en aplicaciones .NET. Ofrece una amplia gama de funciones para crear, editar, convertir y manipular documentos PDF.

#### P: ¿Cómo importo las bibliotecas necesarias para mi proyecto C#?

R: Para importar las bibliotecas necesarias para su proyecto C#, incluya las siguientes directivas de importación:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Estas directivas le permiten acceder a las clases y métodos necesarios para trabajar con documentos PDF y aplicar estilos de numeración.

#### P: ¿Cómo especifico el directorio para guardar el archivo PDF generado?

R: En el código fuente proporcionado, modifique la variable "dataDir" para especificar el directorio donde desea guardar el archivo PDF generado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta del directorio actual.

#### P: ¿Cómo puedo crear un documento PDF con dimensiones y márgenes específicos?

R: Para crear un documento PDF con dimensiones y márgenes específicos, utilice el siguiente código:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### P: ¿Cómo puedo agregar encabezados con estilo de numeración al documento PDF?

A: Para agregar encabezados con estilo de numeración al documento PDF, use los ejemplos de código provistos para crear encabezados y personalizar sus estilos de numeración. Ajuste propiedades como texto, estilo de numeración, número inicial y secuencia automática según sea necesario.

#### P: ¿Cómo guardo el documento PDF generado?

 A: Para guardar el documento PDF generado, utilice el`Save` método de la`pdfDoc` objeto:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### P: ¿Cómo puedo confirmar que se ha aplicado el estilo de numeración?

A: Abra el archivo PDF generado para verificar que el estilo de numeración especificado se haya aplicado a los encabezados.

#### P: ¿Puedo personalizar aún más el estilo de numeración?

 R: Sí, puede personalizar aún más el estilo de numeración ajustando las propiedades de la`Heading` objetos, como tipo de estilo de numeración, número de inicio y secuencia automática.

#### P: ¿Puedo aplicar diferentes estilos de numeración a diferentes secciones del documento?

 R: Sí, puede aplicar diferentes estilos de numeración a diferentes secciones del documento creando múltiples`Heading` objetos con diferentes estilos y secuencias.