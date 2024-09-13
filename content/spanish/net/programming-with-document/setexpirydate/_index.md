---
title: Establecer fecha de caducidad en archivo PDF
linktitle: Establecer fecha de caducidad en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a establecer una fecha de vencimiento en archivos PDF con Aspose.PDF para .NET. Mejore la seguridad de los documentos con esta guía paso a paso.
type: docs
weight: 300
url: /es/net/programming-with-document/setexpirydate/
---
## Introducción

En la era digital actual, gestionar y proteger documentos es más importante que nunca. Imagina enviar un PDF que se vuelve automáticamente inaccesible después de una fecha determinada. Suena a magia, ¿verdad? Pues bien, con Aspose.PDF para .NET, puedes establecer fácilmente una fecha de caducidad para tus archivos PDF. Esta función es especialmente útil para documentos confidenciales que deben restringirse después de un período determinado. En este tutorial, te guiaremos paso a paso por el proceso de establecer una fecha de caducidad en un archivo PDF. Así que, ¡ponte a programar y manos a la obra!

## Prerrequisitos

Antes de comenzar, hay algunas cosas que debes tener en cuenta:

1. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo .NET. Puede ser Visual Studio o cualquier otro IDE que admita .NET.
2.  Aspose.PDF para .NET: Es necesario tener instalada la biblioteca Aspose.PDF. Si aún no lo ha hecho, puede descargarla desde[aquí](https://releases.aspose.com/pdf/net/).
3. Conocimientos básicos de C#: este tutorial supone que tienes conocimientos básicos de programación en C#. Si eres nuevo en C#, ¡no te preocupes! Lo haremos de forma sencilla y directa.

## Importar paquetes

Para comenzar a utilizar Aspose.PDF, debe importar los espacios de nombres necesarios en su proyecto de C#. Puede hacerlo de la siguiente manera:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Estos espacios de nombres le brindan acceso a las funcionalidades principales necesarias para trabajar con documentos PDF en Aspose.PDF.

## Paso 1: Configurar el directorio de documentos

Lo primero es lo primero: debes especificar la ruta del directorio de tus documentos. Aquí es donde se guardará el PDF resultante. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde desea guardar su archivo PDF. Es como decirle a su programa: "¡Oye, aquí es donde guardo mis archivos!"

## Paso 2: Crear una instancia del objeto de documento

 A continuación, debe crear una nueva instancia del`Document` Clase. Este es tu lienzo donde crearás tu PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Piensa en el`Document` objeto como una hoja de papel en blanco. ¡Puedes agregarle contenido como quieras!

## Paso 3: Agregar una página al PDF

Ahora que ya tienes tu documento configurado, es momento de agregarle una página. Aquí es donde irá tu contenido.

```csharp
doc.Pages.Add();
```

Acabas de crear una nueva página en tu PDF. Es como agregar una nueva página en tu cuaderno donde puedes anotar tus pensamientos.

## Paso 4: Agregar texto a la página

Hagamos que esta página sea un poco más interesante agregando algo de texto. Agregaremos un mensaje simple que diga "Hola mundo".

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Esta línea de código agrega un fragmento de texto a la primera página de tu PDF. ¡Es como escribir un título en la parte superior de la página!

## Paso 5: Crear JavaScript para la fecha de caducidad

Ahora viene la parte divertida. Crearás una acción de JavaScript que comprobará la fecha de caducidad del PDF. Si la fecha actual supera la fecha de caducidad, un mensaje alertará al usuario.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Esto es lo que está pasando:
- Usted define el año y mes de vencimiento.
- Obtendrás la fecha de hoy.
- Compara la fecha de hoy con la fecha de vencimiento.
- ¡Si la fecha de hoy ha pasado la fecha de vencimiento, aparece un mensaje!

## Paso 6: Establezca JavaScript como acción de apertura de PDF

Ahora, debes configurar la acción de JavaScript como la acción de apertura para tu documento PDF. Esto significa que JavaScript se ejecutará tan pronto como se abra el PDF.

```csharp
doc.OpenAction = javaScript;
```

Esta línea le indica al PDF que ejecute el código JavaScript cuando alguien lo abra. ¡Es como configurar un recordatorio que se activa en cuanto abres tu calendario!

## Paso 7: Guarde el documento PDF

Finalmente, es el momento de guardar su documento PDF con la función de fecha de caducidad. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Esta línea guarda el PDF en el directorio especificado con el nombre "SetExpiryDate_out.pdf". ¡Es como poner la obra de arte terminada en un marco!

## Conclusión

¡Y ya está! Has creado con éxito un archivo PDF con fecha de caducidad utilizando Aspose.PDF para .NET. Esta función no solo mejora la seguridad, sino que también garantiza que la información confidencial se mantenga bajo control. Ya sea que estés enviando contratos, informes o cualquier otro documento importante, establecer una fecha de caducidad puede ser un cambio radical.

## Preguntas frecuentes

### ¿Qué es Aspose.PDF para .NET?
Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores crear, manipular y convertir documentos PDF en aplicaciones .NET.

### ¿Puedo utilizar Aspose.PDF gratis?
 Sí, puedes utilizar una versión de prueba gratuita de Aspose.PDF. Puedes descargarla[aquí](https://releases.aspose.com/).

### ¿Cómo compro Aspose.PDF?
Puedes comprar Aspose.PDF visitando el sitio[Página de compra](https://purchase.aspose.com/buy).

### ¿Qué pasa si necesito ayuda?
Si tiene alguna pregunta o necesita ayuda, puede visitar el[Foro de soporte de Aspose](https://forum.aspose.com/c/pdf/10).

### ¿Puedo obtener una licencia temporal para Aspose.PDF?
 Sí, puedes solicitar una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).