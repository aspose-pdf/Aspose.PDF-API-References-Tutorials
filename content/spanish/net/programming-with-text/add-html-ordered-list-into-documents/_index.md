---
title: Agregar una lista ordenada HTML a los documentos
linktitle: Agregar lista HTMLOrdered a documentos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar una lista ordenada HTML a un documento usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-text/add-html-ordered-list-into-documents/
---
En este tutorial, aprenderá a utilizar la biblioteca Aspose.PDF para .NET para agregar una lista ordenada en HTML a un documento. El código proporcionado demuestra los pasos necesarios para realizar esta tarea.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea agregar la lista ordenada HTML, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: Establezca el directorio del documento y la ruta del archivo de salida
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

 A continuación, localice la línea que dice`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` y reemplazar`"AddHTMLOrderedListIntoDocuments_out.pdf"` con el nombre deseado para el archivo PDF de salida.

## Paso 4: Crear un nuevo objeto Documento
 Crear una nueva instancia`Document` objeto agregando la siguiente línea de código:

```csharp
Document doc = new Document();
```

## Paso 5: Crea un objeto HtmlFragment con el contenido HTML
 Crear una instancia`HtmlFragment` objeto con el contenido HTML que desea agregar al documento. En el código proporcionado, el contenido HTML se asigna a la variable`t`Puede modificar el contenido HTML según sea necesario.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Paso 6: Agregar una página al documento
 Agregue una nueva página al documento utilizando el`Add` método de la`Pages` colección. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Paso 7: Agrega el HtmlFragment a la página
 Añade el`HtmlFragment` objeto a la página mediante el uso de`Add` método de la`Paragraphs` recopilación.

```csharp
page.Paragraphs.Add(t);
```

## Paso 8: Guarde el documento PDF
 Guarde el archivo PDF resultante utilizando el`Save` método de la`Document` objeto. Especifique la ruta del archivo de salida que configuró en el paso 3.

```csharp
doc.Save(outFile);
```

### Código fuente de muestra para agregar una lista ordenada en HTML a documentos usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// La ruta al documento de salida.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Crear una instancia del objeto Documento
Document doc = new Document();
// Crear una instancia del objeto HtmlFragment con el fragmento HTML correspondiente
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Agregar página a la colección de páginas
Page page = doc.Pages.Add();
// Agregar HtmlFragment dentro de la página
page.Paragraphs.Add(t);
//Guardar el archivo PDF resultante
doc.Save(outFile);
```

## Conclusión
Ha añadido correctamente una lista ordenada en HTML a un documento mediante Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta de archivo de salida especificada.

Recuerde personalizar el contenido HTML y ajustar el código según sus requisitos específicos.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de este tutorial?

A: Este tutorial tiene como objetivo guiarlo a través del proceso de agregar una lista ordenada en HTML a un documento mediante la biblioteca Aspose.PDF para .NET. Proporciona instrucciones paso a paso y fragmentos de código para ayudarlo a realizar esta tarea.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: Debe importar los siguientes espacios de nombres en la parte superior de su archivo de código:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio del documento y la ruta del archivo de salida?

 A: En el código, localiza la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta actual al directorio de su documento. Además, busque la línea`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` y reemplazar`"AddHTMLOrderedListIntoDocuments_out.pdf"` con el nombre del archivo PDF de salida que desee.

#### P: ¿Puedo personalizar el contenido HTML que se agrega al documento?

 A: ¡Por supuesto! En el paso 5, crearás un`HtmlFragment` objeto nombrado`t` que contiene el contenido HTML. Puede modificar el contenido HTML dentro de las comillas invertidas para adaptarlo a sus necesidades.

#### P: ¿Cómo agrego la lista ordenada HTML a una página del documento?

 A: En el paso 7, agregarás el`HtmlFragment` objeto (`t` ) a la página usando el`Add` método de la`Paragraphs` Colección. Esto integrará perfectamente la lista ordenada HTML en el documento.

#### P: ¿Cómo guardo el documento PDF resultante?

 A: Después de agregar el contenido HTML y organizarlo en una página, puede guardar el documento PDF usando el`Save` método de la`Document` objeto. Asegúrese de proporcionar la ruta correcta del archivo de salida que configuró anteriormente.

#### P: ¿Puede proporcionarme un resumen del código fuente de muestra como referencia?

A: ¡Por supuesto! A continuación, se incluye una versión resumida del código fuente de muestra que se incluye en este tutorial:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, aprendió a aprovechar la biblioteca Aspose.PDF para .NET para incorporar una lista ordenada en HTML a un documento. Este nuevo conocimiento se puede aplicar para mejorar los procesos de creación y manipulación de documentos.