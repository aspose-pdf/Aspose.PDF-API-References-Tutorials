---
title: Ocultar números de página en la tabla de contenido
linktitle: Ocultar números de página en la tabla de contenido
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a ocultar números de página en una tabla de contenido usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 220
url: /es/net/programming-with-document/hidepagenumbersintoc/
---
En este artículo, analizaremos la implementación de la función Ocultar números de página en la TOC de Aspose.PDF para .NET usando C#. Comenzaremos con una breve introducción a Aspose.PDF para .NET y luego profundizaremos en la guía paso a paso para implementar esta función. 

## Introducción a Aspose.PDF para .NET

Aspose.PDF para .NET es un potente componente de manipulación de PDF que permite a los desarrolladores crear, editar y manipular archivos PDF mediante programación. Proporciona una amplia gama de características y funcionalidades que facilitan el trabajo con documentos PDF. Aspose.PDF para .NET es compatible con sistemas operativos de 32 y 64 bits y se puede usar con las plataformas .NET Framework, .NET Core y Xamarin. 

## ¿Qué es la función Ocultar números de página en la TOC?

La tabla de contenido (TOC) es una parte esencial de un documento PDF que brinda a los usuarios una descripción general rápida del contenido. A veces, los usuarios pueden querer ocultar los números de página en la tabla de contenido para que sea más fácil de usar. Aspose.PDF para .NET proporciona una función integrada para ocultar los números de página en la TOC. Esta función se puede utilizar para crear documentos PDF más fáciles de usar. 

## requisitos previos

Para seguir este tutorial, necesitará lo siguiente:

- Visual Studio 2010 o posterior
- Aspose.PDF para .NET instalado en su sistema
- Conocimientos básicos del lenguaje de programación C#

## Guía paso a paso para implementar la función Ocultar números de página en TOC

Siga los pasos a continuación para implementar la función Ocultar números de página en la TOC usando Aspose.PDF para .NET:

## Paso 1: Cree una nueva aplicación de consola C# en Visual Studio

Abra Visual Studio y cree una nueva aplicación de consola C#.

## Paso 2: agregue una referencia a Aspose.PDF para .NET

Haga clic derecho en la carpeta Referencias en su proyecto y seleccione Agregar referencia. Vaya a la ubicación donde está instalado Aspose.PDF para .NET en su sistema y agréguele una referencia.

## Paso 1: Crea un nuevo documento PDF

Cree un nuevo documento PDF usando el siguiente código:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Paso 2: Cree una página TOC

Cree una nueva página para el TOC y agréguela al documento PDF usando el siguiente código:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Paso 3: agregue la sección de lista a la colección de secciones del documento PDF

Agregue la sección de lista a la colección de secciones del documento PDF usando el siguiente código:

```csharp
tocPage.TocInfo = tocInfo;
```

## Paso 4: Definir el formato de la lista de cuatro niveles

Defina el formato de la lista de cuatro niveles configurando los márgenes izquierdos y la configuración de formato de texto de cada nivel usando el siguiente código:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Paso 5: agregue cuatro encabezados en la sección

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Ejemplo de código fuente para ocultar números de página en TOC usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Agregue la sección de lista a la colección de secciones del documento PDF
tocPage.TocInfo = tocInfo;
//Defina el formato de la lista de cuatro niveles configurando los márgenes izquierdos y
//configuración de formato de texto de cada nivel

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Agregue cuatro encabezados en la sección
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Conclusión

En este tutorial, exploramos cómo trabajar con metadatos XMP en un documento PDF usando Aspose.PDF para .NET. Los metadatos XMP proporcionan información valiosa sobre el documento PDF, incluido su título, autor, fecha de creación y más. Aspose.PDF para .NET permite a los desarrolladores acceder y manipular estos metadatos, proporcionando una API flexible y potente para trabajar con documentos PDF.

### Preguntas frecuentes

#### P: ¿Qué son los metadatos XMP en un documento PDF?

R: Los metadatos XMP (Plataforma de metadatos extensibles) en un documento PDF son un formato estándar para almacenar información de metadatos sobre el documento. Incluye detalles como el título del documento, el autor, la fecha de creación, las palabras clave y más. Los metadatos XMP proporcionan una forma estructurada y estandarizada de almacenar y compartir información sobre el documento PDF.

#### P: ¿Puedo modificar los metadatos XMP de un documento PDF usando Aspose.PDF para .NET?

 R: Sí, puede modificar los metadatos XMP de un documento PDF mediante programación usando Aspose.PDF para .NET. Puedes acceder a la`Info` propiedad de la`Document` objeto, que le da acceso a las propiedades de metadatos XMP. Luego puede actualizar los valores de estas propiedades para modificar los metadatos XMP del documento PDF.

#### P: ¿Puedo extraer propiedades de metadatos XMP personalizadas de un documento PDF usando Aspose.PDF para .NET?

 R: Sí, puede extraer propiedades de metadatos XMP personalizadas de un documento PDF utilizando Aspose.PDF para .NET. Puedes usar el`Metadata` propiedad de la`Document`objeto, que proporciona acceso a todas las propiedades de metadatos XMP del documento PDF. A continuación, puede extraer propiedades personalizadas y utilizar sus valores según sea necesario.