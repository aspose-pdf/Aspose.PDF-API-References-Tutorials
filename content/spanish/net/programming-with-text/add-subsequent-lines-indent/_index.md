---
title: Agregar sangría a líneas posteriores en un archivo PDF
linktitle: Agregar sangría a líneas posteriores en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda cómo agregar sangría a las líneas subsiguientes del texto en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-text/add-subsequent-lines-indent/
---
Este tutorial le guiará a través del proceso de agregar sangrías a las líneas posteriores del texto en un archivo PDF mediante Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea agregar sangría a las líneas subsiguientes, agregue la siguiente directiva using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Crear un nuevo objeto Documento
 Crear una nueva instancia`Document` objeto agregando la siguiente línea de código:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Paso 5: Agregar una página al documento
 Agregue una nueva página al documento utilizando el`Add` método de la`Pages` colección. En el código proporcionado, la nueva página se asigna a la variable`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Paso 6: Crear un TextFragment con sangría en las líneas subsiguientes
 Crear una instancia`TextFragment` objeto y proporcione el texto deseado. En el código proporcionado, el texto se asigna a la variable`text` Luego, inicializar`TextFormattingOptions` Para el`TextFragment` y especificar el`SubsequentLinesIndent` valor.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Paso 7: Agrega el TextFragment a la página
 Añade el`TextFragment` objeto a la colección de párrafos de la página.

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
 Guarde el documento PDF utilizando el`Save` método de la`Document` objeto. Especifique la ruta del archivo de salida.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Código fuente de muestra para agregar sangría a líneas posteriores mediante Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Crear nuevo objeto de documento
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//Inicialice TextFormattingOptions para el fragmento de texto y especifique el valor de FollowingLinesIndent
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
Ha agregado correctamente la sangría de las líneas subsiguientes al texto mediante Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta de archivo de salida especificada.

### Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

A: Este tutorial ofrece una guía completa sobre cómo agregar sangrías a las líneas posteriores del texto en un archivo PDF mediante la biblioteca Aspose.PDF para .NET. Incluye ejemplos de código fuente de C# para ilustrar los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres necesito importar para este tutorial?

R: En el archivo de código donde desea agregar sangría a las líneas subsiguientes, importe los siguientes espacios de nombres al comienzo del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: En el código, localiza la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo creo un objeto Documento?

 A: En el paso 4, creará una nueva instancia`Document` objeto utilizando la siguiente línea de código:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### P: ¿Cómo agrego una página al documento?

 A: En el paso 5, agregará una nueva página al documento utilizando el`Add` método de la`Pages` recopilación:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### P: ¿Cómo puedo agregar sangría en las líneas subsiguientes del texto?

 A: En el paso 6, crearás un`TextFragment` objeto y asignarle el texto deseado. Luego, inicializará`TextFormattingOptions` Para el`TextFragment` y especificar el`SubsequentLinesIndent` valor:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### P: ¿Cómo agrego el TextFragment al documento PDF?

 A: En el paso 7, agregarás el`TextFragment` objeto (`text`) a la colección de párrafos de la página:

```csharp
page.Paragraphs.Add(text);
```

#### P: ¿Puedo repetir el proceso para líneas adicionales?

R: Sí, en el paso 8, puede repetir el proceso para líneas adicionales con la misma sangría creando nuevas`TextFragment` objetos y agregarlos a la colección de párrafos de la página.

#### P: ¿Cómo guardo el documento PDF resultante?

 A: Después de agregar el texto con sangría en las líneas subsiguientes, utilice el`Save` método de la`Document` objeto para guardar el documento PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### P: ¿Cuál es la conclusión clave de este tutorial?

R: Si siguió este tutorial, aprendió a mejorar la legibilidad del texto en un documento PDF agregando sangría a las líneas posteriores mediante Aspose.PDF para .NET. Esta técnica puede resultar útil para varios tipos de documentos e informes.