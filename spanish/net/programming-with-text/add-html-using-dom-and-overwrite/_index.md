---
title: Agregar HTML usando DOM y sobrescribir
linktitle: Agregar HTML usando DOM y sobrescribir
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar contenido HTML usando DOM en Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-text/add-html-using-dom-and-overwrite/
---

Este tutorial lo guiará a través del proceso de agregar contenido HTML usando DOM (Document Object Model) en Aspose.PDF para .NET. Además, aprenderá a sobrescribir estilos para el contenido HTML. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código donde desea agregar el contenido HTML, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: establezca el directorio del documento y la ruta del archivo de salida
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 4: Cree un nuevo objeto Documento
 Instanciar un nuevo`Document` objeto agregando la siguiente línea de código:

```csharp
Document doc = new Document();
```

## Paso 5: Agregar una página al documento
 Agregue una nueva página al documento usando el`Add` metodo de la`Pages` recopilación. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Paso 6: Cree un HtmlFragment con el contenido HTML
 Instanciar un`HtmlFragment` objeto y proporcionar el contenido HTML deseado. En el código proporcionado, el contenido HTML se asigna a la variable`title`. Puede modificar el contenido HTML según sea necesario.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Paso 7: sobrescriba los estilos para el contenido HTML
 Para sobrescribir los estilos del contenido HTML, puede modificar el`TextState` propiedades de la`HtmlFragment`objeto. En el código proporcionado, la familia de fuentes se cambia a "Arial" y el tamaño de fuente se establece en 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Paso 8: Establecer información de margen
Ajuste los márgenes inferior y superior del fragmento HTML si es necesario. En el código proporcionado, el margen inferior se establece en 10 y el margen superior se establece en 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Paso 9: Agregue HtmlFragment a la página
 Añade el`HtmlFragment` oponerse a la colección de párrafos de la página.

```csharp
page.Paragraphs.Add(title);
```

## Paso 10: Guarde el documento PDF
 Guarde el documento PDF usando el`Save` metodo de la`Document` objeto. Especifique la ruta del archivo de salida que configuró en el Paso 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para agregar HTML usando DOMAN y sobrescribir usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto de documento
Document doc = new Document();
// Agregar una página a la colección de páginas de un archivo PDF
Page page = doc.Pages.Add();
// Instancia HtmlFragment con contenido HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La familia de fuentes de 'Verdana' se restablecerá a 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Establecer información del margen inferior
title.Margin.Bottom = 10;
// Establecer la información del margen superior
title.Margin.Top = 400;
// Agregar fragmento HTML a la colección de párrafos de la página
page.Paragraphs.Add(title);
// Guardar archivo PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);
```

## Conclusión
Ha agregado con éxito contenido HTML usando DOM en Aspose.PDF para .NET y sobrescrito los estilos para el contenido HTML. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificado.