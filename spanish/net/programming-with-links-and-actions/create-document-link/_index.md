---
title: Crear enlace de documento
linktitle: Crear enlace de documento
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente enlaces a otros documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-links-and-actions/create-document-link/
---

Vincular a otro documento en un archivo PDF le permite crear vínculos en los que se puede hacer clic que redirigen a los usuarios a otros documentos PDF. Con Aspose.PDF para .NET, puede crear fácilmente dichos enlaces siguiendo el siguiente código fuente:

## Paso 1: importa las bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF al que desea agregar un enlace a otro documento. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

Ahora abriremos el documento PDF al que queremos añadir el enlace a otro documento utilizando el siguiente código:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Paso 4: Crea el enlace a otro documento

 En este paso, crearemos el enlace a otro documento usando el`LinkAnnotation` anotación. Especificaremos las coordenadas y área del enlace, así como la acción de navegación a un documento externo. Aquí está el código correspondiente:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Paso 5: Guarde el archivo actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`document` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Ejemplo de código fuente para Crear enlace de documento usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Crear enlace
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Guardar documento actualizado
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para vincular a otros documentos con Aspose.PDF para .NET. Puede usar este código para crear enlaces en los que se puede hacer clic en sus archivos PDF, redirigiendo a los usuarios a otros documentos.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de los enlaces interactivos.