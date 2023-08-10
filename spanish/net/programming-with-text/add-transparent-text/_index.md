---
title: Agregar texto transparente
linktitle: Agregar texto transparente
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar texto transparente a un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-text/add-transparent-text/
---

Este tutorial lo guiará a través del proceso de agregar texto transparente a un documento PDF utilizando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código en el que desea agregar texto transparente, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: crea una nueva instancia de documento
 Instanciar un nuevo`Document` objeto agregando la siguiente línea de código:

```csharp
Document doc = new Document();
```

## Paso 5: Agregar una página al documento
 Agregue una nueva página al documento usando el`Add` metodo de la`Pages` recopilación. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Paso 6: crea un objeto gráfico
 Crear un nuevo`Graph` objeto con un ancho y alto específicos.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Paso 7: crea un rectángulo con transparencia
 Cree un rectángulo con dimensiones específicas y establezca su color de relleno en un color transparente usando el`Color.FromRgb` método.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Paso 8: agregue el objeto Graph a la página
 Añade el`Graph` oponerse a la colección de párrafos de la página.

```csharp
page.Paragraphs.Add(canvas);
```

## Paso 9: Establecer la posición del objeto Gráfico
 Selecciona el`IsChangePosition` propiedad de la`Graph` oponerse a`false` para evitar que cambie de posición.

```csharp
canvas. IsChangePosition = false;
```

## Paso 10: Crea un TextFragment con transparencia
 Crear un`TextFragment` objeto y establezca su contenido en el texto deseado. Selecciona el`ForegroundColor` propiedad de la`TextState` a un color con transparencia usando el`Color.FromArgb` método.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Paso 11: Guarde el documento PDF
 Guarde el documento PDF usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Ejemplo de código fuente para agregar texto transparente usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear instancia de documento
Document doc = new Document();
// Crear una colección de página a página de un archivo PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Crear objeto gráfico
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Crear instancia de rectángulo con ciertas dimensiones
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Crear objeto de color desde el canal de color alfa
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Agregar rectángulo a la colección de formas del objeto Graph
canvas.Shapes.Add(rect);
// Agregar objeto de gráfico a la colección de párrafos del objeto de página
page.Paragraphs.Add(canvas);
// Establecer valor para no cambiar la posición del objeto gráfico
canvas.IsChangePosition = false;
// Crear instancia de TextFragment con valor de muestra
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Crear objeto de color desde el canal alfa
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Establecer información de color para la instancia de texto
text.TextState.ForegroundColor = color;
// Agregar texto a la colección de párrafos de instancia de página
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Conclusión
Ha agregado con éxito texto transparente a su documento PDF utilizando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificado.