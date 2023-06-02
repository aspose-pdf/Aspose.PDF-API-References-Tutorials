---
title: Establecer imagen como fondo
linktitle: Establecer imagen como fondo
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para configurar una imagen como fondo de página en un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-pdf-pages/image-as-background/
---
En este tutorial, lo guiaremos a través del proceso paso a paso para establecer una imagen como fondo de página usando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo agregar una imagen como fondo de página en un documento PDF utilizando Aspose.PDF para .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento PDF editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear un nuevo documento
 Luego puede crear un nuevo objeto Documento usando el`Document` clase.

```csharp
Document doc = new Document();
```

## Paso 3: Agregar una nueva página al documento
 Ahora puede agregar una nueva página al objeto Documento usando el`Add()` metodo de la`Pages` clase.

```csharp
Page page = doc.Pages.Add();
```

## Paso 4: Cree un objeto Artefacto de fondo
Luego puede crear un nuevo objeto BackgroundArtifact para establecer la imagen de fondo.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Paso 5: Agrega el fondo a la página
 Luego puede agregar el objeto BackgroundArtifact a la colección de artefactos de la página usando el`Artifacts` propiedad de la`Page` clase.

```csharp
page. Artifacts. Add(background);
```

## Paso 6: Guarde el documento PDF
 Finalmente, puede guardar el documento PDF en un archivo usando el`Save()` metodo de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Ejemplo de código fuente para Imagen como fondo usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear un nuevo objeto Documento
Document doc = new Document();
// Agregar una nueva página al objeto del documento
Page page = doc.Pages.Add();
// Crear objeto de artefacto de fondo
BackgroundArtifact background = new BackgroundArtifact();
// Especifique la imagen para el objeto backgroundartefact
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Agregar backgroundartifact a la colección de artefactos de la página
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Guardar el documento
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Conclusión
En este tutorial, aprendimos cómo configurar una imagen como fondo de página en un documento PDF utilizando Aspose.PDF para .NET. Siguiendo esta guía paso a paso, puede agregar fácilmente una imagen de fondo a sus documentos PDF. Aspose.PDF ofrece una API potente y flexible para trabajar con archivos PDF, incluida la personalización del fondo de página. Ahora puede aplicar esta función en sus propios proyectos para crear documentos PDF con imágenes de fondo personalizadas
