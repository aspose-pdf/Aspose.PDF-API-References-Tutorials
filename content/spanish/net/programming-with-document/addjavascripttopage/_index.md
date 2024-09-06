---
title: Agregar Java Script a un archivo PDF
linktitle: Agregar archivo PDF de Java Script
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar JavaScript a un archivo PDF con Aspose.PDF para .NET. Guía paso a paso con tutoriales de código para la creación de scripts a nivel de documento y página.
type: docs
weight: 10
url: /es/net/programming-with-document/addjavascripttopage/
---
## Introducción

¿Alguna vez se preguntó cómo mejorar sus archivos PDF con elementos interactivos como alertas emergentes o funciones de impresión automática? ¡Buenas noticias! ¡Puede hacerlo! Al usar Aspose.PDF para .NET, puede agregar JavaScript a sus documentos PDF sin problemas. Ya sea que esté automatizando tareas o creando experiencias de usuario dinámicas, la incorporación de JavaScript en archivos PDF le brinda a sus archivos un nivel adicional de funcionalidad.

## Prerrequisitos

Antes de pasar a la parte de codificación, hay algunas cosas que deberás tener configuradas:

-  Aspose.PDF para .NET: Descargue la biblioteca desde[Comunicados de Aspose](https://releases.aspose.com/pdf/net/) o conseguir uno[prueba gratis](https://releases.aspose.com/).
- Entorno de desarrollo: cualquier IDE compatible con .NET como Visual Studio.
- Conocimientos básicos de C#: esta guía asume que está familiarizado con la sintaxis básica de C#.
-  Licencia Temporal (Opcional): Puedes obtener una[licencia temporal](https://purchase.aspose.com/temporary-license/) Si quieres evitar limitaciones durante tu desarrollo.

## Importar paquetes

Antes de comenzar a escribir código, deberá importar los espacios de nombres necesarios de la biblioteca Aspose.PDF. Estos espacios de nombres le permitirán manipular archivos PDF y agregar acciones de JavaScript fácilmente.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Ahora que ha importado los espacios de nombres correctos, está todo listo para comenzar a codificar.

## Paso 1: Cargue un PDF existente

Lo primero es lo primero: debes cargar el documento PDF al que quieres añadir JavaScript. Este paso prepara el terreno para todas las modificaciones posteriores. Imagina que tienes un PDF que quieres mejorar con funciones dinámicas, como imprimir el documento automáticamente al abrirlo.

Aquí le mostramos cómo puede cargar ese archivo PDF:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar un archivo PDF existente
Document doc = new Document(dataDir + "input.pdf");
```

 En este fragmento de código, usamos el`Document` clase para cargar un archivo PDF existente desde el directorio especificado. Asegúrese de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su archivo PDF.

## Paso 2: Agregar JavaScript a nivel de documento

Ahora, agreguemos algo de código JavaScript que se activará cuando se abra el documento. En este ejemplo, escribiremos un script que abra el cuadro de diálogo de impresión tan pronto como el usuario abra el PDF.

El código JavaScript a nivel de documento es perfecto para las acciones que desea aplicar a todo el PDF. Piense en ello como si estuviera configurando una regla global para su documento.

Aquí está el código:

```csharp
// Cómo agregar JavaScript a nivel de documento
// Crear una instancia de JavascriptAction con la declaración de JavaScript deseada
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Asignar objeto JavascriptAction a OpenAction del documento
doc.OpenAction = javaScript;
```

 En este paso, creamos un`JavascriptAction` objeto que define una función de JavaScript para abrir el cuadro de diálogo de impresión cuando se abre el documento.`doc.OpenAction` A continuación, a la propiedad se le asigna esta acción de JavaScript.

## Paso 3: Agregar JavaScript a nivel de página

No todas las acciones tienen por qué afectar a todo el documento. A veces, es necesario que se realicen acciones específicas cuando se abren o cierran determinadas páginas. Aquí, configuraremos acciones de JavaScript para cuando se abre y se cierra una página en particular (por ejemplo, la página 2).

El código JavaScript a nivel de página es útil para interacciones específicas. Puede ser cualquier cosa, desde mostrar un mensaje cuando un usuario navega a una página hasta acciones personalizadas, como el llenado automático de campos de formulario.

Aquí te explicamos cómo hacerlo:

```csharp
// Cómo agregar JavaScript a nivel de página
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

En este fragmento de código, agregamos dos acciones de JavaScript:
1. Acción OnOpen: muestra una alerta que dice “Página 2 abierta” cuando el usuario abre la página 2.
2. Acción OnClose: muestra una alerta que dice “Página 2 cerrada” cuando el usuario sale de la página 2.

Esto añade una capa de interactividad a su PDF. Imagine guiar al usuario a través de una serie de pasos en diferentes páginas, con alertas que aparecen cuando ingresa o sale de una página.

## Paso 4: Guarde el documento PDF

Ya ha añadido JavaScript tanto al documento como a las páginas específicas. El paso final es guardar el PDF modificado en la ubicación deseada. Esta parte es sencilla pero crucial: ¡no olvide guardar su trabajo!

Aquí está el código:

```csharp
// Especifique la ruta del archivo de salida
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Guardar el documento PDF actualizado
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 En este fragmento, guardamos el documento actualizado con el JavaScript agregado en un nuevo archivo llamado`"JavaScript-Added_out.pdf"`Esto garantiza que no sobrescriba el archivo original y le brinda una copia de seguridad con la que trabajar.

## Conclusión

Agregar JavaScript a archivos PDF con Aspose.PDF para .NET es una forma eficaz de crear archivos PDF interactivos y dinámicos. Ya sea que esté automatizando tareas como la impresión o creando alertas personalizadas, la capacidad de incorporar JavaScript en sus archivos PDF hace que sus documentos sean más atractivos y funcionales.

## Preguntas frecuentes

### ¿Puedo agregar múltiples acciones de JavaScript a diferentes páginas de un PDF?
Sí, puedes asignar diferentes acciones de JavaScript a páginas individuales o a todo el documento.

### ¿Es posible eliminar JavaScript de un PDF después de agregarlo?
Sí, puedes eliminar o modificar acciones de JavaScript existentes borrando la casilla`Actions` Propiedades del documento o página.

### ¿Qué tipo de funciones de JavaScript puedo utilizar en un PDF?
Puede utilizar cualquier JavaScript compatible con el motor JavaScript de Adobe Acrobat, como impresión, alertas y manipulaciones de formularios.

### ¿Funciona JavaScript en todos los visores de PDF?
La mayoría de las acciones de JavaScript funcionarán en visores de PDF que admitan archivos PDF interactivos, como Adobe Acrobat. Sin embargo, es posible que algunos lectores de PDF básicos no admitan JavaScript.

### ¿Puedo activar acciones de JavaScript en función de la entrada del usuario en el PDF?
Sí, puedes vincular JavaScript a los campos de formulario para activar acciones en función de la entrada del usuario.