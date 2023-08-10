---
title: Agregar sangría de líneas subsiguientes
linktitle: Agregar sangría de líneas subsiguientes
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar sangría de líneas subsiguientes al texto usando Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-text/add-subsequent-lines-indent/
---

Este tutorial lo guiará a través del proceso de agregar sangría de líneas subsiguientes al texto usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código en el que desea agregar sangría de líneas posteriores, agregue la siguiente directiva de uso en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Cree un nuevo objeto Documento
 Instanciar un nuevo`Document` objeto agregando la siguiente línea de código:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Paso 5: Agregar una página al documento
 Agregue una nueva página al documento usando el`Add` metodo de la`Pages` recopilación. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Paso 6: Cree un TextFragment con sangría de líneas subsiguientes
 Instanciar un`TextFragment` objeto y proporcionar el texto deseado. En el código proporcionado, el texto se asigna a la variable`text` . Luego, inicializa`TextFormattingOptions` Para el`TextFragment` y especificar el`SubsequentLinesIndent` valor.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Paso 7: Agrega el TextFragment a la página
 Añade el`TextFragment` oponerse a la colección de párrafos de la página.

```csharp
page.Paragraphs.Add(text);
```

## Paso 8: Repita los pasos 6 y 7 para líneas adicionales
Para agregar líneas posteriores con la misma sangría, repita los pasos 6 y 7 para cada línea. Actualice el contenido del texto según sea necesario.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Paso 9: Guarde el documento PDF
 Guarde el documento PDF usando el`Save` metodo de la`Document` objeto. Especifique la ruta del archivo de salida.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Ejemplo de código fuente para Agregar sangría de líneas subsiguientes usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear nuevo objeto de documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Inicie TextFormattingOptions para el fragmento de texto y especifique el valor de SubsiguienteLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusión
Ha agregado con éxito la sangría de líneas subsiguientes al texto usando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificado.