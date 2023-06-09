---
title: Extraer enlaces
linktitle: Extraer enlaces
second_title: Referencia de API de Aspose.PDF para .NET
description: Extraiga fácilmente enlaces de un documento PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-links-and-actions/extract-links/
---

La extracción de enlaces de un documento PDF le permite recuperar todos los enlaces de hipertexto presentes en el documento. Con Aspose.PDF para .NET, puede extraer fácilmente estos enlaces siguiendo el siguiente código fuente:

## Paso 1: Importar bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta que contiene el archivo PDF del que desea extraer los enlaces. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Abra el documento PDF

 Abriremos el documento PDF usando el`Document` clase. Aquí está el código correspondiente:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Paso 4: Extraer enlaces

 En este paso, extraeremos los enlaces presentes en el documento PDF usando el`AnnotationSelector` clase. Aquí está el código correspondiente:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Paso 5: Guarde el documento actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`document` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Ejemplo de código fuente para Extraer enlaces usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Extraer acciones
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Guardar documento actualizado
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para extraer enlaces de un documento PDF utilizando Aspose.PDF para .NET. Puede usar este código para recuperar todos los hipervínculos presentes en el documento.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de extracción de enlaces.