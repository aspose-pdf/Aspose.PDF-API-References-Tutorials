---
title: Crear PDF con varias columnas
linktitle: Crear PDF con varias columnas
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear un PDF de varias columnas utilizando Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-text/create-multi-column-pdf/
---
Este tutorial lo guiará a través del proceso de creación de un PDF de varias columnas con Aspose.PDF para .NET. El código fuente de C# proporcionado muestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea crear un PDF de varias columnas, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Crear una nueva instancia de documento
 Crear una nueva instancia`Document` objeto agregando la siguiente línea de código:

```csharp
Document doc = new Document();
```

## Paso 5: Establezca los márgenes de la página
 Especifique la información del margen izquierdo y derecho para el archivo PDF utilizando el`PageInfo.Margin` propiedad de la`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Paso 6: Agregar una página al documento
 Agregue una nueva página al documento usando el`Add` método de la`Pages`colección. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Paso 7: Crea un objeto gráfico y agrega una línea
 Crear uno nuevo`Graph` objeto con dimensiones específicas y agréguele una línea. Luego, agregue el`Graph` objeto a la`Paragraphs` colección de la página.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Paso 8: Agregar texto de encabezado con formato HTML
 Crear un`HtmlFragment` objeto y establezca su contenido en el texto HTML deseado. Luego, agregue el fragmento al`Paragraphs` colección de la página.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Paso 9: Crea un FloatingBox con múltiples columnas
 Crear un`FloatingBox` objeto y establezca el número de columnas y el espaciado entre columnas. Luego, agregue fragmentos de texto y una línea al`Paragraphs` colección de la`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Paso 10: Guarde el documento PDF
 Guarde el documento PDF utilizando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir);
```

### Código fuente de muestra para crear un PDF de varias columnas con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//Especifique la información del margen izquierdo para el archivo PDF
doc.PageInfo.Margin.Left = 40;
// Especifique la información del margen derecho para el archivo PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Agregar la línea a la colección de paráfrasis del objeto de sección
page.Paragraphs.Add(graph1);
// Especifique las coordenadas de la línea
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Crear variables de cadena con texto que contenga etiquetas html
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Crear párrafos de texto que contengan texto HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Añadir cuatro columnas en la sección
box.ColumnInfo.ColumnCount = 2;
// Establezca el espaciado entre las columnas
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Crea un objeto gráfico para dibujar una línea
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Especifique las coordenadas de la línea
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Agregar la línea a la colección de párrafos del objeto de sección
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Conclusión
Ha creado correctamente un PDF de varias columnas con Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta de archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

Este tutorial se centra en guiarlo a través del proceso de creación de un PDF de varias columnas utilizando la biblioteca Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres debo importar para este tutorial?

R: En el archivo de código donde desea crear un PDF de varias columnas, importe los siguientes espacios de nombres al comienzo del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: En el código, busque la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo una nueva instancia de documento?

 A: En el paso 4, creará una nueva instancia`Document` objeto utilizando el código proporcionado.

#### P: ¿Cómo configuro los márgenes de la página?

 A: En el paso 5, utilizarás el`PageInfo.Margin` propiedad de la`Document` para especificar la información del margen izquierdo y derecho del archivo PDF.

#### P: ¿Cómo agrego una página al documento?

 A: En el paso 6, agregará una nueva página al documento utilizando el`Add` método de la`Pages` recopilación.

#### P: ¿Cómo creo un objeto Gráfico y agrego una línea?

 A: En el paso 7, crearás un nuevo`Graph` objeto, agréguele una línea y luego agregue el`Graph` objeto a la`Paragraphs` colección de la página.

#### P: ¿Cómo puedo agregar texto de encabezado con formato HTML?

 A: En el paso 8, crearás un`HtmlFragment` objeto y establezca su contenido en el texto HTML deseado, luego agregue el fragmento al`Paragraphs` colección de la página.

#### P: ¿Cómo creo un FloatingBox con múltiples columnas?

 A: En el paso 9, crearás un`FloatingBox` objeto con múltiples columnas y espaciado entre columnas, luego agregue fragmentos de texto y una línea al`Paragraphs` colección de la`FloatingBox`.

#### P: ¿Cómo guardo el documento PDF?

 A: En el paso 10, guardará el documento PDF utilizando el`Save` método de la`Document` objeto.

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Al seguir este tutorial, aprendió a crear un documento PDF de varias columnas con Aspose.PDF para .NET. Esto puede resultar útil para mostrar contenido en un diseño estructurado y organizado.