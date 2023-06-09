---
title: Agregar hipervínculo
linktitle: Agregar hipervínculo
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente hipervínculos interactivos en sus archivos PDF con Aspose.PDF para .NET.
type: docs
weight: 10
url: /es/net/programming-with-links-and-actions/add-hyperlink/
---

Agregar hipervínculos en un documento PDF le permite crear hipervínculos interactivos a otras páginas, sitios web o destinos en el documento. Con Aspose.PDF para .NET, puede agregar fácilmente hipervínculos siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un hipervínculo. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora abriremos el documento PDF al que queremos añadir un hipervínculo utilizando el siguiente código:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## Paso 4: Crea un enlace

 En este paso, crearemos un hipervínculo usando el`LinkAnnotation` anotación. Especificaremos los datos de contacto y el área del enlace, el tipo de enlace y el contenido del enlace. Aquí está el código correspondiente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## Paso 5: Agrega texto adicional

 Además del hipervínculo, también podemos agregar texto adicional usando el`FreeTextAnnotation` anotación. Especificaremos las coordenadas, la apariencia del texto y el contenido del texto. Aquí está el código correspondiente:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## Paso 6: Guarde el archivo actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`document` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Ejemplo de código fuente para Agregar hipervínculo usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Crear enlace
Page page = document.Pages[1];
//Crear objeto de anotación de enlace
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Crear objeto de borde para LinkAnnotation
Border border = new Border(link);
// Establezca el valor del ancho del borde en 0
border.Width = 0;
// Establecer el borde para LinkAnnotation
link.Border = border;
// Especifique el tipo de enlace como URI remoto
link.Action = new GoToURIAction("www.aspose.com");
// Agregar anotación de enlace a la colección de anotaciones de la primera página del archivo PDF
page.Annotations.Add(link);
// Crear anotación de texto libre
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// Cadena que se agregará como texto libre
textAnnotation.Contents = "Link to Aspose website";
// Establecer el borde para la anotación de texto libre
textAnnotation.Border = border;
// Agregar anotación de texto libre a la colección de anotaciones de la primera página del documento
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Guardar documento actualizado
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para agregar hipervínculos con Aspose.PDF para .NET. Puede usar este código para crear enlaces interactivos en sus documentos PDF.