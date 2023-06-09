---
title: Contenido PDF etiquetado
linktitle: Contenido PDF etiquetado
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a trabajar con contenido etiquetado en un documento PDF con Aspose.PDF para .NET. Una guía paso a paso para usar etiquetas.
type: docs
weight: 200
url: /es/net/programming-with-tagged-pdf/tagged-pdf-content/
---
En este tutorial detallado, lo guiaremos a través del código fuente de C# proporcionado paso a paso para trabajar con contenido marcado de un documento PDF usando Aspose.PDF para .NET. Siga las instrucciones a continuación para entender cómo usar la etiqueta para contenido PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo para usar Aspose.PDF para .NET. Esto incluye instalar la biblioteca Aspose.PDF y configurar su proyecto para hacer referencia a él.

## Paso 2: Crear el documento PDF

En este paso, crearemos un nuevo objeto de documento PDF con Aspose.PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear el documento PDF
Document document = new Document();
```

Hemos creado un nuevo documento PDF con Aspose.PDF.

## Paso 3: Obtener contenido para trabajar con el PDF etiquetado

En este paso, conseguiremos que el contenido del documento PDF funcione con el PDF etiquetado.

```csharp
// Obtenga el contenido para trabajar con el PDF etiquetado
ITaggedContent taggedContent = document.TaggedContent;
```

Conseguimos que el contenido del documento PDF funcione con el PDF etiquetado.

## Paso 4: Trabaje con contenido etiquetado en PDF

Ahora trabajaremos con el contenido etiquetado del PDF usando las etiquetas apropiadas.

```csharp
// Trabajar con el contenido etiquetado del PDF
taggedContent.SetTitle("Simple tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Hemos establecido el título y el idioma del documento PDF etiquetado.

## Paso 5: Guardar el documento PDF etiquetado

Ahora que hemos trabajado con el contenido etiquetado del documento PDF, guardémoslo como un documento PDF etiquetado.

```csharp
// Guarde el documento PDF etiquetado
document.Save(dataDir + "ContentPDFTag.pdf");
```

Guardamos el documento PDF etiquetado en el directorio especificado.

### Ejemplo de código fuente para PDFContent etiquetado usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear Documento PDF
Document document = new Document();

// Obtenga contenido para trabajar con TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Trabajar con contenido PDF etiquetado
// Establecer título e idioma para Documnet
taggedContent.SetTitle("Simple Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Guardar documento PDF etiquetado
document.Save(dataDir + "TaggedPDFContent.pdf");

```
## Conclusión

En este tutorial, aprendimos a trabajar con contenido marcado en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede usar Aspose.PDF para crear documentos PDF con contenido etiquetado adecuado.
