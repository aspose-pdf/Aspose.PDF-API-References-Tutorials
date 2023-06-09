---
title: Configurar idioma y título
linktitle: Configurar idioma y título
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para configurar el idioma y el título de un documento PDF con Aspose.PDF para .NET. Cree documentos multilingües personalizados.
type: docs
weight: 140
url: /es/net/programming-with-tagged-pdf/setup-language-and-title/
---
En esta guía, le diremos cómo configurar el idioma y el título de un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Aspose.PDF es una poderosa biblioteca que le permite crear, manipular y convertir archivos PDF mediante programación.

Profundicemos en el código y aprendamos cómo configurar el idioma y el título de un documento PDF usando Aspose.PDF para .NET.

## requisitos previos

Antes de comenzar, asegúrese de haber instalado Aspose.PDF para .NET y configurar su entorno de desarrollo.

## Paso 1: Crear el documento

 El primer paso es crear un nuevo documento PDF usando el`Document` clase.

```csharp
// Crear el documento PDF
Document document = new Document();
```

## Paso 2: accede al contenido etiquetado

 A continuación, accedemos al contenido etiquetado del documento mediante el`ITaggedContent` objeto.

```csharp
//Accede al contenido etiquetado
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## Paso 3: Establecer título e idioma

 Ahora podemos configurar el título del documento y el idioma usando el`SetTitle` y`SetLanguage` métodos de la`ITaggedContent` objeto.

```csharp
// Definir el título del documento.
taggedContent.SetTitle("Example of tagged document");

// Establecer el idioma del documento
taggedContent.SetLanguage("fr-FR");
```

## Paso 4: Agrega contenido multilingüe

A continuación, agregamos contenido multilingüe al documento utilizando elementos de párrafo para cada idioma.

```csharp
// Agregar un párrafo en inglés
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Agregar un párrafo en alemán
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Agregar un párrafo en francés
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Agregar un párrafo en español
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## Paso 5: Guarde el documento PDF etiquetado

Finalmente, guardamos el documento PDF etiquetado.

```csharp
// Guarde el documento PDF etiquetado
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Ejemplo de código fuente para configurar el idioma y el título usando Aspose.PDF para .NET 
```csharp

Document document = new Document();

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Obtener contenido etiquetado
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Establecer título e idioma
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// Encabezado (en-US, heredado del documento)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Párrafo (inglés)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Párrafo (alemán)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Párrafo (francés)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Párrafo (Español)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Guardar documento PDF etiquetado
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Conclusión

¡Felicidades! Ahora sabe cómo configurar el idioma y el título de un documento PDF utilizando Aspose.PDF para .NET. Puede explorar más a fondo las características de Aspose.PDF para crear documentos PDF personalizados y multilingües.
