---
title: Buscar texto y dibujar rectángulo
linktitle: Buscar texto y dibujar rectángulo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a buscar texto en archivos PDF y a resaltarlo con rectángulos usando Aspose.PDF para .NET. Tutorial sencillo paso a paso para mejorar sus habilidades de manipulación de archivos PDF.
type: docs
weight: 460
url: /es/net/programming-with-text/search-text-and-draw-rectangle/
---
## Introducción

¿Está buscando mejorar sus habilidades de manipulación de PDF? ¿Quiere aprender a buscar texto específico en archivos PDF y resaltarlo con un rectángulo? ¡Ha encontrado la guía perfecta! Hoy le mostraré cómo usar Aspose.PDF para .NET para buscar texto en un documento PDF y dibujar rectángulos a su alrededor. Este artículo le proporcionará un tutorial paso a paso diseñado con claridad y utilidad en mente, lo que le garantizará que pueda seguir y aplicar estas técnicas a sus proyectos. 

## Prerrequisitos

Antes de sumergirnos en el tutorial, preparemos lo necesario para garantizar un flujo de trabajo fluido:

1. Comprensión básica de .NET: debe estar familiarizado con la programación en C# y el marco .NET para seguir este tutorial de manera efectiva.
   
2. Visual Studio instalado: necesitará un entorno de desarrollo integrado (IDE) para escribir y probar su código. Visual Studio Community es una excelente opción y es gratis.
   
3. Aspose.PDF para .NET: Necesita tener la biblioteca Aspose.PDF instalada en su proyecto. Puede descargarla[aquí](https://releases.aspose.com/pdf/net/) o considere una[licencia temporal](https://purchase.aspose.com/temporary-license/) para funciones ampliadas.
   
4.  Documento PDF de muestra: para este tutorial, necesitará un archivo PDF de muestra llamado`SearchAndGetTextFromAll.pdf` almacenado en el directorio de su proyecto. 

## Importar paquetes

Para comenzar, primero deberá importar los paquetes necesarios a su proyecto .NET. Siga estos pasos:

### Abra Visual Studio

Inicie Visual Studio y cree una nueva aplicación de consola o utilice una existente donde desee implementar las funcionalidades de PDF.

### Agregue Aspose.PDF a su proyecto

1. Haga clic derecho en su proyecto en el Explorador de soluciones.
2. Seleccione "Administrar paquetes NuGet".
3.  Buscar`Aspose.PDF` e instalar la última versión.

Al hacer esto, estás sentando las bases para todas las increíbles manipulaciones de PDF que estás a punto de realizar.

## Importar espacios de nombres

En la parte superior del archivo de programa, querrás importar los espacios de nombres relevantes de la biblioteca Aspose:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Esto facilita el acceso a las clases y métodos dentro de la biblioteca Aspose.PDF para sus tareas.


Ahora que tiene todo configurado, desglosemos el proceso de búsqueda de texto en un PDF y dibujo de un rectángulo a su alrededor en pasos manejables.

## Paso 1: Establezca la ruta para su documento

 En primer lugar, establezca la ruta de su archivo PDF. Asegúrese de reemplazar`YOUR DOCUMENT DIRECTORY` con la ruta real donde se encuentra`SearchAndGetTextFromAll.pdf` se almacena.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 A continuación, cree una instancia de la`Document` clase para cargar tu PDF:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Esta línea de código abre el archivo PDF especificado, lo que le permite manipularlo más.

## Paso 3: Crea un absorbente de texto

 Ahora, necesitará una forma de buscar texto dentro de ese documento. Para ello, utilizamos el`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 La expresión regular`@"[\S]+"` está diseñado para coincidir con cualquier cadena que no contenga espacios en blanco en el PDF. 

## Paso 4: Configurar las opciones de búsqueda de texto

A continuación, debes configurar las opciones de búsqueda de texto:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Aquí, el`true` El parámetro significa que la búsqueda distinguirá entre mayúsculas y minúsculas. Puedes configurarlo como`false` Si desea una búsqueda que no distinga entre mayúsculas y minúsculas.

## Paso 5: Acepte el Absorbedor de Texto en el Documento

 Con tu`TextFragmentAbsorber` y con las opciones de búsqueda listas, es hora de absorber el texto del documento:

```csharp
document.Pages.Accept(textAbsorber);
```

Este método examina cada página de su PDF para encontrar fragmentos de texto que coincidan con el patrón especificado.

## Paso 6: Crear un PdfContentEditor

 Para dibujar formas en el documento, necesitarás el`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Este editor le permite manipular y editar el contenido PDF fácilmente.

## Paso 7: Recorrer los fragmentos de texto encontrados

Ahora, querrás recorrer los fragmentos de texto encontrados para dibujar rectángulos alrededor de ellos:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Este bucle itera sobre cada fragmento de texto y sus segmentos, llamando a un`DrawBox` Método para dibujar rectángulos.

## Paso 8: Definir el método DrawBox

 Es necesario definir el`DrawBox` Método que se encargará de la lógica de dibujo del rectángulo. Aquí hay una implementación simple:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Calcular las dimensiones del rectángulo en función del segmento de texto
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Dibuje un rectángulo utilizando los valores calculados
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Este método determina la posición y el tamaño del rectángulo en función del rectángulo delimitador del segmento y utiliza el editor para dibujarlo.

## Paso 9: Guardar el documento modificado

Después de dibujar los rectángulos alrededor del texto encontrado, puedes guardar el documento modificado:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Asegúrese de que su nuevo archivo se guarde con un nombre distinto para evitar sobrescribir su documento original.

## Paso 10: Mensaje de confirmación

Por último, imprima un mensaje de confirmación en la consola para informarle que la operación fue exitosa:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

¡Y ya lo tienes! Has creado con éxito un script para buscar texto en un PDF y resaltarlo con rectángulos.

## Conclusión

¡Felicitaciones! Acaba de desbloquear una poderosa habilidad que puede mejorar enormemente sus capacidades de manipulación de PDF con Aspose.PDF para .NET. Con solo unos pocos pasos simples, puede buscar cualquier texto en su documento y resaltarlo visualmente, lo que hará que sus documentos PDF sean más interactivos y manejables. ¡No dude en experimentar con diferentes patrones de expresiones regulares y opciones de color para personalizar esta herramienta!

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una biblioteca que proporciona una forma integral de crear, manipular y convertir documentos PDF mediante programación.

### ¿Puedo utilizar Aspose.PDF gratis?
Sí, Aspose ofrece una versión de prueba gratuita que puedes usar para probar las funcionalidades de la biblioteca. Échale un vistazo[aquí](https://releases.aspose.com/).

### ¿Qué lenguaje de programación necesito utilizar con Aspose.PDF para .NET?
Aspose.PDF para .NET está diseñado para usarse con C# y otros lenguajes .NET.

### ¿Cómo puedo obtener ayuda con Aspose.PDF?
 Puede visitar el foro de soporte de Aspose para obtener ayuda con cualquier problema o consulta que pueda tener. Encuentre ayuda[aquí](https://forum.aspose.com/c/pdf/10).

### ¿Dónde puedo descargar Aspose.PDF para .NET?
 Puede descargar la biblioteca desde el sitio web de Aspose,[aquí](https://releases.aspose.com/pdf/net/).