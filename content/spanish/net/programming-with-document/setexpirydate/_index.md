---
title: Establecer fecha de caducidad en archivo PDF
linktitle: Establecer fecha de caducidad en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a establecer la fecha de vencimiento en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.
type: docs
weight: 300
url: /es/net/programming-with-document/setexpirydate/
---
Aspose.PDF para .NET es una potente biblioteca que ofrece varias funciones para trabajar con archivos PDF. Una de ellas es la capacidad de establecer una fecha de caducidad para un documento PDF. En este tutorial, le explicaremos el proceso de establecer una fecha de caducidad para un documento PDF utilizando Aspose.PDF para .NET. 

## Paso 1: Establezca la ruta al directorio del documento

Antes de comenzar, debemos establecer la ruta del directorio donde se encuentra nuestro documento PDF. Almacenaremos esta ruta en una variable llamada "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Crear un nuevo documento PDF

 Para crear un nuevo documento PDF, necesitamos crear una nueva instancia`Aspose.Pdf.Document` objeto. Podemos hacer esto usando el siguiente código:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Paso 3: Agregar una nueva página al documento PDF

Una vez que hemos creado el documento PDF, podemos añadirle una nueva página. Para ello, podemos utilizar el siguiente código:

```csharp
doc.Pages.Add();
```

## Paso 4: Agregar texto al documento PDF

 Después de agregar una página al documento PDF, podemos agregarle texto usando el`Paragraphs` Colección. Podemos hacer esto usando el siguiente código:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Paso 5: Configurar la fecha de caducidad del PDF mediante JavaScript

Para configurar la fecha de caducidad del PDF, necesitamos crear un objeto JavaScript. Podemos hacerlo mediante el siguiente código:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Establecer JavaScript como acción de apertura de PDF
doc.OpenAction = javaScript;
```

En este código, establecemos la fecha de vencimiento en mayo de 2017.

## Paso 6: Guarde el archivo PDF

 Después de haber establecido la fecha de caducidad, debe guardar el archivo PDF. Para ello, puede utilizar el botón`Save` método de la`Document` objeto y pase la ruta donde desea guardar el archivo PDF actualizado.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);
```

### Código fuente de ejemplo para establecer fecha de vencimiento con Aspose.PDF para .NET

Aquí está el código fuente de ejemplo completo para configurar la fecha de vencimiento usando Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear una instancia del objeto Documento
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Agregar página a la colección de páginas del archivo PDF
doc.Pages.Add();
// Agregar fragmento de texto a la colección de párrafos del objeto de página
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Crear un objeto JavaScript para establecer la fecha de caducidad del PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Establecer JavaScript como acción de apertura de PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Guardar documento PDF
doc.Save(dataDir);
```

## Conclusión

Establecer una fecha de vencimiento para un documento PDF mediante Aspose.PDF para .NET es una función útil para garantizar que el documento solo sea válido durante un período específico. Siguiendo la guía paso a paso y utilizando el código fuente de C# proporcionado, los desarrolladores pueden establecer fácilmente la fecha de vencimiento y crear archivos PDF con validez limitada en el tiempo. Esta función puede ser particularmente útil para documentos a los que se debe acceder o distribuir durante un período limitado.

### Preguntas frecuentes sobre la fecha de caducidad establecida en un archivo PDF

#### P: ¿Puedo establecer una fecha de vencimiento diferente para el documento PDF?

 R: Sí, puede establecer una fecha de vencimiento diferente para el documento PDF modificando el código JavaScript en el Paso 5. En el ejemplo proporcionado, la fecha de vencimiento está establecida en mayo de 2017. Para establecer una fecha de vencimiento diferente, debe modificar el código JavaScript en el Paso 5.`year` y`month` variables en el código JavaScript al año y mes deseados.

#### P: ¿Qué sucede cuando el documento PDF ha expirado?

A: Cuando el documento PDF ha caducado, tal y como se especifica en el código JavaScript, el visor mostrará un mensaje de alerta indicando que el archivo ha caducado y que el usuario necesita uno nuevo. Este mensaje de alerta se mostrará cuando se abra el PDF.

#### P: ¿Puedo utilizar una hora específica para la fecha de vencimiento en lugar de solo la fecha?

 R: Sí, puedes establecer una hora específica para la fecha de vencimiento en el código JavaScript. Al modificar el`expiry` variable en el código JavaScript para incluir el tiempo deseado, puede establecer un tiempo específico para la fecha de vencimiento.