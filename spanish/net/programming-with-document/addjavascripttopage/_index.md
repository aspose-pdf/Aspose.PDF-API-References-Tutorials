---
title: Agregar Java Script a la página
linktitle: Agregar Java Script a la página
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar JavaScript a archivos PDF usando Aspose.PDF para .NET. Guía paso a paso con tutoriales de código para secuencias de comandos a nivel de documentos y páginas.
type: docs
weight: 10
url: /es/net/programming-with-document/addjavascripttopage/
---

Para agregar JavaScript a un archivo PDF, usaremos Aspose.PDF para .NET. Esta biblioteca proporciona una manera simple y eficiente de trabajar con archivos PDF en aplicaciones .NET. Los siguientes pasos lo guiarán a través del proceso de agregar JavaScript a un archivo PDF usando Aspose.PDF para .NET.

## Paso 1: Cargue el archivo PDF

 El primer paso es cargar el archivo PDF al que desea agregar JavaScript. Puedes hacer esto usando el`Document` clase proporcionada por Aspose.PDF para .NET. El`Document` La clase proporciona métodos para cargar, guardar y manipular archivos PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargue un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 2: agregue JavaScript a nivel de documento

 Para agregar JavaScript a nivel de documento, usaremos el`JavascriptAction` clase proporcionada por Aspose.PDF para .NET. Esta clase le permite especificar la declaración de JavaScript que desea agregar al archivo PDF.

```csharp
// Agregar JavaScript a nivel de documento
// Crear una instancia de JavascriptAction con la declaración de JavaScript deseada
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Asigne el objeto JavascriptAction a la acción deseada del documento
doc.OpenAction = javaScript;
```

En este tutorial, estamos agregando una declaración de JavaScript que imprimirá el archivo PDF con las opciones especificadas cuando se abra el documento.

## Paso 3: agregue JavaScript a nivel de página

 Para agregar JavaScript a nivel de página, usaremos el`JavascriptAction` clase y el`Actions`propiedad proporcionada por Aspose.PDF para .NET. Esta propiedad le permite especificar declaraciones de JavaScript que se ejecutarán cuando se abra o cierre la página.

```csharp
// Agregar JavaScript a nivel de página
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

En este tutorial, estamos agregando declaraciones de JavaScript que mostrarán un mensaje de alerta cuando la página se abra o se cierre.

## Paso 4: Guarde el archivo PDF

 Después de haber agregado JavaScript al archivo PDF, debe guardar el archivo modificado. Puedes hacer esto usando el`Save` método proporcionado por el`Document` clase.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Este código guardará el archivo PDF modificado en el directorio especificado.

### Ejemplo de código fuente para agregar Java Script a la página usando Aspose.PDF para .NET

```csharp
            
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargue un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");

// Agregar JavaScript a nivel de documento
// Crear una instancia de JavascriptAction con la declaración de JavaScript deseada
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Asigne el objeto JavascriptAction a la acción deseada del documento
doc.OpenAction = javaScript;

// Agregar JavaScript a nivel de página
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Conclusión

En este artículo, hemos explicado cómo agregar JavaScript a un archivo PDF tanto a nivel de documento como a nivel de página usando Aspose.PDF para .NET. Hemos proporcionado instrucciones paso a paso e incluido el código fuente completo para cada ejemplo. Con este conocimiento, puede agregar JavaScript a sus archivos PDF y personalizar su comportamiento según sus necesidades.


