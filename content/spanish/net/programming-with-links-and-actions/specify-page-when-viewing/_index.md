---
title: Especificar la página al visualizarla
linktitle: Especificar la página al visualizarla
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a especificar una página para visualizar en un PDF mediante Aspose.PDF para .NET. Mejore la navegación del usuario con esta sencilla guía.
type: docs
weight: 110
url: /es/net/programming-with-links-and-actions/specify-page-when-viewing/
---
## Introducción

¿Está buscando mejorar sus aplicaciones PDF dirigiendo a los usuarios a páginas específicas al abrir un documento? ¡Ha llegado al lugar correcto! En esta guía, profundizaremos en los detalles del uso de Aspose.PDF para .NET para especificar la página que se debe mostrar cuando se abre un PDF. Esta funcionalidad puede mejorar significativamente la experiencia del usuario, especialmente cuando necesita llamar la atención sobre secciones críticas de su documento.

## Prerrequisitos

Antes de comenzar a codificar, asegurémonos de que tienes todo lo que necesitas para empezar. Esto es lo que necesitarás:

1. Conocimientos básicos de .NET: es fundamental estar familiarizado con el marco .NET. Si te sientes cómodo con C# y tienes conocimientos básicos de programación orientada a objetos, ¡estás listo!

2.  Aspose.PDF para .NET: Necesitará tener la biblioteca Aspose.PDF instalada en su proyecto. Si aún no la ha instalado, puede descargarla[aquí](https://releases.aspose.com/pdf/net/).

3. Visual Studio: este tutorial asume que estás usando Visual Studio como tu IDE. Asegúrate de tenerlo instalado en tu equipo.

4. Un archivo PDF: necesitarás un archivo PDF existente con el que trabajar. Si no tienes uno, puedes crear un documento de muestra o usar cualquier PDF que elijas.

¡Una vez que tengamos estos requisitos previos establecidos, podemos ponernos manos a la obra y empezar a codificar!

## Importar paquetes

Ahora que ya tenemos todo listo, vamos a importar los paquetes necesarios a nuestro proyecto. Siga estos pasos:

### Iniciar Visual Studio

Abra Visual Studio y cree un nuevo proyecto o cargue uno existente donde desee implementar la funcionalidad de visualización de páginas PDF.

### Referencia Aspose.PDF

Para utilizar la biblioteca Aspose.PDF, debe agregarle una referencia:

1. Haga clic derecho en su proyecto en el Explorador de soluciones.
2. Seleccione “Administrar paquetes NuGet”.
3.  Buscar`Aspose.PDF` e instalar el paquete.

### Importar espacios de nombres

Agregue la siguiente directiva using en la parte superior de su archivo de código:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

¡Ahora estás listo para comenzar a construir la lógica de navegación de tu página PDF!

Dividiremos nuestra tarea en pasos manejables. Escribiremos un código que abra un documento PDF, especifique una página en particular que se mostrará al visualizarlo y guarde el documento actualizado. 

## Paso 1: Establezca el directorio del documento

Primero, debes establecer la ruta a tus documentos:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Reemplazar con su directorio
```

 Esta línea es básicamente tu hoja de ruta. Le estás indicando a tu código dónde encontrar el archivo PDF. Asegúrate de reemplazar`YOUR DOCUMENT DIRECTORY` con la ruta actual en su máquina.

## Paso 2: Cargue el archivo PDF

A continuación, cargará el archivo PDF en su aplicación:

```csharp
// Cargar el archivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

 Lo que sucede aquí es que estás creando una nueva instancia de un`Document`objeto mientras especifica la ruta a su archivo PDF. Puede pensar en ello como si estuviera abriendo el libro que acaba de colocar sobre la mesa.

## Paso 3: Acceda a la página deseada

Ahora, accedamos a la página que deseamos mostrar cuando se abra el documento:

```csharp
// Obtener la instancia de la segunda página del documento
Page page2 = doc.Pages[2]; // Recuerde, la indexación comienza en 1
```

Aquí, estamos accediendo a la segunda página de su documento. Vale la pena señalar que la numeración de páginas comienza en 1 en este contexto, por lo que si está pensando en la página 2, debe utilizar un índice de 2.

## Paso 4: Establezca el factor de zoom

Puede ajustar el nivel de zoom de la página que se mostrará:

```csharp
// Crea la variable para establecer el factor de zoom de la página de destino
double zoom = 1; // 1 significa zoom del 100%
```

Establecer un factor de zoom ayuda a determinar qué parte de la página ve el usuario inmediatamente después de abrirla. Un valor de 1 significa que la página se mostrará con un zoom del 100 %, lo que suele ser un buen valor predeterminado.

## Paso 5: Crear la instancia de GoToAction

Pongamos en acción las funciones de navegación:

```csharp
// Crear una instancia de GoToAction
GoToAction action = new GoToAction(doc.Pages[2]); 
```

 En este paso, estás creando una instancia de`GoToAction` que esencialmente representa la acción de navegar a un punto específico en el PDF, en este caso, la segunda página.

## Paso 6: Definir el destino

Ahora, necesitas definir a dónde debe conducir la acción:

```csharp
// Ir a la página 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

Esta línea es como configurar un destino GPS para GoToAction. Le estás indicando que vaya a la página 2 en la parte superior de la página (altura) y en el nivel de zoom especificado.

## Paso 7: Establezca la acción Abrir

Asegurémonos de que esta acción se realice cuando se abre el documento:

```csharp
// Establecer la acción de apertura del documento
doc.OpenAction = action;
```

Con esto, has declarado que cuando se abre tu PDF, se activa la acción de navegación que acabamos de definir. Es como si hubieras colocado el felpudo de bienvenida en la puerta de entrada de tu documento.

## Paso 8: Guarde el documento actualizado

Por último, guardemos el documento con los cambios realizados:

```csharp
// Guardar documento actualizado
doc.Save(dataDir + "goto2page_out.pdf");
```

¡Este paso finaliza tu trabajo! Tendrás un nuevo archivo PDF llamado`goto2page_out.pdf` que se abre directamente a la página que usted especificó.

¡Con esto, la parte de codificación está completa! Has programado con éxito Aspose.PDF para que muestre una página específica cuando se abre un PDF. 

## Conclusión

En esta guía, hemos adoptado un enfoque paso a paso para comprender cómo especificar una página en un archivo PDF mediante Aspose.PDF para .NET. Esta funcionalidad no solo mejora la navegación para los usuarios, sino que también agiliza su interacción con el contenido crucial de sus documentos. Al adoptar estas funciones, está creando una experiencia más sencilla de usar que puede diferenciar sus aplicaciones PDF.

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una biblioteca que permite a los desarrolladores crear, modificar y administrar documentos PDF dentro de aplicaciones .NET.

### ¿Puedo especificar varias páginas para ver?
No, solo puedes configurar el documento para que se abra en una página específica. Sin embargo, puedes crear distintos documentos para distintas páginas iniciales.

### ¿Qué pasa si quiero ver una página con un nivel de zoom diferente?
 Puede cambiar el nivel de zoom ajustando el`zoom` variable antes de guardar el documento.

### ¿Dónde puedo encontrar más ejemplos del uso de Aspose.PDF?
 Puedes comprobarlo[documentación](https://reference.aspose.com/pdf/net/) para más ejemplos y funcionalidades.

### ¿Hay una prueba gratuita disponible para Aspose.PDF para .NET?
 ¡Sí! Puedes descargar una versión de prueba gratuita de Aspose.PDF[aquí](https://releases.aspose.com/).