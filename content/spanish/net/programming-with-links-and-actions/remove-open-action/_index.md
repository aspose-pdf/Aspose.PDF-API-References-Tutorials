---
title: Eliminar acción abierta
linktitle: Eliminar acción abierta
second_title: Referencia de API de Aspose.PDF para .NET
description: ¡Elimine fácilmente acciones abiertas de archivos PDF con Aspose.PDF para .NET! Un sencillo tutorial con instrucciones paso a paso para una gestión eficaz de archivos PDF.
type: docs
weight: 80
url: /es/net/programming-with-links-and-actions/remove-open-action/
---
## Introducción

En este tutorial, repasaremos los sencillos pasos necesarios para eliminar una acción de apertura de un documento PDF con Aspose.PDF para .NET. Te sorprenderá lo sencillo que es y, al final, te sentirás como un profesional del PDF. Vamos a profundizar en los requisitos previos.

## Prerrequisitos

Antes de comenzar, necesitarás tener un par de cosas en cuenta:

1. Comprensión básica de C#: la familiaridad con el lenguaje de programación C# le ayudará a navegar por los fragmentos de código con facilidad.
2. Visual Studio: asegúrese de tener instalado Visual Studio. Es el IDE más común para el desarrollo de .NET.
3.  Aspose.PDF para .NET: Necesitará tener esta biblioteca a mano. Puede descargarla[aquí](https://releases.aspose.com/pdf/net/). 
4. .NET Framework: asegúrese de haber configurado su proyecto para usar .NET Framework (se recomienda la versión 4.0 o posterior).
5. Un archivo PDF con acciones abiertas: este es el documento en el que trabajaremos. Puedes crear uno o descargar una muestra para practicar.

Una vez que tengas cubiertas estas bases, ¡estarás listo para comenzar! Ahora, importemos los paquetes necesarios para comenzar a codificar.

## Importar paquetes

Para comenzar a codificar, deberá incluir algunos paquetes esenciales en su proyecto. De esta manera, establecerá las bases para las operaciones que realizará en los archivos PDF. Esto es lo que debe hacer:

### Abra su proyecto

Abra su proyecto .NET en Visual Studio donde desea realizar las operaciones.

### Agregar biblioteca Aspose.PDF

Necesitará agregar la biblioteca Aspose.PDF a su proyecto. Puede hacerlo fácilmente a través del Administrador de paquetes NuGet. Simplemente busque Aspose.PDF e instale la última versión estable.

### Incluir espacios de nombres necesarios

En la parte superior del archivo C#, debes importar el espacio de nombres Aspose.PDF. Esto permite que tu código sepa que vas a trabajar con las funcionalidades PDF que ofrece Aspose. Esto es lo que debes agregar:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Ahora que ya está todo configurado y listo, veamos los detalles de cómo eliminar las acciones abiertas de un documento PDF.

## Paso 1: Definir el directorio del documento

En primer lugar, debe especificar dónde se encuentra su archivo PDF. Piense en esto como si estuviera configurando su espacio de trabajo. A continuación, le indicamos cómo hacerlo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Asegúrese de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta actual donde se almacena el PDF. Por ejemplo:

```csharp
string dataDir = "C:\\Documents\\";
```

Esto prepara el terreno para los siguientes pasos. 

## Paso 2: Abra el documento PDF

A continuación, carguemos el documento PDF en su aplicación. ¡Aquí es donde comienza a suceder la magia! Utilice el siguiente código:

```csharp
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

 En este paso, le decimos a nuestra aplicación que cree un nuevo`Document` objeto, que representa el archivo PDF denominado "RemoveOpenAction.pdf". ¡Asegúrese de que este archivo exista en el directorio especificado!

## Paso 3: Eliminar la acción abierta

Ahora viene la parte interesante: eliminar la acción de abrir del documento. Puedes hacerlo con una sola línea de código. A continuación, te indicamos cómo:

```csharp
document.OpenAction = null;
```

Esta línea básicamente le dice al documento que ya no hay un conjunto de acciones abierto. ¡Es como darle un nuevo comienzo a tu PDF justo antes de guardarlo!

## Paso 4: Guarde el documento actualizado

Una vez que hayas eliminado la acción de abrir, deberás guardar los cambios. A continuación, te indicamos cómo guardar el documento actualizado en tu directorio:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document.Save(dataDir);
```

Este código guardará el documento modificado como "RemoveOpenAction_out.pdf" en el mismo directorio. Básicamente, habrá creado una nueva versión de su PDF libre de acciones no deseadas.

## Paso 5: Confirmar el éxito

Para que todos sepan que la operación se realizó correctamente, es posible que desee imprimir un mensaje de confirmación en la consola. Simplemente agregue la siguiente línea para finalizar el proceso:

```csharp
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir);
```

Este paso no es estrictamente necesario, pero es bueno tener un cierre después de ejecutar las operaciones. ¡Lo lograste! Eliminaste con éxito la acción de abrir de un documento PDF.

## Conclusión

¡Y ya está! Con solo unas pocas líneas de código C# y la potencia de Aspose.PDF para .NET, ha optimizado su PDF eliminando una acción de apertura. La gestión de documentos no tiene por qué ser tan complicada como parece. Si domina herramientas como Aspose, podrá hacerse cargo de sus archivos PDF y hacer que trabajen más para usted, no al revés.

## Preguntas frecuentes

### ¿Qué son las acciones de apertura en archivos PDF?
Las acciones de apertura son comandos que se ejecutan cuando se abre un PDF, como reproducir un sonido o navegar a una página web.

### ¿Debo pagar por Aspose.PDF para .NET?
 Aspose ofrece una versión de prueba gratuita. Puedes descargarla[aquí](https://releases.aspose.com/).

### ¿Puedo eliminar varias acciones abiertas de un PDF?
 Sí, puedes configurar el`OpenAction` propiedad a`null` para eliminar todas las acciones abiertas.

### ¿Cómo puedo probar si la eliminación de la acción abierta funcionó?
Abra el archivo PDF guardado y verifique si se han realizado las acciones configuradas previamente. Si no es así, ¡lo logró!

### ¿Dónde puedo encontrar ayuda si tengo algún problema?
 Visite el foro de Aspose para obtener ayuda sobre problemas relacionados con PDF[aquí](https://forum.aspose.com/c/pdf/10).