---
title: Agregar borde de texto en un archivo PDF
linktitle: Agregar borde de texto en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar un borde de texto en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-text/add-text-border/
---
Este tutorial lo guiará a través del proceso de agregar un borde de texto en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea agregar el borde de texto, agregue la siguiente directiva usando en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: configurar el directorio de documentos
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

## Paso 4: crea un nuevo objeto de documento
 Crear una instancia nueva`Document` objeto agregando la siguiente línea de código:

```csharp
Document pdfDocument = new Document();
```

## Paso 5: agregue una página al documento
 Agregue una nueva página al documento usando el`Add` método de la`Pages`recopilación. En el código proporcionado, la nueva página se asigna a la variable`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Paso 6: crea un fragmento de texto
 Crear un`TextFragment` objeto y proporcione el texto deseado. Establezca la posición del fragmento de texto usando el`Position` propiedad. En el código proporcionado, el texto se establece como "texto principal" y se coloca en (100, 600) en la página.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Paso 7: establecer las propiedades del texto
Personalice las propiedades del texto, como el tamaño de fuente, el tipo de fuente, el color de fondo, el color de primer plano, etc. En el código proporcionado, se establecen propiedades como el tamaño de fuente, la fuente, el color de fondo, el color de primer plano y el color de trazo para el fragmento de texto.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Paso 8: habilitar el borde de texto
 Para habilitar el borde del texto, configure el`DrawTextRectangleBorder`propiedad del fragmento de texto`TextState` a`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Paso 9: agregue el fragmento de texto a la página
 Utilizar el`TextBuilder` clase para agregar el`TextFragment` objeto a la página.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Paso 10: guarde el documento PDF
 Guarde el documento PDF usando el`Save` método de la`Document` objeto. Especifique la ruta del archivo de salida que estableció en el Paso 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Código fuente de muestra para Agregar borde de texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear nuevo objeto de documento
Document pdfDocument = new Document();
// Obtener página particular
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Crear fragmento de texto
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Establecer propiedades de texto
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Establezca la propiedad StrokeingColor para dibujar el borde (trazar) alrededor del rectángulo de texto
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Establezca el valor de la propiedad DrawTextRectangleBorder en verdadero
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// guardar el documento
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusión
Ha agregado con éxito un borde de texto a su documento PDF usando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque principal de este tutorial?

R: Este tutorial lo guía a través del proceso de agregar un borde de texto a un archivo PDF usando la biblioteca Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: En el archivo de código donde desea agregar el borde de texto, importe los siguientes espacios de nombres al principio del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio de documentos?

 R: En el código, localice la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo un objeto Documento?

 R: En el paso 4, creará una instancia de un nuevo`Document` objeto usando la siguiente línea de código:

```csharp
Document pdfDocument = new Document();
```

#### P: ¿Cómo agrego una página al documento?

 R: En el paso 5, agregará una nueva página al documento usando el`Add` método de la`Pages` recopilación:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### P: ¿Cómo creo un TextFragment y establezco su posición?

 R: En el paso 6, creará un`TextFragment`objeto y establezca su posición en la página usando el`Position` propiedad:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### P: ¿Cómo puedo personalizar las propiedades del texto, incluido el borde del texto?

R: En el Paso 7, personalizará varias propiedades del texto, como el tamaño de fuente, el tipo de fuente, el color de fondo, el color de primer plano y el borde del texto:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### P: ¿Cómo agrego el fragmento de texto al documento PDF?

 R: En el paso 9, utilizará el`TextBuilder` clase para agregar el`TextFragment` objeto a la página:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### P: ¿Cómo guardo el documento PDF resultante?

 R: Después de agregar el texto con un borde, use el`Save` método de la`Document` objeto para guardar el documento PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Al seguir este tutorial, habrá aprendido cómo mejorar su documento PDF agregando un borde de texto usando Aspose.PDF para .NET. Esto puede resultar particularmente útil para enfatizar contenido de texto específico dentro de sus archivos PDF.