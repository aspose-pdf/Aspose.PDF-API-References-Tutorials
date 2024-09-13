---
title: Agregar HTML mediante DOM y sobrescritura de PDF
linktitle: Agregar HTML usando DOM y sobrescribir
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar contenido HTML usando DOM y sobrescritura de PDF en Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Este tutorial le guiará a través del proceso de agregar contenido HTML mediante DOM (Document Object Model) en Aspose.PDF para .NET. Además, aprenderá a sobrescribir estilos para el contenido HTML. El código fuente C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea agregar el contenido HTML, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: Establezca el directorio del documento y la ruta del archivo de salida
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 4: Crear un nuevo objeto Documento
 Crear una nueva instancia`Document` objeto agregando la siguiente línea de código:

```csharp
Document doc = new Document();
```

## Paso 5: Agregar una página al documento
 Agregue una nueva página al documento utilizando el`Add` método de la`Pages` colección. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Paso 6: Crea un HtmlFragment con el contenido HTML
 Crear una instancia`HtmlFragment` objeto y proporcionar el contenido HTML deseado. En el código proporcionado, el contenido HTML se asigna a la variable`title`Puede modificar el contenido HTML según sea necesario.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Paso 7: Sobrescribir los estilos del contenido HTML
 Para sobrescribir los estilos del contenido HTML, puede modificar el`TextState` Propiedades de la`HtmlFragment` objeto. En el código proporcionado, la familia de fuentes se cambia a "Arial" y el tamaño de fuente se establece en 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Paso 8: Establecer la información del margen
Ajuste los márgenes superior e inferior del fragmento HTML si es necesario. En el código proporcionado, el margen inferior está configurado en 10 y el margen superior en 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Paso 9: Agrega el HtmlFragment a la página
 Añade el`HtmlFragment` objeto a la colección de párrafos de la página.

```csharp
page.Paragraphs.Add(title);
```

## Paso 10: Guarde el documento PDF
 Guarde el documento PDF utilizando el`Save` método de la`Document` objeto. Especifique la ruta del archivo de salida que configuró en el paso 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para agregar HTML mediante DOM y sobrescribir mediante Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear una instancia del objeto Documento
Document doc = new Document();
// Agregar una página a la colección de páginas de un archivo PDF
Page page = doc.Pages.Add();
// Crear una instancia de HtmlFragment con contenido HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La familia de fuentes de 'Verdana' se restablecerá a 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Establecer la información del margen inferior
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
Ha añadido contenido HTML correctamente mediante DOM en Aspose.PDF para .NET y ha sobrescrito los estilos del contenido HTML. El archivo PDF resultante ahora se puede encontrar en la ruta de archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

R: Este tutorial está diseñado para guiarlo a través del proceso de agregar contenido HTML a un documento PDF mediante el Modelo de objetos de documento (DOM) en Aspose.PDF para .NET. Además, aprenderá a sobrescribir estilos para el contenido HTML, lo que le permitirá personalizar su apariencia. El tutorial proporciona fragmentos de código fuente de C# para demostrar los pasos necesarios.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: En el archivo de código donde desea agregar contenido HTML, importe los siguientes espacios de nombres al comienzo del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio del documento y la ruta del archivo de salida?

 A: En el código, localiza la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo un objeto Documento?

 A: En el paso 4, creará una nueva instancia`Document` objeto utilizando la siguiente línea de código:

```csharp
Document doc = new Document();
```

#### P: ¿Cómo agrego una página al documento?

 A: En el paso 5, agregará una nueva página al documento utilizando el`Add` método de la`Pages` recopilación:

```csharp
Page page = doc.Pages.Add();
```

#### P: ¿Cómo puedo configurar contenido HTML utilizando el DOM?

 A: En el paso 6, crearás un`HtmlFragment` objeto y asígnele el contenido HTML que desee. El contenido HTML se asigna a la variable`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### P: ¿Cómo puedo sobrescribir los estilos del contenido HTML?

 A: En el paso 7, sobrescribirá los estilos del contenido HTML modificando el`TextState` Propiedades de la`HtmlFragment`objeto. Por ejemplo, puede cambiar la familia de fuentes a "Arial" y establecer el tamaño de fuente en 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### P: ¿Puedo ajustar el margen del contenido HTML?

R: Sí, en el paso 8, puedes ajustar los márgenes inferior y superior del fragmento HTML según sea necesario:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### P: ¿Cómo agrego el HtmlFragment al documento PDF?

 A: En el paso 9, agregarás el`HtmlFragment` objeto (`title`) a la colección de párrafos de la página:

```csharp
page.Paragraphs.Add(title);
```

#### P: ¿Cómo guardo el documento PDF resultante?

 A: Después de agregar el contenido HTML y personalizar sus estilos, utilice el`Save` método de la`Document` objeto para guardar el documento PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, aprendió a incorporar contenido HTML mediante el Modelo de objetos de documento (DOM) en Aspose.PDF para .NET. Además, adquirió la capacidad de sobrescribir estilos para adaptar la apariencia del contenido HTML dentro del documento PDF resultante.