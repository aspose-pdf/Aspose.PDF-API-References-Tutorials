---
title: Agregar HTML usando DOM
linktitle: Agregar HTML usando DOM
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar contenido HTML usando DOM en Aspose.PDF para .NET.
type: docs
weight: 40
url: /es/net/programming-with-text/add-html-using-dom/
---

Este tutorial lo guiará a través del proceso de agregar contenido HTML usando DOM (Document Object Model) en Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

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
```

## Paso 3: establezca el directorio del documento y la ruta del archivo de salida
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

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
Instanciar un`HtmlFragment` objeto y proporcionar el contenido HTML deseado. En el código proporcionado, el contenido HTML se asigna a la variable`titel`. Puede modificar el contenido HTML según sea necesario.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Paso 7: Establecer información de margen
Ajuste el margen inferior y superior del fragmento HTML si es necesario. En el código proporcionado, el margen inferior se establece en 10 y el margen superior se establece en 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Paso 8: agregue HtmlFragment a la página
 Añade el`HtmlFragment` oponerse a la colección de párrafos de la página.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Paso 9: Guarde el documento PDF
 Guarde el documento PDF usando el`Save` metodo de la`Document` objeto. Especifique la ruta del archivo de salida que configuró en el paso 3.

```csharp
doc.Save(dataDir);
```

## Paso 10: Mostrar el mensaje de éxito
Muestra un mensaje de éxito junto con la ruta donde se guardó el archivo PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para agregar HTMLUsing DOM usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanciar objeto de documento
Document doc = new Document();
// Agregar una página a la colección de páginas de un archivo PDF
Page page = doc.Pages.Add();
// Instancia HtmlFragment con contenido HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Establecer información del margen inferior
titel.Margin.Bottom = 10;
// Establecer la información del margen superior
titel.Margin.Top = 200;
// Agregar fragmento HTML a la colección de párrafos de la página
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Conclusión
Ha agregado con éxito contenido HTML usando DOM en Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificado.