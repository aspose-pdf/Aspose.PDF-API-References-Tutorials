---
title: Agregar anotación
linktitle: Agregar anotación
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar anotaciones de texto con Aspose.PDF para .NET usando este código fuente de C#. Personaliza tus anotaciones con detalles e íconos específicos.
type: docs
weight: 10
url: /es/net/annotations/addannotation/
---

Agregar anotaciones a documentos PDF es una característica poderosa que puede mejorar los procesos de colaboración y revisión. Aspose.PDF para .NET facilita la adición de anotaciones mediante programación a documentos PDF mediante C#. En esta guía, explicaremos paso a paso cómo usar Aspose.PDF para .NET para agregar anotaciones a un documento PDF.

## Paso 1: cree un nuevo proyecto e instale Aspose.PDF para .NET

Antes de comenzar a escribir el código para agregar anotaciones, debemos crear un nuevo proyecto e instalar Aspose.PDF para .NET. Para instalar Aspose.PDF para .NET, siga estos pasos:

1. Abra Visual Studio y cree un nuevo proyecto de C#.
2. Haga clic con el botón derecho en el proyecto en el Explorador de soluciones y seleccione "Administrar paquetes NuGet".
3. Busque "Aspose.PDF" y seleccione "Instalar".

Una vez finalizada la instalación, podemos empezar a escribir el código.

## Paso 2: Abra el documento PDF

El primer paso para agregar anotaciones es abrir el documento PDF. Podemos usar el siguiente código para abrir el documento:

```
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

En este código, especificamos la ruta al documento PDF que queremos abrir. Asegúrese de reemplazar "SU DIRECTORIO DE DATOS" con la ruta real a su directorio de datos.

## Paso 3: crea la anotación

 Para agregar una anotación, necesitamos crear una nueva instancia de la`TextAnnotation` clase. Podemos usar el siguiente código para crear una nueva anotación de texto:

```
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

En este código, creamos una nueva anotación de texto en la segunda página del documento PDF. También establecemos las propiedades de título, asunto, estado, contenido, apertura e icono de la anotación.

## Paso 4: personaliza la anotación

 Podemos personalizar la apariencia de la anotación usando el`Border` clase. Podemos usar el siguiente código para personalizar el borde de la anotación:

```
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 En este código, creamos un nuevo`Border` objeto y establezca sus propiedades de ancho y guión. Luego configuramos el`Border`propiedad de la anotación a la nueva`Border` objeto. Finalmente, configuramos el`Rect` propiedad de la anotación para especificar su posición y tamaño.

## Paso 5: agregue la anotación al documento PDF

Una vez que hayamos creado y personalizado la anotación, debemos agregarla al documento PDF. Podemos usar el siguiente código para agregar la anotación al documento PDF:

```
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

En este código, agregamos la anotación a la colección de anotaciones de la segunda página del documento PDF.

## Paso 6: Guarde el archivo de salida

Finalmente, debemos guardar el documento PDF con la anotación agregada. Podemos usar el siguiente código para guardar el archivo de salida:

```
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Ejemplo de código fuente para agregar anotaciones usando Aspose.PDF para .NET


```csharp   
	 // La ruta al directorio de documentos.
	string dataDir = "YOUR DATA DIRECTORY";

	// Abrir documento
	Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

	// Crear anotación
	TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
	textAnnotation.Title = "Sample Annotation Title";
	textAnnotation.Subject = "Sample Subject";
	textAnnotation.State = AnnotationState.Accepted;
	textAnnotation.Contents = "Sample contents for the annotation";
	textAnnotation.Open = true;
	textAnnotation.Icon = TextIcon.Key;
   
	Border border = new Border(textAnnotation);
	border.Width = 5;
	border.Dash = new Dash(1, 1);
	textAnnotation.Border = border;
	textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
   
	// Agregar anotación en la colección de anotaciones de la página
	pdfDocument.Pages[1].Annotations.Add(textAnnotation);
	dataDir = dataDir + "AddAnnotation_out.pdf";
	// Guardar archivo de salida
	pdfDocument.Save(dataDir);
```
Este código demuestra cómo agregar una anotación de texto con un título, asunto, estado, contenido e ícono específicos a una página PDF usando Aspose.PDF para .NET. Puede modificar este código según sus requisitos para agregar anotaciones a sus documentos PDF. Solo recuerde reemplazar SU DIRECTORIO DE DATOS con la ruta del directorio real donde se encuentra su archivo PDF y donde desea guardar el archivo de salida.