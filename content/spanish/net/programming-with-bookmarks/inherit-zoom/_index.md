---
title: Heredar zoom en archivo PDF
linktitle: Heredar zoom en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a heredar el zoom en archivos PDF con Aspose.PDF para .NET con esta guía paso a paso. Mejore su experiencia de visualización de archivos PDF.
type: docs
weight: 90
url: /es/net/programming-with-bookmarks/inherit-zoom/
---
## Introducción

¿Alguna vez ha abierto un archivo PDF y se ha dado cuenta de que el nivel de zoom no es el correcto? Puede resultar frustrante, especialmente cuando intenta centrarse en un contenido específico. Por suerte, con Aspose.PDF para .NET, puede establecer fácilmente un nivel de zoom predeterminado para sus documentos PDF. Esta guía le guiará por el proceso paso a paso, garantizando que sus lectores tengan la mejor experiencia posible al ver sus archivos PDF. Así que, ¡coja su sombrero de codificador y comencemos!

## Prerrequisitos

Antes de comenzar, hay algunas cosas que debes tener en cuenta:

1. Visual Studio: Asegúrate de tener Visual Studio instalado en tu equipo. Es el mejor entorno para el desarrollo de .NET.
2.  Aspose.PDF para .NET: Deberá descargar e instalar la biblioteca Aspose.PDF. Puede encontrarla[aquí](https://releases.aspose.com/pdf/net/).
3. Conocimientos básicos de C#: la familiaridad con la programación en C# le ayudará a comprender mejor los fragmentos de código.

## Importar paquetes

Para comenzar, debes importar los paquetes necesarios a tu proyecto. Puedes hacerlo de la siguiente manera:

### Crear un nuevo proyecto

Abra Visual Studio y cree un nuevo proyecto de C#. Puede elegir una aplicación de consola para simplificar el proceso.

### Añadir referencia de Aspose.PDF

1. Haga clic derecho en su proyecto en el Explorador de soluciones.
2. Seleccione "Administrar paquetes NuGet".
3. Busque "Aspose.PDF" e instale la última versión.

### Importar el espacio de nombres

En la parte superior de su archivo C#, importe el espacio de nombres Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

¡Ahora que ya tienes todo configurado, pasemos a la codificación real!

## Paso 1: Definir el directorio del documento

Lo primero es lo primero: debes especificar la ruta del directorio de tus documentos. Aquí es donde se ubicará el archivo PDF de entrada y donde se guardará el archivo de salida.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Abra el documento PDF

 A continuación, deberá abrir el documento PDF que desea modificar. Esto se hace mediante el botón`Document` clase de la biblioteca Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 3: Acceda a la colección de esquemas/marcadores

Ahora, vayamos al meollo del asunto: los contornos o marcadores del PDF. Se trata de los elementos de navegación que permiten a los usuarios saltar a secciones específicas del documento.

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Paso 4: Establezca el nivel de zoom

 ¡Aquí es donde ocurre la magia! Puedes configurar el nivel de zoom usando el`XYZExplicitDestination` Clase. En este ejemplo, estableceremos el nivel de zoom en 0, lo que significa que el documento heredará el nivel de zoom del visor.

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Paso 5: Agregar la acción a la colección de contornos

Ahora que ya tienes establecido tu destino, es momento de agregar esta acción a la colección de contornos del PDF.

```csharp
item.Action = new GoToAction(dest);
```

## Paso 6: Agrega el elemento a la colección Outlines

A continuación, deberá agregar el elemento a la colección de contornos del archivo PDF. Este paso garantiza que se guarden los cambios.

```csharp
doc.Outlines.Add(item);
```

## Paso 7: Guardar el PDF de salida

Por último, debes guardar el documento PDF modificado. Especifica la ruta en la que deseas guardar el nuevo archivo.

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

## Paso 8: Confirmar la actualización

Para finalizar, imprimamos un mensaje de confirmación en la consola para informarnos que todo salió bien.

```csharp
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusión

¡Y ya está! Has heredado con éxito el nivel de zoom en tus archivos PDF usando Aspose.PDF para .NET. Esta sencilla pero potente función puede mejorar enormemente la experiencia del usuario, haciendo que tus documentos sean más accesibles y fáciles de navegar. Así que, la próxima vez que crees un PDF, ¡recuerda configurar ese nivel de zoom!

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, manipular y convertir documentos PDF mediante programación.

### ¿Puedo utilizar Aspose.PDF gratis?
 Sí, Aspose ofrece una versión de prueba gratuita que puedes usar para probar la biblioteca. Puedes descargarla[aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar la documentación?
 Puede encontrar la documentación de Aspose.PDF para .NET[aquí](https://reference.aspose.com/pdf/net/).

### ¿Cómo compro una licencia?
 Puedes comprar una licencia para Aspose.PDF para .NET[aquí](https://purchase.aspose.com/buy).

### ¿Qué pasa si necesito ayuda?
 Si necesita ayuda, puede visitar el foro de soporte de Aspose[aquí](https://forum.aspose.com/c/pdf/10).