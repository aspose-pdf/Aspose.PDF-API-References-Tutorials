---
title: Tabulaciones personalizadas en archivos PDF
linktitle: Tabulaciones personalizadas en archivos PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear tabulaciones personalizadas en archivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-text/custom-tab-stops/
---

Este tutorial lo guiará a través del proceso de creación de tabulaciones personalizadas en un archivo PDF utilizando Aspose.PDF para .NET. El código fuente C# proporcionado muestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea crear tabulaciones personalizadas, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Crear una nueva instancia de documento
 Crear una nueva instancia`Document` objeto agregando la siguiente línea de código:

```csharp
Document _pdfdocument = new Document();
```

## Paso 5: Agregar una página al documento
 Agregue una nueva página al documento usando el`Add` método de la`Pages`colección. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Paso 6: Crea tabulaciones personalizadas
 Crear un`TabStops` objeto y agréguele tabulaciones personalizadas. Establezca el tipo de alineación y el tipo de línea guía para cada tabulación.

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

## Paso 7: Crea fragmentos de texto con tabulaciones
 Crear`TextFragment` objetos y pasarles las tabulaciones personalizadas. Utilice los caracteres especiales`#$TAB` para indicar las tabulaciones dentro del texto.

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

## Paso 8: Guarde el documento PDF
 Guarde el documento PDF utilizando el`Save` método de la`Document` objeto.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Código fuente de muestra para tabulaciones personalizadas con Aspose.PDF para .NET 
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
Ha creado correctamente un documento PDF con tabulaciones personalizadas utilizando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta de archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

R: Este tutorial se centra en guiarlo a través del proceso de creación de tabulaciones personalizadas en un archivo PDF mediante la biblioteca Aspose.PDF para .NET. El código fuente C# proporcionado demuestra los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres debo importar para este tutorial?

R: En el archivo de código donde desea crear tabulaciones personalizadas, importe los siguientes espacios de nombres al comienzo del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: En el código, busque la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo una nueva instancia de documento?

 A: En el paso 4, creará una nueva instancia`Document` objeto utilizando el código proporcionado.

#### P: ¿Cómo agrego una página al documento?

 A: En el paso 5, agregará una nueva página al documento utilizando el`Add` método de la`Pages` recopilación.

#### P: ¿Cómo puedo crear tabulaciones personalizadas?

 A: En el paso 6, crearás un`TabStops` objeto y agregarle tabulaciones personalizadas. También establecerá la alineación y los tipos de guía para cada tabulación.

#### P: ¿Cómo puedo crear fragmentos de texto con tabulaciones?

 A: En el paso 7, crearás`TextFragment` objetos y pasarles las tabulaciones personalizadas. Usarás los caracteres especiales`#$TAB` para indicar las tabulaciones dentro del texto.

#### P: ¿Cómo guardo el documento PDF?

 A: En el paso 8, guardará el documento PDF utilizando el`Save` método de la`Document` objeto.

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Al seguir este tutorial, aprendió a crear un documento PDF con tabulaciones personalizadas mediante Aspose.PDF para .NET. Esto puede resultar útil para organizar y alinear el texto de manera estructurada.