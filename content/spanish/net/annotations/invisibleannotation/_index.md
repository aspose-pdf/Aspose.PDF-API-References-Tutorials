---
title: Anotación invisible en archivo PDF
linktitle: Anotación invisible en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a realizar anotaciones invisibles en archivos PDF utilizando el código fuente C# con Aspose.PDF para .NET. Guía paso por paso.
type: docs
weight: 100
url: /es/net/annotations/invisibleannotation/
---
Las anotaciones en un archivo PDF son una característica poderosa que le permite agregar información o notas adicionales a un documento sin cambiar el contenido real. Se pueden utilizar para resaltar texto, llamar la atención sobre áreas específicas de un documento o agregar comentarios o opiniones.

Hay muchos tipos diferentes de anotaciones que puede utilizar en documentos PDF, entre ellos:

- Anotaciones de texto
- Anotaciones de enlaces
- Anotaciones de sello
- Anotaciones de sonido
- Anotaciones de archivos adjuntos
- y muchos más

## Paso 1: Crear una anotación invisible en un documento PDF usando Aspose.PDF para .NET

 Para crear una anotación invisible en un documento PDF usando Aspose.PDF para .NET, primero debemos crear una`FreeTextAnnotation` objeto y especifique la ubicación y el tamaño de la anotación.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 En el código anterior, creamos un`FreeTextAnnotation`objeto y especifique la ubicación de la anotación en la página 2 del documento PDF. También especificamos el tipo, tamaño y color de fuente del texto que se mostrará en la anotación.

## Paso 2: agregar características a la anotación invisible

A continuación, podemos agregar algunas características a la anotación, como color de borde, color de fondo u opacidad.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

En el código anterior, configuramos el color del borde de la anotación en rojo.

## Paso 3: configurar los indicadores de anotación

Una vez que hayamos creado la anotación y establecido sus características, podemos especificar los indicadores de anotación. En este tutorial, queremos que la anotación sea imprimible, pero no visible.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Paso 4: guardar el documento PDF modificado

Finalmente, podremos guardar el documento PDF modificado con la nueva anotación invisible.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Código fuente de ejemplo sobre cómo realizar anotaciones invisibles utilizando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Guardar archivo de salida
doc.Save(dataDir);
// ExEnd: Anotación invisible
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo crear una anotación invisible en un documento PDF usando Aspose.PDF para .NET. Las anotaciones invisibles son una característica útil cuando desea agregar información o notas adicionales a un documento sin mostrárselas al lector. Siguiendo la guía paso a paso y utilizando el código fuente C# proporcionado, los desarrolladores pueden crear y personalizar fácilmente anotaciones invisibles en sus documentos PDF. Aspose.PDF para .NET proporciona un conjunto completo de herramientas para trabajar con anotaciones, lo que le permite mejorar la interactividad y usabilidad de sus archivos PDF.

### Preguntas frecuentes

#### P: ¿Qué es una anotación invisible en un documento PDF?

R: Una anotación invisible en un documento PDF es una anotación que no es visible en la página pero que contiene información o notas adicionales. Le permite agregar comentarios o opiniones sin mostrárselos al lector.

#### P: ¿Qué tipos de características se pueden agregar a una anotación invisible?

R: Se pueden agregar varias características a una anotación invisible, como color de borde, color de fondo, opacidad, tipo de fuente, tamaño y color del texto que se mostrará.

#### P: ¿Puedo configurar diferentes indicadores de anotación para una anotación invisible?

R: Sí, puede configurar diferentes indicadores de anotación para una anotación invisible, según sus requisitos. Por ejemplo, puede hacer que la anotación sea imprimible pero no visible.

#### P: ¿Cómo puedo agregar una anotación invisible a una página específica del documento PDF?

 R: Para agregar una anotación invisible a una página específica del documento PDF, necesita crear una`FreeTextAnnotation` objeto y especifique la ubicación y el tamaño de la anotación en esa página.

#### P: ¿Puedo modificar las características de una anotación invisible existente en un archivo PDF?

R: Sí, puede modificar las características de una anotación invisible existente en un archivo PDF usando Aspose.PDF para .NET. Puede cambiar el tipo de fuente, el tamaño, el color, el color del borde, el color de fondo, la opacidad y otras propiedades de la anotación.