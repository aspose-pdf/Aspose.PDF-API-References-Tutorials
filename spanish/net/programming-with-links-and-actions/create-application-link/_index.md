---
title: Crear enlace de aplicación
linktitle: Crear enlace de aplicación
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente enlaces de aplicaciones en sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 20
url: /es/net/programming-with-links-and-actions/create-application-link/
---

La creación de un enlace de aplicación en un documento PDF le permite crear enlaces a aplicaciones externas, como archivos ejecutables o URL. Con Aspose.PDF para .NET, puede crear fácilmente enlaces de aplicaciones siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establecer la ruta a la carpeta de documentos

En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un enlace de aplicación. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora abriremos el documento PDF al que queremos añadir un enlace de aplicación utilizando el siguiente código:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Paso 4: Cree el enlace de la aplicación

 En este paso, crearemos el enlace de la aplicación usando el`LinkAnnotation` anotación. Especificaremos las coordenadas y el área del enlace, así como la acción de lanzamiento de la aplicación. Aquí está el código correspondiente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Paso 5: Guarde el archivo actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`document` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Ejemplo de código fuente para Crear enlace de aplicación usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Crear enlace
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Guardar documento actualizado
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para crear enlaces de aplicaciones con Aspose.PDF para .NET. Puede usar este código para agregar enlaces a aplicaciones externas en sus documentos PDF.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de los enlaces interactivos.