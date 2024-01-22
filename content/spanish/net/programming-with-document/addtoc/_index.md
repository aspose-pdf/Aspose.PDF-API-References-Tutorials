---
title: Agregar TOC al archivo PDF
linktitle: Agregar TOC al archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar una tabla de contenido a un archivo PDF usando Aspose.PDF para .NET. Guía paso a paso con código fuente de ejemplo. ¡Impulsa la navegación de documentos!
type: docs
weight: 40
url: /es/net/programming-with-document/addtoc/
---
En este tutorial, exploraremos cómo utilizar la función Agregar TOC (Tabla de contenido) a un archivo PDF de Aspose.PDF para .NET para agregar una tabla de contenido a documentos PDF. Proporcionaremos una guía paso a paso y explicaremos el código fuente de C# necesario para lograrlo. Al final de este tutorial, podrá generar un documento PDF con una tabla de contenido usando Aspose.PDF para .NET.


## Paso 1: cargue el archivo PDF existente

 Para comenzar, necesitamos cargar un archivo PDF existente. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su archivo PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Paso 2: cree una nueva página para la tabla de contenido

Crearemos una nueva página para contener la tabla de contenidos. El siguiente código inserta una nueva página en el índice 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Paso 3: definir la información del índice

A continuación, debemos definir la información de la tabla de contenido. Estableceremos el título y otras propiedades de la tabla de contenido. Agregue el siguiente código:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Paso 4: crear elementos TOC

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

## Paso 5: guarde el documento actualizado

 Finalmente, necesitamos guardar el documento modificado con la tabla de contenido. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta del archivo de salida deseada:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Código fuente de ejemplo para agregar TOC a documentos PDF usando Aspose.PDF para .NET

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar archivos PDF existentes
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

//Cree objetos de cadena que se utilizarán como elementos TOC
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

	// Página de destino
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

## Conclusión

En este tutorial, exploramos cómo agregar una tabla de contenido (TOC) a documentos PDF usando Aspose.PDF para .NET. Si sigue la guía paso a paso y utiliza el código fuente C# proporcionado, puede generar fácilmente un documento PDF con una tabla de contenido. El TOC mejora la usabilidad del documento, permitiendo a los usuarios navegar a secciones o páginas específicas de manera más eficiente. Aspose.PDF para .NET proporciona una solución sólida y fácil de usar para trabajar con archivos PDF en aplicaciones .NET, lo que le permite crear documentos PDF dinámicos e interactivos con facilidad.

### Preguntas frecuentes para agregar TOC a un archivo PDF

#### P: ¿Qué es Aspose.PDF para .NET?

R: Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores trabajar con archivos PDF en aplicaciones .NET de forma eficaz. Proporciona una amplia gama de funciones para crear, manipular y administrar documentos PDF mediante programación.

#### P: ¿Cuál es el propósito de agregar una tabla de contenido (TOC) a un documento PDF?

R: La tabla de contenido (TOC) proporciona una ayuda de navegación para los usuarios, permitiéndoles saltar rápidamente a secciones o páginas específicas dentro del documento PDF. Mejora la usabilidad del documento y la experiencia de usuario.

#### P: ¿Cómo agrego una tabla de contenido a un documento PDF usando Aspose.PDF para .NET?

R: Para agregar una tabla de contenido a un documento PDF usando Aspose.PDF para .NET, necesita crear una nueva página para contener la tabla de contenido, definir la información de la tabla de contenido y luego crear elementos de la tabla de contenido que correspondan a páginas específicas o secciones del documento.

#### P: ¿Puedo personalizar la apariencia de la tabla de contenido?

R: Sí, puede personalizar la apariencia de la tabla de contenido configurando varias propiedades de los elementos de la TOC, como el tamaño de fuente, el estilo de fuente y la alineación. Aspose.PDF para .NET brinda flexibilidad en el diseño del TOC para que coincida con la apariencia deseada.

#### P: ¿Aspose.PDF para .NET es adecuado para agregar funciones avanzadas a documentos PDF?

R: Por supuesto, Aspose.PDF para .NET es una biblioteca rica en funciones que le permite agregar funcionalidades avanzadas a documentos PDF, incluidos elementos interactivos, campos de formulario, firmas digitales y más.