---
title: Anotación invisible
linktitle: Anotación invisible
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a anotar archivos PDF de forma invisible utilizando el código fuente de C# con Aspose.PDF para .NET. Guía paso por paso.
type: docs
weight: 100
url: /es/net/annotations/invisibleannotation/
---

Las anotaciones en documentos PDF son una característica poderosa que le permite agregar información adicional o notas a un documento sin cambiar el contenido real. Se pueden usar para resaltar texto, llamar la atención sobre áreas específicas de un documento o agregar comentarios o comentarios.

Hay muchos tipos diferentes de anotaciones que puede usar en documentos PDF, que incluyen:

- Anotaciones de texto
- Anotaciones de enlaces
- Anotaciones de sellos
- Anotaciones de sonido
- Anotaciones de archivos adjuntos
- y muchos más

## Paso 1: Crear una anotación invisible en un documento PDF usando Aspose.PDF para .NET

 Para crear una anotación invisible en un documento PDF utilizando Aspose.PDF para .NET, primero debemos crear un`FreeTextAnnotation` objeto y especifique la ubicación y el tamaño de la anotación.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Abrir documento
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 En el código anterior, creamos un`FreeTextAnnotation`objeto y especifique la ubicación de la anotación en la página 2 del documento PDF. También especificamos el tipo de fuente, el tamaño y el color del texto que se mostrará en la anotación.

## Paso 2: agregar características a la anotación invisible

A continuación, podemos agregar algunas características a la anotación, como un color de borde, color de fondo u opacidad.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

En el código anterior, establecemos el color del borde de la anotación en rojo.

## Paso 3: Configuración de los indicadores de anotación

Una vez que hayamos creado la anotación y establecido sus características, podemos especificar los indicadores de la anotación. En este tutorial, queremos que la anotación sea imprimible, pero no visible.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Paso 4: Guardar el documento PDF modificado

Finalmente, podemos guardar el documento PDF modificado con la nueva anotación invisible.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Ejemplo de código fuente de cómo hacer anotaciones invisibles usando Aspose.PDF para .NET

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
// ExEnd:AnotaciónInvisible
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```