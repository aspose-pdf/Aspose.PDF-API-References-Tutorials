---
title: Crear hipervínculo local
linktitle: Crear hipervínculo local
second_title: Referencia de API de Aspose.PDF para .NET
description: Cree fácilmente hipervínculos locales en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-links-and-actions/create-local-hyperlink/
---

La creación de hipervínculos locales en un archivo PDF le permite crear vínculos en los que se puede hacer clic que llevan a los usuarios a otras páginas en el mismo documento PDF. Con Aspose.PDF para .NET, puede crear fácilmente dichos enlaces siguiendo el siguiente código fuente:

## Paso 1: Importar bibliotecas requeridas

Antes de comenzar, debe importar las bibliotecas necesarias para su proyecto de C#. Aquí está la directiva de importación necesaria:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Paso 2: establecer la ruta a la carpeta de documentos

 En este paso, debe especificar la ruta a la carpeta donde desea guardar el archivo PDF resultante. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el siguiente código con la ruta real a su carpeta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 3: Crear una instancia de Documento

 Vamos a crear una instancia de la`Document` class para representar nuestro documento PDF. Aquí está el código correspondiente:

```csharp
Document doc = new Document();
```

## Paso 4: Agregar página y texto con hipervínculos

En este paso, agregaremos una página a nuestro documento PDF y agregaremos texto que contenga hipervínculos locales. Definiremos las páginas de destino para cada enlace. Aquí está el código correspondiente:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Paso 5: Guarde el documento actualizado

Ahora guardemos el archivo PDF actualizado usando el`Save` metodo de la`doc` objeto. Aquí está el código correspondiente:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para crear un hipervínculo local con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas del archivo PDF
Page page = doc.Pages.Add();
// Crear instancia de fragmento de texto
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Crear una instancia de hipervínculo local
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Establecer página de destino para instancia de enlace
link.TargetPageNumber = 7;
// Establecer hipervínculo TextFragment
text.Hyperlink = link;
// Agregar texto a la colección de párrafos de la página
page.Paragraphs.Add(text);
// Crear nueva instancia de TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment debe agregarse sobre la nueva página
text.IsInNewPage = true;
// Crear otra instancia de hipervínculo local
link = new LocalHyperlink();
// Establecer página de destino para el segundo hipervínculo
link.TargetPageNumber = 1;
// Establecer enlace para el segundo TextFragment
text.Hyperlink = link;
// Agregar texto a la colección de párrafos del objeto de página
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Guardar documento actualizado
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusión

¡Felicidades! Ahora tiene una guía paso a paso para crear hipervínculos locales en un PDF usando Aspose.PDF para .NET. Puede usar este código para crear enlaces en los que se puede hacer clic que lleven a los usuarios a otras páginas en el mismo documento.

Asegúrese de consultar la documentación oficial de Aspose.PDF para obtener más información sobre las funciones avanzadas de hipervínculos.