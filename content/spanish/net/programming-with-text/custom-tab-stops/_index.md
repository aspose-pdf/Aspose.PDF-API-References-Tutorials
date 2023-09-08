---
title: Tabulaciones personalizadas en un archivo PDF
linktitle: Tabulaciones personalizadas en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a crear tabulaciones personalizadas en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-text/custom-tab-stops/
---

Este tutorial lo guiará a través del proceso de creación de tabulaciones personalizadas en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea crear tabulaciones personalizadas, agregue las siguientes directivas de uso en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: configurar el directorio de documentos
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

## Paso 4: crear una nueva instancia de documento
 Crear una instancia nueva`Document` objeto agregando la siguiente línea de código:

```csharp
Document _pdfdocument = new Document();
```

## Paso 5: agregue una página al documento
 Agregue una nueva página al documento usando el`Add` método de la`Pages`recopilación. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Paso 6: cree tabulaciones personalizadas
 Crear un`TabStops` objeto y agregarle tabulaciones personalizadas. Establezca el tipo de alineación y el tipo de directriz para cada tabulación.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Paso 7: crea fragmentos de texto con tabulaciones
 Crear`TextFragment` objetos y pasarles las tabulaciones personalizadas. Usa los caracteres especiales`#$TAB` para indicar las tabulaciones dentro del texto.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Paso 8: guarde el documento PDF
 Guarde el documento PDF usando el`Save` método de la`Document` objeto.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Código fuente de muestra para tabulaciones personalizadas usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Conclusión
Ha creado con éxito un documento PDF con tabulaciones personalizadas utilizando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

R: Este tutorial se centra en guiarlo a través del proceso de creación de tabulaciones personalizadas en un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres debo importar para este tutorial?

R: En el archivo de código donde desea crear tabulaciones personalizadas, importe los siguientes espacios de nombres al principio del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio de documentos?

 R: En el código, busque la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo una nueva instancia de documento?

 R: En el paso 4, creará una instancia de un nuevo`Document` objeto usando el código proporcionado.

#### P: ¿Cómo agrego una página al documento?

 R: En el paso 5, agregará una nueva página al documento usando el`Add` método de la`Pages` recopilación.

#### P: ¿Cómo creo tabulaciones personalizadas?

 R: En el paso 6, creará un`TabStops` objeto y agregarle tabulaciones personalizadas. También establecerá tipos de alineación y guía para cada tabulación.

#### P: ¿Cómo creo fragmentos de texto con tabulaciones?

 R: En el paso 7, creará`TextFragment` objetos y pasarles las tabulaciones personalizadas. Usarás los caracteres especiales.`#$TAB` para indicar las tabulaciones dentro del texto.

#### P: ¿Cómo guardo el documento PDF?

 R: En el paso 8, guardará el documento PDF usando el`Save` método de la`Document` objeto.

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Al seguir este tutorial, habrá aprendido cómo crear un documento PDF con tabulaciones personalizadas usando Aspose.PDF para .NET. Esto puede resultar útil para organizar y alinear texto de forma estructurada.