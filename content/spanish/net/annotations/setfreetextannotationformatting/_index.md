---
title: Establecer formato de anotación de texto libre
linktitle: Establecer formato de anotación de texto libre
second_title: Aspose.PDF para referencia de API .NET
description: Este artículo proporciona una guía paso a paso sobre cómo crear una anotación de texto libre y especificar su contenido usando Aspose.PDF para .NET.
type: docs
weight: 140
url: /es/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF para .NET es una API de manipulación de documentos PDF potente y fácil de usar que le permite trabajar con archivos PDF mediante programación en sus aplicaciones .NET. Una de las características proporcionadas por Aspose.PDF para .NET es la capacidad de configurar el formato de anotación de texto libre en documentos PDF. En este artículo, lo guiaremos a través del proceso paso a paso para configurar el formato de anotación de texto libre usando Aspose.PDF para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Microsoft Visual Studio 2010 o posterior
- Aspose.PDF para .NET
- Conocimientos básicos de C#.



## Paso 1: crear una nueva aplicación de consola C#

Primero, cree una nueva aplicación de consola C# en Microsoft Visual Studio. Para crear una nueva aplicación de consola, seleccione "Archivo" > "Nuevo" > "Proyecto" > "Visual C#" > "Aplicación de consola" en el menú principal.

## Paso 2: agregue una referencia a Aspose.PDF para .NET

A continuación, agregue una referencia a Aspose.PDF para .NET en su proyecto. Para hacer esto, haga clic derecho en su proyecto en el panel "Explorador de soluciones", seleccione "Agregar" > "Referencia" y luego busque la ubicación donde guardó el archivo DLL Aspose.PDF para .NET. Seleccione el archivo DLL y haga clic en "Aceptar" para agregar la referencia a su proyecto.

## Paso 3: configurar el entorno

Después de agregar la referencia a Aspose.PDF para .NET, debe configurar el entorno. Para hacer esto, cree una nueva variable de cadena llamada "dataDir" y configúrela en la ruta del directorio donde se encuentra su documento PDF. Reemplace "SU DIRECTORIO DE DOCUMENTOS" en el código siguiente con la ruta real de su directorio de documentos:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 4: abre el documento PDF

Una vez que haya configurado el entorno, puede abrir el documento PDF usando el siguiente código:

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Reemplace "SetFreeTextAnnotationFormatting.pdf" con el nombre real de su documento PDF.

## Paso 5: configurar la apariencia predeterminada

Para configurar la apariencia predeterminada de la anotación de texto libre, debe crear una instancia del objeto DefaultAppearance con la fuente, el tamaño de fuente y el color deseados. En este tutorial, configuraremos la fuente en "Arial", el tamaño de fuente en 28 y el color en rojo.

```csharp
// Crear una instancia del objeto DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## Paso 6: crea una anotación de texto libre

Ahora que ha configurado la apariencia predeterminada, puede crear una anotación de texto libre usando el siguiente código:

```csharp
// Crear anotación
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

El código anterior crea una nueva anotación de texto libre en la segunda página del documento PDF. La anotación se colocará en (200, 400) y tendrá un ancho de 400 y un alto de 600.

## Paso 7: especificar el contenido de la anotación

Después de crear la anotación de texto libre, puede especificar el contenido de la anotación usando el siguiente código:

```csharp
// Especificar el contenido de la anotación.
freetext.Contents = "Free Text
```

### Código fuente de ejemplo para establecer formato de anotación de texto libre usando Aspose.PDF para .NET
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Crear una instancia del objeto DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Crear anotación
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Especificar el contenido de la anotación.
freetext.Contents = "Free Text";
// Agregar anotación a la colección de anotaciones de la página
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Guardar el documento actualizado
pdfDocument.Save(dataDir);            
```

## Conclusión

En este tutorial, aprendimos cómo configurar el formato de anotación de texto libre en un documento PDF usando Aspose.PDF para .NET. La biblioteca proporciona una forma sencilla y eficiente de trabajar con documentos PDF mediante programación, lo que permite a los desarrolladores crear y personalizar varios tipos de anotaciones, incluidas anotaciones de texto libre. Si sigue la guía paso a paso y utiliza el código fuente C# proporcionado, puede configurar fácilmente el entorno, abrir un documento PDF y crear una anotación de texto libre con formato personalizado. Aspose.PDF para .NET es una API sólida y confiable que simplifica las tareas de manipulación de documentos PDF, lo que la convierte en una herramienta valiosa para los desarrolladores de .NET que trabajan con archivos PDF.

### Preguntas frecuentes

#### P: ¿Qué es una anotación de texto libre en un documento PDF?

R: Una anotación de texto libre en un documento PDF es un tipo de anotación que le permite agregar texto al documento sin estar vinculado a una ubicación o estructura específica. Se utiliza comúnmente para proporcionar comentarios, notas u otra información adicional en el documento.

#### P: ¿Puedo personalizar la apariencia de la anotación de texto libre usando Aspose.PDF para .NET?

R: Sí, puedes personalizar varias propiedades de la anotación de texto libre, como la fuente, el tamaño de la fuente, el color, la posición y más.

#### P: ¿Cómo especifico el contenido de la anotación de texto libre?

 R: Para especificar el contenido de la anotación de texto libre, puede configurar el`Contents` propiedad de la`FreeTextAnnotation` oponerse al texto deseado.

#### P: ¿Puedo agregar varias anotaciones de texto libre a un documento PDF usando Aspose.PDF para .NET?

 R: Sí, puede crear varias anotaciones de texto libre en un documento PDF creando varias instancias del`FreeTextAnnotation`objeto y agregarlos a diferentes páginas o ubicaciones en el documento.