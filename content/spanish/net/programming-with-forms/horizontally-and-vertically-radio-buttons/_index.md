---
title: Botones de opción horizontales y verticales
linktitle: Botones de opción horizontales y verticales
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear botones de opción alineados horizontal y verticalmente en PDF usando Aspose.PDF para .NET con este tutorial paso a paso.
type: docs
weight: 180
url: /es/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Introducción

La creación de formularios PDF interactivos puede mejorar significativamente la experiencia del usuario, especialmente cuando se trata de recopilar información. Uno de los elementos de formulario más comunes es el botón de opción, que permite a los usuarios seleccionar una opción de un conjunto. En este tutorial, exploraremos cómo crear botones de opción alineados horizontal y verticalmente con Aspose.PDF para .NET. Ya sea que sea un desarrollador experimentado o recién esté comenzando, esta guía lo guiará a través del proceso paso a paso, lo que le permitirá comprender claramente cada parte.

## Prerrequisitos

Antes de sumergirse en el código, hay algunos requisitos previos que debe tener en cuenta:

1.  Aspose.PDF para .NET: Asegúrese de tener instalada la biblioteca Aspose.PDF. Puede descargarla desde el sitio web[sitio](https://releases.aspose.com/pdf/net/).
2. Visual Studio: un entorno de desarrollo donde puedes escribir y probar tu código.
3. Conocimientos básicos de C#: la familiaridad con la programación en C# le ayudará a comprender mejor los fragmentos de código.

## Importar paquetes

Para comenzar, debe importar los paquetes necesarios en su proyecto de C#. A continuación, le indicamos cómo hacerlo:

### Crear un nuevo proyecto

Abra Visual Studio y cree un nuevo proyecto de C#. Puede elegir una aplicación de consola para simplificar el proceso.

### Añadir referencia de Aspose.PDF

1. Haga clic derecho en su proyecto en el Explorador de soluciones.
2. Seleccione "Administrar paquetes NuGet".
3. Busque "Aspose.PDF" e instale la última versión.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Ahora que tienes todo configurado, vamos a desglosar el código para crear botones de opción alineados horizontal y verticalmente.

## Paso 1: Configurar el directorio de documentos

En este paso definiremos la ruta al directorio donde se almacenarán sus documentos PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde desea guardar el archivo PDF. Esto es crucial, ya que le indica al programa dónde buscar los archivos de entrada y dónde guardar el de salida.

## Paso 2: Cargue el documento PDF existente

 A continuación, debemos cargar el documento PDF con el que trabajaremos. Esto se hace mediante el comando`FormEditor` clase.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Aquí, creamos una instancia de`FormEditor` y vincularlo a un archivo PDF existente llamado`input.pdf`Asegúrese de que este archivo exista en el directorio especificado.

## Paso 3: Configurar las propiedades del botón de opción

Ahora, vamos a configurar algunas propiedades para nuestros botones de opción. Esto incluye el espacio entre los botones, su orientación y su tamaño.

```csharp
formEditor.RadioGap = 4; // Distancia entre las opciones de los botones de opción
formEditor.RadioHoriz = true; // Establecer como verdadero para la alineación horizontal
formEditor.RadioButtonItemSize = 20; // Tamaño del botón de opción
formEditor.Facade.BorderWidth = 1; // Ancho del borde
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Color del borde
```

 Estas propiedades ayudarán a definir cómo aparecerán los botones de opción en el PDF.`RadioGap` La propiedad controla el espacio entre los botones, mientras que`RadioHoriz` determina su diseño.

## Paso 4: Agregar botones de opción horizontales

Ahora, agreguemos los botones de opción horizontales al PDF.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 En este código, definimos los elementos para los botones de opción y los agregamos al PDF.`AddField`El método toma varios parámetros, incluido el tipo de campo, el nombre del campo y las coordenadas para la ubicación.

## Paso 5: Agregar botones de opción verticales

A continuación, agregaremos los botones de opción verticales. Para ello, debemos volver a cambiar la orientación a vertical.

```csharp
formEditor.RadioHoriz = false; // Establecer como falso para la alineación vertical
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Al igual que antes, definimos los elementos y los agregamos al PDF, pero esta vez estarán alineados verticalmente.

## Paso 6: Guarde el documento PDF

Por último, necesitamos guardar el documento PDF modificado.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Este código guarda el PDF con los botones de opción recién agregados. Asegúrese de verificar el directorio especificado para el archivo de salida.

## Conclusión

Crear botones de opción en un PDF con Aspose.PDF para .NET es un proceso sencillo. Si sigue los pasos que se describen en este tutorial, podrá agregar fácilmente botones de opción alineados tanto horizontal como verticalmente a sus formularios PDF. Esto no solo mejora la interactividad de sus documentos, sino que también mejora la experiencia general del usuario. ¡Así que, adelante y pruébelo!

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, manipular y convertir documentos PDF mediante programación.

### ¿Puedo utilizar Aspose.PDF gratis?
 Sí, Aspose ofrece una versión de prueba gratuita que puedes usar para evaluar la biblioteca. Puedes descargarla[aquí](https://releases.aspose.com/).

### ¿Cómo puedo obtener soporte para Aspose.PDF?
 Puede obtener ayuda visitando el sitio[Foro de Aspose](https://forum.aspose.com/c/pdf/10).

### ¿Es posible crear otros elementos de formulario con Aspose.PDF?
¡Por supuesto! Aspose.PDF admite varios elementos de formulario, incluidos campos de texto, casillas de verificación y menús desplegables.

### ¿Dónde puedo comprar Aspose.PDF para .NET?
 Puede comprar Aspose.PDF para .NET desde[Página de compra](https://purchase.aspose.com/buy).