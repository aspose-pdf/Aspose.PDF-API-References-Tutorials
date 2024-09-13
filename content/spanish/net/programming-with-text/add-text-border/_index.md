---
title: Agregar borde de texto en archivo PDF
linktitle: Agregar borde de texto en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar un borde de texto en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-text/add-text-border/
---
Este tutorial le guiará a través del proceso de agregar un borde de texto en un archivo PDF mediante Aspose.PDF para .NET. El código fuente de C# proporcionado muestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea agregar el borde de texto, agregue la siguiente directiva using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Crear un nuevo objeto Documento
 Crear una nueva instancia`Document` objeto agregando la siguiente línea de código:

```csharp
Document pdfDocument = new Document();
```

## Paso 5: Agregar una página al documento
 Agregue una nueva página al documento utilizando el`Add` método de la`Pages` colección. En el código proporcionado, la nueva página se asigna a la variable`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Paso 6: Crear un fragmento de texto
 Crear un`TextFragment`objeto y proporcione el texto deseado. Establezca la posición del fragmento de texto utilizando el`Position` Propiedad. En el código proporcionado, el texto se establece como "texto principal" y se ubica en (100, 600) en la página.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Paso 7: Establecer propiedades de texto
Personalice las propiedades del texto, como el tamaño de fuente, el tipo de fuente, el color de fondo, el color de primer plano, etc. En el código proporcionado, se establecen propiedades como el tamaño de fuente, la fuente, el color de fondo, el color de primer plano y el color del trazo para el fragmento de texto.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Paso 8: Habilitar el borde de texto
 Para habilitar el borde del texto, configure el`DrawTextRectangleBorder` propiedad del fragmento de texto`TextState` a`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Paso 9: Agrega el TextFragment a la página
 Utilice el`TextBuilder` clase para agregar el`TextFragment` objeto a la página.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Paso 10: Guarde el documento PDF
 Guarde el documento PDF utilizando el`Save` método de la`Document` objeto. Especifique la ruta del archivo de salida que configuró en el paso 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Código fuente de muestra para agregar un borde de texto con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear nuevo objeto de documento
Document pdfDocument = new Document();
// Obtener página específica
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crear fragmento de texto
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Establecer propiedades de texto
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Establezca la propiedad StrokingColor para dibujar un borde (trazo) alrededor del rectángulo de texto
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Establezca el valor de la propiedad DrawTextRectangleBorder en verdadero
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Guardar el documento
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusión
Ha añadido correctamente un borde de texto a su documento PDF con Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta de archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque principal de este tutorial?

A: Este tutorial lo guía a través del proceso de agregar un borde de texto a un archivo PDF mediante la biblioteca Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: En el archivo de código donde desea agregar el borde de texto, importe los siguientes espacios de nombres al comienzo del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: En el código, localiza la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo un objeto Documento?

 A: En el paso 4, creará una nueva instancia`Document` objeto utilizando la siguiente línea de código:

```csharp
Document pdfDocument = new Document();
```

#### P: ¿Cómo agrego una página al documento?

 A: En el paso 5, agregará una nueva página al documento utilizando el`Add` método de la`Pages` recopilación:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### P: ¿Cómo creo un TextFragment y establezco su posición?

 A: En el paso 6, crearás un`TextFragment` objeto y establecer su posición en la página utilizando el`Position` propiedad:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### P: ¿Cómo puedo personalizar las propiedades del texto, incluido el borde del texto?

R: En el paso 7, personalizará varias propiedades de texto, como el tamaño de fuente, el tipo de fuente, el color de fondo, el color de primer plano y el borde del texto:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### P: ¿Cómo agrego el TextFragment al documento PDF?

 A: En el paso 9, utilizarás el`TextBuilder` clase para agregar el`TextFragment` objeto a la pagina:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### P: ¿Cómo guardo el documento PDF resultante?

A: Después de agregar el texto con un borde, utilice el`Save` método de la`Document` objeto para guardar el documento PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Si siguió este tutorial, aprendió a mejorar su documento PDF agregando un borde de texto con Aspose.PDF para .NET. Esto puede resultar particularmente útil para resaltar contenido de texto específico dentro de sus archivos PDF.