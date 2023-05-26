---
title: Agregar archivo SWF como anotación
linktitle: Agregar archivo SWF como anotación
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar archivos SWF como anotaciones en Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 30
url: /es/net/annotations/addswffileasannotation/
---
Si es un desarrollador de .NET que busca agregar un archivo multimedia SWF como una anotación a su documento PDF usando Aspose.PDF para .NET, esta guía paso a paso es para usted. En este artículo, explicaremos cómo agregar archivos SWF como anotaciones en sus documentos PDF usando el lenguaje de programación C#. 

Siga los pasos a continuación para agregar un archivo SWF como una anotación en su documento PDF usando Aspose.PDF para .NET:

## Paso 1: establecer la ruta del directorio

Primero, debemos establecer la ruta del directorio donde se almacenan el archivo PDF y el archivo SWF. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta a su directorio de documentos.

## Paso 2: Cargue el documento PDF

A continuación, necesitamos cargar el documento PDF usando el siguiente código:

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

Este código cargará el archivo "AddSwfFileAsAnnotation.pdf" del directorio del documento.

## Paso 3: Obtener la página para agregar anotaciones

Ahora, necesitamos obtener la referencia de la página a la que queremos agregar la anotación. En este tutorial, agregaremos la anotación a la primera página del documento.

```csharp
Page page = doc.Pages[1];
```

## Paso 4: Cree un objeto ScreenAnnotation

 Ahora podemos crear un`ScreenAnnotation` objeto con el archivo SWF como argumento.

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

 El`ScreenAnnotation` constructor toma tres argumentos:

- `page`: La página a la que se agregará la anotación.
- `rectangle`: el rectángulo en el que se mostrará el archivo SWF en la página.
- `dataDir + "input.swf"`: la ruta al archivo SWF.

## Paso 5: Agrega la anotación a la página

Ahora, podemos agregar la anotación a la colección de anotaciones de la página.

```csharp
page.Annotations.Add(annotation);
```

## Paso 6: Guarde el documento PDF actualizado

Finalmente, necesitamos guardar el documento PDF actualizado con la anotación usando el siguiente código:

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

Este código guardará el documento PDF actualizado con la anotación "AddSwfFileAsAnnotation_out.pdf" en el directorio del documento.

### Ejemplo de código fuente para agregar un archivo SWF como una anotación usando Aspose.PDF para .NET

```csharp
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Abre el documento PDF
	Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

	// Obtenga la referencia de la página a la que necesita agregar la anotación
	Page page = doc.Pages[1];

	// Cree un objeto ScreenAnnotation con un archivo multimedia .swf como argumento
	ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

	// Agregar la anotación a la colección de anotaciones de la página
	page.Annotations.Add(annotation);

	dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
	// Guarde el documento PDF de actualización con anotación
	doc.Save(dataDir);
```        
