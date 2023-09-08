---
title: Agregue HTML usando DOM y sobrescritura de PDF
linktitle: Agregue HTML usando DOM y sobrescriba
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar contenido HTML usando DOM y sobrescritura de PDF en Aspose.PDF para .NET.
type: docs
weight: 50
url: /es/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Este tutorial lo guiará a través del proceso de agregar contenido HTML usando DOM (modelo de objetos de documento) en Aspose.PDF para .NET. Además, aprenderá a sobrescribir estilos para el contenido HTML. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea agregar el contenido HTML, agregue lo siguiente usando directivas en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: establezca el directorio del documento y la ruta del archivo de salida
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 4: crea un nuevo objeto de documento
 Crear una instancia nueva`Document` objeto agregando la siguiente línea de código:

```csharp
Document doc = new Document();
```

## Paso 5: agregue una página al documento
 Agregue una nueva página al documento usando el`Add` método de la`Pages`recopilación. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Paso 6: crea un HtmlFragment con el contenido HTML
 Crear una instancia de`HtmlFragment` objeto y proporcione el contenido HTML deseado. En el código proporcionado, el contenido HTML se asigna a la variable`title`. Puede modificar el contenido HTML según sea necesario.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Paso 7: sobrescriba los estilos del contenido HTML
 Para sobrescribir los estilos del contenido HTML, puede modificar el`TextState` propiedades de la`HtmlFragment` objeto. En el código proporcionado, la familia de fuentes se cambia a "Arial" y el tamaño de fuente se establece en 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Paso 8: establecer la información del margen
Ajuste los márgenes superior e inferior del fragmento HTML si es necesario. En el código proporcionado, el margen inferior se establece en 10 y el margen superior se establece en 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Paso 9: agregue el fragmento Html a la página
 Añade el`HtmlFragment` oponerse a la recopilación de párrafos de la página.

```csharp
page.Paragraphs.Add(title);
```

## Paso 10: guarde el documento PDF
 Guarde el documento PDF usando el`Save` método de la`Document` objeto. Especifique la ruta del archivo de salida que estableció en el Paso 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para agregar HTML usando DOM y sobrescribir usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear una instancia del objeto Documento
Document doc = new Document();
// Agregar una página a una colección de páginas de un archivo PDF
Page page = doc.Pages.Add();
// Crear una instancia de HtmlFragment con contenido HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//La familia de fuentes de 'Verdana' se restablecerá a 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Establecer información del margen inferior
title.Margin.Bottom = 10;
// Establecer información del margen superior
title.Margin.Top = 400;
// Agregar fragmento HTML a la colección de párrafos de la página
page.Paragraphs.Add(title);
// Guardar archivo PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);
```

## Conclusión
Ha agregado con éxito contenido HTML usando DOM en Aspose.PDF para .NET y sobrescribió los estilos del contenido HTML. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

R: Este tutorial está diseñado para guiarlo a través del proceso de agregar contenido HTML a un documento PDF utilizando el Modelo de objetos de documento (DOM) en Aspose.PDF para .NET. Además, aprenderá a sobrescribir estilos para el contenido HTML, lo que le permitirá personalizar su apariencia. El tutorial proporciona fragmentos de código fuente de C# para demostrar los pasos necesarios.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: En el archivo de código donde desea agregar contenido HTML, importe los siguientes espacios de nombres al principio del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio del documento y la ruta del archivo de salida?

 R: En el código, localice la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo un objeto Documento?

 R: En el paso 4, creará una instancia de un nuevo`Document` objeto usando la siguiente línea de código:

```csharp
Document doc = new Document();
```

#### P: ¿Cómo agrego una página al documento?

 R: En el paso 5, agregará una nueva página al documento usando el`Add` método de la`Pages` recopilación:

```csharp
Page page = doc.Pages.Add();
```

#### P: ¿Cómo puedo configurar contenido HTML usando DOM?

 R: En el paso 6, creará un`HtmlFragment` objeto y asígnele el contenido HTML deseado. El contenido HTML se asigna a la variable.`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### P: ¿Cómo puedo sobrescribir los estilos del contenido HTML?

 R: En el paso 7, sobrescribirá los estilos del contenido HTML modificando el`TextState` propiedades de la`HtmlFragment` objeto. Por ejemplo, puedes cambiar la familia de fuentes a "Arial" y establecer el tamaño de fuente en 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### P: ¿Puedo ajustar el margen del contenido HTML?

R: Sí, en el Paso 8, puedes ajustar los márgenes superior e inferior del fragmento HTML según sea necesario:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### P: ¿Cómo agrego el fragmento Html al documento PDF?

 R: En el paso 9, agregará el`HtmlFragment` objeto (`title`) a la colección de párrafos de la página:

```csharp
page.Paragraphs.Add(title);
```

#### P: ¿Cómo guardo el documento PDF resultante?

 R: Después de agregar el contenido HTML y personalizar sus estilos, use el`Save` método de la`Document` objeto para guardar el documento PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, habrá aprendido con éxito cómo incorporar contenido HTML utilizando el modelo de objetos de documento (DOM) en Aspose.PDF para .NET. Además, obtuvo la capacidad de sobrescribir estilos para personalizar la apariencia del contenido HTML dentro del documento PDF resultante.