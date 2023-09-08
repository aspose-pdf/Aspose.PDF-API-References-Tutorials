---
title: Agregar sangría de líneas posteriores en un archivo PDF
linktitle: Agregar sangría de líneas posteriores en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar sangría de líneas posteriores al texto en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-text/add-subsequent-lines-indent/
---
Este tutorial lo guiará a través del proceso de agregar sangría de líneas posteriores al texto en un archivo PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o utilizar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importar los espacios de nombres necesarios
En el archivo de código donde desea agregar sangría de líneas posteriores, agregue la siguiente directiva de uso en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: configurar el directorio de documentos
 En el código, localice la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde están almacenados sus documentos.

## Paso 4: crea un nuevo objeto de documento
 Crear una instancia nueva`Document` objeto agregando la siguiente línea de código:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Paso 5: agregue una página al documento
 Agregue una nueva página al documento usando el`Add` método de la`Pages`recopilación. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Paso 6: cree un fragmento de texto con sangría de líneas posteriores
 Crear una instancia de`TextFragment` objeto y proporcione el texto deseado. En el código proporcionado, el texto se asigna a la variable.`text` . Luego, inicializa`TextFormattingOptions` Para el`TextFragment` especificar el`SubsequentLinesIndent` valor.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Paso 7: agregue el fragmento de texto a la página
 Añade el`TextFragment` oponerse a la recopilación de párrafos de la página.

```csharp
page.Paragraphs.Add(text);
```

## Paso 8: repita los pasos 6 y 7 para líneas adicionales
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

## Paso 9: guarde el documento PDF
 Guarde el documento PDF usando el`Save` método de la`Document` objeto. Especifique la ruta del archivo de salida.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Código fuente de muestra para agregar sangría de líneas posteriores usando Aspose.PDF para .NET 
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
Ha agregado correctamente sangría de líneas posteriores al texto utilizando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

R: Este tutorial proporciona una guía completa sobre cómo agregar sangrías de líneas posteriores al texto en un archivo PDF usando la biblioteca Aspose.PDF para .NET. Incluye ejemplos de código fuente de C# para ilustrar los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: En el archivo de código donde desea agregar sangría de líneas posteriores, importe los siguientes espacios de nombres al principio del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio de documentos?

 R: En el código, localice la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo un objeto Documento?

 R: En el paso 4, creará una instancia de un nuevo`Document` objeto usando la siguiente línea de código:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### P: ¿Cómo agrego una página al documento?

 R: En el paso 5, agregará una nueva página al documento usando el`Add` método de la`Pages` recopilación:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### P: ¿Cómo puedo agregar sangría de líneas posteriores al texto?

 R: En el paso 6, creará un`TextFragment` objeto y asignarle el texto deseado. Luego, inicializarás`TextFormattingOptions` Para el`TextFragment` especificar el`SubsequentLinesIndent` valor:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### P: ¿Cómo agrego el fragmento de texto al documento PDF?

 R: En el paso 7, agregará el`TextFragment` objeto (`text`) a la colección de párrafos de la página:

```csharp
page.Paragraphs.Add(text);
```

#### P: ¿Puedo repetir el proceso para líneas adicionales?

 R: Sí, en el Paso 8, puede repetir el proceso para líneas adicionales con la misma sangría creando nuevas`TextFragment` objetos y agregarlos a la colección de párrafos de la página.

#### P: ¿Cómo guardo el documento PDF resultante?

 R: Después de agregar el texto con sangría de líneas posteriores, use el`Save` método de la`Document` objeto para guardar el documento PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Al seguir este tutorial, habrá aprendido cómo mejorar la legibilidad del texto en un documento PDF agregando sangría de líneas posteriores usando Aspose.PDF para .NET. Esta técnica puede resultar útil para varios tipos de documentos e informes.