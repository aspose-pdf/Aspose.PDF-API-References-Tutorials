---
title: Crear rectángulo relleno
linktitle: Crear rectángulo relleno
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear un rectángulo relleno en un PDF con Aspose.PDF para .NET con este tutorial paso a paso. Perfecto para desarrolladores de todos los niveles.
type: docs
weight: 50
url: /es/net/programming-with-graphs/create-filled-rectangle/
---
## Introducción

¿Alguna vez has deseado crear archivos PDF visualmente atractivos mediante programación? Si es así, ¡estás en el lugar correcto! En este tutorial, nos sumergiremos en el mundo de Aspose.PDF para .NET, una potente biblioteca que te permite manipular documentos PDF con facilidad. Hoy, nos centraremos en la creación de un rectángulo relleno dentro de un archivo PDF. Tanto si eres un desarrollador experimentado como si recién estás empezando, esta guía te guiará por cada paso de una manera amena y atractiva. Así que, ¡ponte a programar y comencemos!

## Prerrequisitos

Antes de pasar al código, hay algunas cosas que debes tener en cuenta:

1. Visual Studio: Asegúrate de tener Visual Studio instalado en tu equipo. Es un IDE fantástico para el desarrollo de .NET.
2.  Aspose.PDF para .NET: Deberá descargar e instalar la biblioteca Aspose.PDF. Puede encontrarla[aquí](https://releases.aspose.com/pdf/net/).
3. Conocimientos básicos de C#: un poco de familiaridad con la programación en C# le ayudará a comprender mejor los fragmentos de código.

## Importar paquetes

Para comenzar, debe importar los paquetes necesarios en su proyecto de C#. A continuación, le indicamos cómo hacerlo:

### Crear un nuevo proyecto

Abra Visual Studio y cree un nuevo proyecto de C#. Puede elegir una aplicación de consola para simplificar el proceso.

### Añadir referencia de Aspose.PDF

1. Haga clic derecho en su proyecto en el Explorador de soluciones.
2. Seleccione "Administrar paquetes NuGet".
3. Busque "Aspose.PDF" e instale la última versión.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Ahora que tenemos todo configurado, ¡profundicemos en el código!

## Paso 1: Configurar el directorio de documentos

Lo primero es lo primero: debes especificar la ruta en la que se guardará el PDF. Esto es fundamental porque le indica al programa dónde crear el archivo.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real en su máquina donde desea guardar el PDF.

## Paso 2: Crear una instancia de documento

 A continuación, crearemos una instancia de`Document`Clase. Esta clase representa el documento PDF con el que trabajarás.

```csharp
// Crear instancia de documento
Document doc = new Document();
```

Esta línea inicializa un nuevo documento PDF que podemos manipular.

## Paso 3: Agregar una página al documento

Ahora, agreguemos una página a nuestro documento. Todo PDF necesita al menos una página, ¿no?

```csharp
// Agregar página a la colección de páginas del archivo PDF
Page page = doc.Pages.Add();
```

Este código agrega una nueva página al documento, permitiéndonos dibujar formas en ella.

## Paso 4: Crear una instancia de gráfico

 Para dibujar formas, necesitamos crear una`Graph` Por ejemplo, piense en un gráfico como si fuera un lienzo donde puede dibujar distintas formas.

```csharp
// Crear una instancia de Graph
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Aquí, estamos creando un gráfico con un ancho de 100 y una altura de 400.

## Paso 5: Agrega el gráfico a la página

Ahora que tenemos nuestro gráfico, agreguémoslo a la página que creamos anteriormente.

```csharp
// Agregar objeto gráfico a la colección de párrafos de una instancia de página
page.Paragraphs.Add(graph);
```

Esta línea une el gráfico a la página, preparándolo para dibujar.

## Paso 6: Crear una instancia de rectángulo

A continuación, crearemos un rectángulo que queremos rellenar con color.

```csharp
// Crear una instancia de Rectángulo
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

En este código definimos la posición y el tamaño del rectángulo. Los parámetros representan las coordenadas x e y, el ancho y la altura.

## Paso 7: Especifique el color de relleno

Ahora, elijamos un color para nuestro rectángulo. En este ejemplo, lo rellenaremos con rojo.

```csharp
// Especificar el color de relleno para el objeto gráfico
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Esta línea establece el color de relleno del rectángulo en rojo. ¡Puedes elegir el color que quieras!

## Paso 8: Agrega el rectángulo al gráfico

Con nuestro rectángulo listo, es hora de agregarlo al gráfico.

```csharp
// Agregar objeto rectángulo a la colección de formas del objeto Gráfico
graph.Shapes.Add(rect);
```

Este código agrega el rectángulo al gráfico, haciéndolo parte de nuestro dibujo.

## Paso 9: Guarde el documento PDF

Por último, necesitamos guardar nuestro documento en el directorio especificado.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Guardar archivo PDF
doc.Save(dataDir);
```

 Este código guarda el archivo PDF con el nombre`CreateFilledRectangle_out.pdf` en el directorio que especificó anteriormente.

## Paso 10: Mensaje de confirmación

Para hacernos saber que todo salió bien, podemos imprimir un mensaje de confirmación.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Esta línea generará un mensaje en la consola, confirmando que el rectángulo relleno se ha creado correctamente.

## Conclusión

¡Y ya está! Has creado con éxito un rectángulo relleno en un documento PDF con Aspose.PDF para .NET. Esta potente biblioteca abre un mundo de posibilidades para la manipulación de PDF, lo que te permite crear documentos impresionantes mediante programación. Ya sea que estés generando informes, facturas o cualquier otro tipo de PDF, Aspose.PDF te ayudará.

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una biblioteca que permite a los desarrolladores crear, manipular y convertir documentos PDF mediante programación.

### ¿Puedo utilizar Aspose.PDF gratis?
 Sí, Aspose ofrece una versión de prueba gratuita que puedes usar para explorar las funciones de la biblioteca. Puedes descargarla[aquí](https://releases.aspose.com/).

### ¿Hay alguna forma de obtener soporte para Aspose.PDF?
 ¡Por supuesto! Puedes obtener ayuda a través del foro de Aspose[aquí](https://forum.aspose.com/c/pdf/10).

### ¿Cómo puedo comprar Aspose.PDF?
 Puedes comprar Aspose.PDF visitando la página de compra[aquí](https://purchase.aspose.com/buy).

### ¿Qué tipos de formas puedo crear con Aspose.PDF?
Puede crear varias formas, incluidos rectángulos, círculos, líneas y más, utilizando la biblioteca Aspose.PDF.