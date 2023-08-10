---
title: Eliminar todo el texto
linktitle: Eliminar todo el texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar todo el texto de un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 280
url: /es/net/programming-with-text/remove-all-text/
---

En este tutorial, explicaremos cómo eliminar todo el texto de un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Pasaremos por el proceso paso a paso de abrir un PDF, seleccionar y eliminar texto de cada página y guardar el PDF modificado usando el código fuente de C# provisto.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde se encuentran sus archivos PDF. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a sus archivos PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 A continuación, abrimos el documento PDF usando el`Document` clase de la biblioteca Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Paso 3: eliminar texto de cada página

 Recorremos todas las páginas del documento PDF y usamos un`OperatorSelector` para seleccionar todo el texto de cada página. Luego, borramos el texto seleccionado.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## Paso 4: Guarde el PDF modificado

Finalmente, guardamos el documento PDF modificado en el archivo de salida especificado.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Ejemplo de código fuente para Quitar todo el texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Recorra todas las páginas del documento PDF
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Seleccionar todo el texto de la página
	page.Contents.Accept(operatorSelector);
	// Eliminar todo el texto
	page.Contents.Delete(operatorSelector.Selected);
}
// Guardar el documento
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusión

En este tutorial, ha aprendido a eliminar todo el texto de un documento PDF utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso y ejecutando el código C# proporcionado, puede abrir un PDF, seleccionar y eliminar texto de cada página y guardar el PDF modificado.