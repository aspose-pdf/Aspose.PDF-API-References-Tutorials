---
title: Añadir tabla de contenido
linktitle: Añadir tabla de contenido
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar una tabla de contenido a documentos PDF usando Aspose.PDF para .NET. Guía paso a paso con código fuente de ejemplo. ¡Mejora la navegación de documentos!
type: docs
weight: 40
url: /es/net/programming-with-document/addtoc/
---

En este tutorial, exploraremos cómo usar la función Agregar TOC (Tabla de contenido) de Aspose.PDF para .NET para agregar una tabla de contenido a los documentos PDF. Proporcionaremos una guía paso a paso y explicaremos el código fuente de C# necesario para lograrlo. Al final de este tutorial, podrá generar un documento PDF con una tabla de contenido utilizando Aspose.PDF para .NET.


## Paso 1: Cargue el archivo PDF existente

Para comenzar, necesitamos cargar un archivo PDF existente. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su archivo PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Paso 2: Cree una nueva página para la tabla de contenido

Crearemos una nueva página para contener la tabla de contenido. El siguiente código inserta una nueva página en el índice 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Paso 3: Definir la información de la tabla de contenido

A continuación, necesitamos definir la información de la tabla de contenido. Estableceremos el título y otras propiedades de la tabla de contenido. Agrega el siguiente código:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Paso 4: Crear elementos TOC

Ahora, crearemos los elementos de la tabla de contenido. En este tutorial, crearemos cuatro elementos TOC correspondientes a diferentes páginas. Modifique el siguiente código según sus requisitos:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Paso 5: Guarde el documento actualizado

 Finalmente, necesitamos guardar el documento modificado con la tabla de contenido. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta del archivo de salida deseado:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para agregar TOC a documentos PDF usando Aspose.PDF para .NET

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Cargue un archivo PDF existente
Document doc = new Document(dataDir + "AddTOC.pdf");

// Obtenga acceso a la primera página del archivo PDF
Page tocPage = doc.Pages.Insert(1);

// Crear objeto para representar información TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Establecer el título para TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

// Cree objetos de cadena que se utilizarán como elementos TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Crear objeto de encabezado
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Especificar la página de destino para el objeto de encabezado
	heading2.DestinationPage = doc.Pages[i + 2];

	// página de destino
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Coordenada de destino
	segment2.Text = titles[i];

	// Agregar encabezado a la página que contiene TOC
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Guardar el documento actualizado
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```
