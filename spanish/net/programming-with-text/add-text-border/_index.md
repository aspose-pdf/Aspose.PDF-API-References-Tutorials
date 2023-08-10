---
title: Agregar borde de texto
linktitle: Agregar borde de texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar un borde de texto a un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-text/add-text-border/
---

Este tutorial lo guiará a través del proceso de agregar un borde de texto usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código donde desea agregar el borde de texto, agregue la siguiente directiva de uso en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Cree un nuevo objeto Documento
 Instanciar un nuevo`Document` objeto agregando la siguiente línea de código:

```csharp
Document pdfDocument = new Document();
```

## Paso 5: Agregar una página al documento
 Agregue una nueva página al documento usando el`Add` metodo de la`Pages` recopilación. En el código proporcionado, la nueva página se asigna a la variable`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Paso 6: crea un fragmento de texto
 Crear un`TextFragment`objeto y proporcionar el texto deseado. Establezca la posición del fragmento de texto usando el`Position` propiedad. En el código proporcionado, el texto se establece en "texto principal" y se coloca en (100, 600) en la página.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Paso 7: establecer las propiedades del texto
Personalice las propiedades del texto, como el tamaño de fuente, el tipo de fuente, el color de fondo, el color de primer plano, etc. En el código proporcionado, las propiedades como el tamaño de fuente, la fuente, el color de fondo, el color de primer plano y el color de trazo se establecen para el fragmento de texto.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Paso 8: habilite el borde del texto
 Para habilitar el borde de texto, configure el`DrawTextRectangleBorder` propiedad del fragmento de texto`TextState` a`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Paso 9: Agrega el TextFragment a la página
 Utilizar el`TextBuilder` clase para agregar el`TextFragment` objeto a la página.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Paso 10: Guarde el documento PDF
 Guarde el documento PDF usando el`Save` metodo de la`Document` objeto. Especifique la ruta del archivo de salida que configuró en el paso 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Ejemplo de código fuente para Agregar borde de texto usando Aspose.PDF para .NET 
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
// Establezca la propiedad StrokingColor para dibujar el borde (trazar) alrededor del rectángulo de texto
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Establezca el valor de la propiedad DrawTextRectangleBorder en verdadero
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Guardar el documento
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusión
Ha agregado con éxito un borde de texto a su documento PDF utilizando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificado.