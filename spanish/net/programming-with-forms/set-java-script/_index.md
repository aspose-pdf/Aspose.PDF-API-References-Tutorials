---
title: Establecer secuencias de comandos de Java
linktitle: Establecer secuencias de comandos de Java
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para configurar JavaScript en campos de formulario en archivos PDF.
type: docs
weight: 270
url: /es/net/programming-with-forms/set-java-script/
---

En esta guía, vamos a explicar paso a paso cómo usar la biblioteca Aspose.PDF para .NET para definir JavaScript en un campo de formulario de un documento PDF. Le mostraremos cómo configurar acciones de JavaScript para realizar operaciones específicas en el campo de texto.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado en su sistema.
- La biblioteca Aspose.PDF para .NET. Puede descargarlo desde el sitio web oficial de Aspose.

## Paso 1: Configuración del directorio de documentos

 El primer paso es configurar el directorio del documento donde se encuentra el archivo PDF en el que desea trabajar. Puedes usar el`dataDir`variable para especificar la ruta del directorio.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: Cargar el archivo PDF de entrada

 En este paso, cargaremos el archivo PDF de entrada usando el`Document`clase de Aspose.PDF.

```csharp
// Cargar archivo PDF de entrada
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Asegúrese de que el archivo PDF de entrada esté presente en el directorio de documentos especificado.

## Paso 3: Acceso al campo TextBox

 Para aplicar JavaScript a un campo de texto específico, primero debemos acceder a ese campo. En este ejemplo, asumimos que el campo de texto se llama "textbox1". Utilizar el`doc.Form["textbox1"]` método para obtener el correspondiente`TextBoxField` objeto.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Asegúrese de que el campo de texto especificado existe en el archivo PDF de entrada.

## Paso 4: Configure las acciones de JavaScript

 Ahora que hemos accedido al campo de texto, podemos configurar las acciones de JavaScript asociadas a este campo. En este ejemplo, usaremos dos acciones:`OnModifyCharacter` y`OnFormat` . Estas acciones se definirán mediante`JavascriptAction` objetos.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Asegúrese de personalizar las acciones de JavaScript según sus necesidades.

## Paso 5: Establecer el valor del campo inicial

Antes de guardar el PDF resultante, podemos establecer un valor inicial para el campo de texto. En este ejemplo, estableceremos el valor "123" para el campo.

```csharp
field.Value = "123";
```

Personaliza este valor según tus necesidades.

## Paso 6: Guardar el PDF resultante

 Ahora que hemos terminado de configurar el campo de texto y las acciones de JavaScript, podemos guardar el PDF resultante usando el`Save` metodo de la`Document` clase.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Guardar PDF resultante
doc.Save(dataDir);
```

Asegúrese de especificar la ruta completa y el nombre de archivo del PDF resultante.


### Ejemplo de código fuente para Set Java Script usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar archivo PDF de entrada
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 dígitos después del punto
// Sin separador
// Estilo negativo = menos
// sin moneda
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Establecer valor de campo inicial
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Guardar PDF resultante
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusión

En esta guía, aprendimos a usar la biblioteca Aspose.PDF para .NET para configurar JavaScript en un campo de formulario de un documento PDF. Siguiendo los pasos descritos, puede personalizar las acciones de JavaScript para realizar varias operaciones en los campos de texto. Siéntase libre de explorar más a fondo las funciones de Aspose.PDF para .NET para ampliar las posibilidades de manipular archivos PDF.