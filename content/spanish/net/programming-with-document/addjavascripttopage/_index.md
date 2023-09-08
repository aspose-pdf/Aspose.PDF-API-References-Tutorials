---
title: Agregar Java Script al archivo PDF
linktitle: Agregar archivo PDF de secuencia de comandos Java
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar JavaScript a un archivo PDF usando Aspose.PDF para .NET. Guía paso a paso con tutoriales de código para secuencias de comandos a nivel de documentos y páginas.
type: docs
weight: 10
url: /es/net/programming-with-document/addjavascripttopage/
---
Para agregar JavaScript a un archivo PDF, usaremos Aspose.PDF para .NET. Esta biblioteca proporciona una forma sencilla y eficaz de trabajar con archivos PDF en aplicaciones .NET. Los siguientes pasos lo guiarán a través del proceso de agregar JavaScript a un archivo PDF usando Aspose.PDF para .NET.

## Paso 1: cargue el archivo PDF

 El primer paso es cargar el archivo PDF al que desea agregar JavaScript. Puedes hacer esto usando el`Document` clase proporcionada por Aspose.PDF para .NET. El`Document` La clase proporciona métodos para cargar, guardar y manipular archivos PDF.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar archivos PDF existentes
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 2: agregue JavaScript a nivel de documento

Para agregar JavaScript a nivel de documento, usaremos el`JavascriptAction` clase proporcionada por Aspose.PDF para .NET. Esta clase le permite especificar la declaración de JavaScript que desea agregar al archivo PDF.

```csharp
// Agregar JavaScript a nivel de documento
// Cree una instancia de JavascriptAction con la declaración de JavaScript deseada
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Asigne el objeto JavascriptAction a la acción deseada del documento
doc.OpenAction = javaScript;
```

En este tutorial, agregaremos una declaración de JavaScript que imprimirá el archivo PDF con las opciones especificadas cuando se abra el documento.

## Paso 3: agregue JavaScript a nivel de página

 Para agregar JavaScript a nivel de página, usaremos el`JavascriptAction` clase y el`Actions` propiedad proporcionada por Aspose.PDF para .NET. Esta propiedad le permite especificar declaraciones de JavaScript que se ejecutarán cuando se abra o cierre la página.

```csharp
// Agregar JavaScript a nivel de página
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

En este tutorial, agregaremos declaraciones de JavaScript que mostrarán un mensaje de alerta cuando se abra o cierre la página.

## Paso 4: guarde el archivo PDF

Después de haber agregado JavaScript al archivo PDF, debe guardar el archivo modificado. Puedes hacer esto usando el`Save` método proporcionado por el`Document` clase.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Este código guardará el archivo PDF modificado en el directorio especificado.

### Código fuente de ejemplo para agregar Java Script a la página usando Aspose.PDF para .NET

```csharp
            
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar archivos PDF existentes
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

En este artículo, explicamos cómo agregar JavaScript a un archivo PDF tanto a nivel de documento como a nivel de página usando Aspose.PDF para .NET. Proporcionamos instrucciones paso a paso e incluimos el código fuente completo para cada ejemplo. Con este conocimiento, puede agregar JavaScript a sus archivos PDF y personalizar su comportamiento según sus necesidades.


### Preguntas frecuentes para agregar script java a un archivo PDF

#### P: ¿Qué es Aspose.PDF para .NET?

R: Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores trabajar con archivos PDF en aplicaciones .NET. Proporciona una amplia gama de funciones para crear, modificar y manipular documentos PDF.

#### P: ¿Puedo agregar JavaScript a un documento PDF usando Aspose.PDF para .NET?

R: Sí, Aspose.PDF para .NET le permite agregar JavaScript tanto al nivel del documento como al nivel de la página de un archivo PDF, lo que le permite crear documentos PDF dinámicos e interactivos.

#### P: ¿Cómo cargo un archivo PDF existente usando Aspose.PDF para .NET?

 R: Puede cargar un archivo PDF existente usando el`Document` clase y sus métodos, como se muestra en la guía paso a paso.

#### P: ¿Qué tipos de acciones de JavaScript puedo agregar a un documento PDF?

R: Con Aspose.PDF para .NET, puede agregar una amplia variedad de acciones de JavaScript, como impresión, mensajes de alerta, manipulación de campos de formulario y más.

#### P: ¿Aspose.PDF para .NET es adecuado para proyectos comerciales?

R: Sí, Aspose.PDF para .NET es una biblioteca confiable y sólida que se usa comúnmente en proyectos comerciales para tareas de generación y manipulación de PDF.

