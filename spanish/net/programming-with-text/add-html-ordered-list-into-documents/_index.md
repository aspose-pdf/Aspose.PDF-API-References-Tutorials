---
title: Agregar lista ordenada HTML en documentos
linktitle: Agregar lista ordenada HTML en documentos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar una lista ordenada HTML a un documento usando Aspose.PDF para .NET.
type: docs
weight: 30
url: /es/net/programming-with-text/add-html-ordered-list-into-documents/
---

En este tutorial, aprenderá a usar la biblioteca Aspose.PDF para .NET para agregar una lista ordenada de HTML en un documento. El código proporcionado demuestra los pasos necesarios para realizar esta tarea.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código donde desea agregar la lista ordenada de HTML, agregue las siguientes directivas de uso en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: establezca el directorio del documento y la ruta del archivo de salida
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

 A continuación, busque la línea que dice`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` y reemplazar`"AddHTMLOrderedListIntoDocuments_out.pdf"` con el nombre deseado para su archivo PDF de salida.

## Paso 4: Cree un nuevo objeto Documento
 Instanciar un nuevo`Document` objeto agregando la siguiente línea de código:

```csharp
Document doc = new Document();
```

## Paso 5: Cree un objeto HtmlFragment con el contenido HTML
 Instanciar un`HtmlFragment` objeto con el contenido HTML que desea agregar al documento. En el código proporcionado, el contenido HTML se asigna a la variable`t`. Puede modificar el contenido HTML según sea necesario.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Paso 6: Agregar una página al documento
 Agregue una nueva página al documento usando el`Add` metodo de la`Pages` recopilación. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Paso 7: agregue HtmlFragment a la página
 Añade el`HtmlFragment` oponerse a la página utilizando el`Add` metodo de la`Paragraphs` recopilación.

```csharp
page.Paragraphs.Add(t);
```

## Paso 8: Guarde el documento PDF
 Guarde el archivo PDF resultante usando el`Save` metodo de la`Document` objeto. Especifique la ruta del archivo de salida que configuró en el Paso 3.

```csharp
doc.Save(outFile);
```

### Ejemplo de código fuente para Agregar lista ordenada HTML a documentos usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// La ruta al documento de salida.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Instanciar objeto de documento
Document doc = new Document();
// Crear una instancia del objeto HtmlFragment con el fragmento HTML correspondiente
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Agregar página en la colección de páginas
Page page = doc.Pages.Add();
// Agregar HtmlFragment dentro de la página
page.Paragraphs.Add(t);
// Guardar el archivo PDF resultante
doc.Save(outFile);
```

## Conclusión
Ha agregado con éxito una lista ordenada de HTML en un documento usando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificado.

Recuerde personalizar el contenido HTML y ajustar el código de acuerdo con sus requisitos específicos.