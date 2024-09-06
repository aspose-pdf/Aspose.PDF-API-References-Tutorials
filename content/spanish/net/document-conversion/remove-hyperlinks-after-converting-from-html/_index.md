---
title: Eliminar hipervínculos después de convertir desde HTML
linktitle: Eliminar hipervínculos después de convertir desde HTML
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar hipervínculos de documentos HTML después de convertirlos a PDF usando Aspose.PDF para .NET en esta guía paso a paso.
type: docs
weight: 250
url: /es/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Introducción

En la era digital, convertir documentos HTML a PDF es una tarea habitual. Sin embargo, a veces es posible que desee eliminar hipervínculos del PDF convertido por diversos motivos, como mejorar la legibilidad o evitar la navegación no deseada. En este tutorial, exploraremos cómo lograr esto utilizando Aspose.PDF para .NET. 

## Prerrequisitos

Antes de sumergirse en el código, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio: Asegúrate de tener Visual Studio instalado en tu equipo. Este será tu entorno de desarrollo.
2.  Aspose.PDF para .NET: Necesita tener la biblioteca Aspose.PDF. Puede descargarla desde[aquí](https://releases.aspose.com/pdf/net/).
3. Conocimientos básicos de C#: La familiaridad con la programación en C# le ayudará a comprender mejor el código.

## Importar paquetes

Para comenzar, debe importar los paquetes necesarios en su proyecto de C#. A continuación, le indicamos cómo hacerlo:

1. Abra su proyecto de Visual Studio.
2. Haga clic derecho en su proyecto en el Explorador de soluciones y seleccione "Administrar paquetes NuGet".
3.  Buscar`Aspose.PDF` e instalarlo.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Ahora que tiene todo configurado, analicemos el proceso de eliminación de hipervínculos de un archivo HTML después de convertirlo a PDF.

## Paso 1: Configurar el directorio de documentos

Lo primero es lo primero: debes especificar la ruta del directorio de tus documentos. Aquí es donde se encuentra tu archivo HTML y donde se guardará el PDF resultante.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde se almacena su archivo HTML.

## Paso 2: Cargar el documento HTML

 A continuación, cargará el documento HTML utilizando el`Document` Clase de Aspose.PDF. Esta clase le permite trabajar con documentos PDF fácilmente.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Aquí, estamos cargando el archivo HTML llamado`SampleHtmlFile.html`Asegúrese de que este archivo exista en el directorio especificado.

## Paso 3: Guardar el documento en Memory Stream

Antes de comenzar a procesar las anotaciones, debemos guardar el documento en un flujo de memoria. Este paso es crucial, ya que prepara el documento para su posterior manipulación.

```csharp
doc.Save(new MemoryStream());
```

Esta línea guarda el documento en la memoria, lo que nos permite trabajar con él sin escribirlo todavía en el disco.

## Paso 4: Iterar a través de las anotaciones

Ahora, repasaremos las anotaciones del documento. Las anotaciones son elementos como enlaces, comentarios y resaltados. Nos interesan especialmente las anotaciones de enlaces.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Procesar la anotación del enlace
    }
}
```

En este bucle, verificamos si el tipo de anotación es un enlace. Si lo es, procedemos a los siguientes pasos.

## Paso 5: Eliminar la acción de hipervínculo

Para cada anotación de enlace, debemos verificar si tiene una acción de hipervínculo. Si la tiene, eliminaremos el hipervínculo estableciendo su URI en una cadena vacía.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Este fragmento de código garantiza que la acción del hipervínculo se elimine de manera efectiva.

## Paso 6: Absorber fragmentos de texto

A continuación, absorberemos los fragmentos de texto asociados a la anotación del enlace. Esto nos permite manipular la apariencia del texto.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Aquí creamos un`TextFragmentAbsorber` y configure sus opciones de búsqueda en el rectángulo de la anotación. Esto nos ayuda a encontrar el texto vinculado.

## Paso 7: Modificar la apariencia del texto

Una vez que tengamos los fragmentos de texto, podemos modificar su apariencia. En este caso, eliminaremos el subrayado y cambiaremos el color del texto a negro.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Este paso mejora la legibilidad del texto al eliminar el estilo de hipervínculo.

## Paso 8: Eliminar la anotación

Después de modificar el texto, podemos eliminar de forma segura la anotación del enlace del documento.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Esta línea elimina el hipervínculo del PDF, garantizando que ya no exista en el resultado final.

## Paso 9: Guardar el documento modificado

Por último, debemos guardar el documento modificado en un nuevo archivo PDF. Este es el último paso de nuestro proceso.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Esta línea guarda el documento con los hipervínculos eliminados, creando un nuevo archivo PDF llamado`RemoveHyperlinksFromText_out.pdf`.

## Conclusión

¡Y ya está! Has eliminado con éxito los hipervínculos de un documento HTML después de convertirlo a PDF con Aspose.PDF para .NET. Este proceso no solo mejora la legibilidad de tu PDF, sino que también te da control sobre el contenido que presentas. 

## Preguntas frecuentes

### ¿Puedo eliminar hipervínculos de cualquier documento PDF?
Sí, puede eliminar hipervínculos de cualquier documento PDF utilizando Aspose.PDF para .NET.

### ¿Aspose.PDF es de uso gratuito?
 Aspose.PDF ofrece una versión de prueba gratuita, pero para obtener todas las funciones, debe comprar una licencia.[página de compra](https://purchase.aspose.com/buy).

### ¿Qué pasa si encuentro problemas al utilizar Aspose.PDF?
 Puedes buscar ayuda en el[foro de soporte](https://forum.aspose.com/c/pdf/10).

### ¿Puedo convertir otros formatos de archivos a PDF usando Aspose?
Sí, Aspose admite varios formatos de archivos para la conversión a PDF.

### ¿Dónde puedo descargar Aspose.PDF para .NET?
 Puedes descargarlo desde[enlace de descarga](https://releases.aspose.com/pdf/net/).