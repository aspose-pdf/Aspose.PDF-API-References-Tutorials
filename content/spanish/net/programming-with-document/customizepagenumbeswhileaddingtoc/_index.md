---
title: Personalice los números de página mientras agrega TOC
linktitle: Personalice los números de página mientras agrega TOC
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a personalizar los números de página mientras agrega una tabla de contenido (TOC) usando Aspose.PDF para .NET con esta guía paso a paso y un ejemplo de código.
type: docs
weight: 100
url: /es/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
En este tutorial, exploraremos cómo personalizar los números de página mientras agregamos una tabla de contenido (TOC) usando Aspose.PDF para .NET. Le proporcionaremos orientación paso a paso, junto con un ejemplo de código, para ayudarle a lograrlo.

## Paso 1: cargar un archivo PDF existente

Primero, necesitamos cargar un archivo PDF existente. Para este tutorial, usaremos el archivo "42824.pdf" ubicado en el directorio "SU DIRECTORIO DE DOCUMENTOS". Reemplace esta ruta de directorio con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Paso 2: Agregar una página TOC

 A continuación, debemos agregar una nueva página al principio del documento para que sirva como página TOC. Esto lo podemos lograr utilizando el`Insert()` método de la`Pages` colección de la`Document` objeto.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Paso 3: crear un objeto TOC

 Para crear un objeto TOC, primero necesitamos crear un`TocInfo` objeto y establecer sus propiedades. En este tutorial, estableceremos el título del TOC en "Tabla de contenido" y el prefijo del número de página en "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Paso 4: Crear entradas TOC

Para crear entradas TOC, debemos recorrer todas las páginas del documento, excepto la página TOC, y crear un objeto de encabezado para cada página. Luego podemos agregar el objeto de encabezado a la página TOC y especificar su página de destino.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Crear objeto de encabezado
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Especificar la página de destino para el objeto de encabezado
    heading2.DestinationPage = doc.Pages[i + 1];
    // Página de destino
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Coordenada de destino
    segment2.Text = "Page " + i.ToString();
    // Agregar encabezado a la página que contiene TOC
    tocPage.Paragraphs.Add(heading2);
}
```

## Paso 5: guardar el documento actualizado

Finalmente, necesitamos guardar el documento actualizado en un archivo nuevo. Esto lo podemos lograr utilizando el`Save()` método de la`Document` objeto.

```csharp
doc.Save(outFile);
```

### Código fuente de ejemplo para personalizar los números de página mientras se agrega TOC usando Aspose.PDF para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Cargar archivos PDF existentes
Document doc = new Document(inFile);
// Obtenga acceso a la primera página del archivo PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Crear objeto para representar información TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Establecer el título para TOC
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Crear objeto de encabezado
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Especificar la página de destino para el objeto de encabezado
	heading2.DestinationPage = doc.Pages[i + 1];
	// Página de destino
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Coordenada de destino
	segment2.Text = "Page " + i.ToString();
	// Agregar encabezado a la página que contiene TOC
	tocPage.Paragraphs.Add(heading2);
}

// Guardar el documento actualizado
doc.Save(outFile);
```

## Conclusión

En este tutorial, proporcionamos orientación paso a paso sobre cómo personalizar los números de página mientras agregamos una tabla de contenido usando Aspose.PDF para .NET. También proporcionamos un ejemplo de código que puede utilizar como referencia al implementar esta función en su

### Preguntas frecuentes

#### P: ¿Qué es una tabla de contenido (TOC) en un documento PDF?

R: Una tabla de contenido (TOC) en un documento PDF es una ayuda para la navegación que proporciona una lista organizada de secciones o capítulos del documento junto con sus números de página correspondientes. Permite a los lectores navegar rápidamente a secciones específicas del documento.

#### P: ¿Por qué querría personalizar los números de página en una tabla de contenidos?

R: Personalizar los números de página en una tabla de contenido puede resultar útil cuando desea utilizar un formato de numeración de páginas específico o incluir información adicional junto con los números de página. Le permite crear una tabla de contenidos más personalizada e informativa.

#### P: ¿Puedo incluir hipervínculos en el TOC para vincular a secciones o páginas específicas dentro del documento PDF?

R: Sí, Aspose.PDF para .NET le permite crear hipervínculos en el TOC que enlazan con secciones o páginas específicas dentro del documento PDF. Esto mejora la interactividad y navegación del documento PDF.

#### P: ¿Aspose.PDF para .NET es compatible con los estándares PDF/A?

R: Sí, Aspose.PDF para .NET admite los estándares PDF/A, incluidos PDF/A-1, PDF/A-2 y PDF/A-3. Le permite crear documentos PDF que cumplen con los requisitos de archivo y preservación a largo plazo.

#### P: ¿Puedo agregar más formato a las entradas de la TOC, como estilos de fuente o colores?

R: Sí, puede agregar formato adicional a las entradas de la TOC, como estilos de fuente, colores y tamaños de fuente, utilizando Aspose.PDF para .NET. Esto le permite personalizar la apariencia del TOC según sus requisitos.
