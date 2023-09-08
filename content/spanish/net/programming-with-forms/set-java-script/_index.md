---
title: Establecer secuencia de comandos Java
linktitle: Establecer secuencia de comandos Java
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a utilizar Aspose.PDF para .NET para configurar JavaScript en campos de formulario en archivos PDF.
type: docs
weight: 270
url: /es/net/programming-with-forms/set-java-script/
---
En esta guía, explicaremos paso a paso cómo utilizar la biblioteca Aspose.PDF para .NET para definir JavaScript en un campo de formulario de un documento PDF. Le mostraremos cómo configurar acciones de JavaScript para realizar operaciones específicas en el campo de texto.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado en su sistema.
- La biblioteca Aspose.PDF para .NET. Puede descargarlo desde el sitio web oficial de Aspose.

## Paso 1: Configurar el directorio de documentos

 El primer paso es configurar el directorio de documentos donde se encuentra el archivo PDF con el que desea trabajar. Puedes usar el`dataDir` variable para especificar la ruta del directorio.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Asegúrate de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: cargar el archivo PDF de entrada

En este paso, cargaremos el archivo PDF de entrada usando el`Document` clase de Aspose.PDF.

```csharp
// Cargar archivo PDF de entrada
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Asegúrese de que el archivo PDF de entrada esté presente en el directorio de documentos especificado.

## Paso 3: acceder al campo TextBox

 Para aplicar JavaScript a un campo de texto específico, primero debemos acceder a ese campo. En este ejemplo, asumimos que el campo de texto se llama "cuadro de texto1". Utilizar el`doc.Form["textbox1"]` método para obtener el correspondiente`TextBoxField` objeto.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Asegúrese de que el campo de texto especificado exista en el archivo PDF de entrada.

## Paso 4: configurar acciones de JavaScript

 Ahora que hemos accedido al campo de texto, podemos configurar las acciones de JavaScript asociadas con este campo. En este ejemplo, usaremos dos acciones:`OnModifyCharacter` y`OnFormat` . Estas acciones se definirán utilizando`JavascriptAction` objetos.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Asegúrese de personalizar las acciones de JavaScript según sus necesidades.

## Paso 5: configurar el valor del campo inicial

Antes de guardar el PDF resultante, podemos establecer un valor inicial para el campo de texto. En este ejemplo, estableceremos el valor "123" para el campo.

```csharp
field.Value = "123";
```

Personaliza este valor según tus necesidades.

## Paso 6: guardar el PDF resultante

 Ahora que hemos terminado de configurar el campo de texto y las acciones de JavaScript, podemos guardar el PDF resultante usando el`Save` método de la`Document` clase.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Guardar el PDF resultante
doc.Save(dataDir);
```

Asegúrese de especificar la ruta completa y el nombre del archivo del PDF resultante.


### Código fuente de muestra para configurar Java Script usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar archivo PDF de entrada
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 dígitos después del punto
// Sin separador
// Estilo neg = menos
// Sin moneda
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Establecer el valor del campo inicial
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Guardar PDF resultante
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusión

En esta guía, aprendimos cómo usar la biblioteca Aspose.PDF para .NET para configurar JavaScript en un campo de formulario de un documento PDF. Siguiendo los pasos descritos, puede personalizar las acciones de JavaScript para realizar diversas operaciones en campos de texto. No dude en explorar más a fondo las funciones de Aspose.PDF para .NET para ampliar las posibilidades de manipulación de archivos PDF.


### Preguntas frecuentes

#### P: ¿Puedo usar Aspose.PDF para .NET para agregar JavaScript a otros elementos del formulario, como casillas de verificación y botones de opción?

 R: Sí, Aspose.PDF para .NET le permite agregar JavaScript a varios elementos de formulario, incluidas casillas de verificación, botones de opción y listas desplegables. Puedes usar el`JavascriptAction` clase para definir acciones de JavaScript para diferentes elementos de formulario.

#### P: ¿Es posible validar la entrada del usuario usando JavaScript en los campos del formulario?

 R: Sí, puede utilizar JavaScript para validar la entrada del usuario en los campos del formulario. Al definir acciones de JavaScript como`OnBlur` o`OnKeystroke` para un campo de formulario, puede validar los datos ingresados y mostrar mensajes de error si es necesario.

#### P: ¿Puedo ejecutar funciones JavaScript complejas usando Aspose.PDF para .NET?

 R: Sí, puede ejecutar funciones JavaScript complejas utilizando Aspose.PDF para .NET. Tiene la flexibilidad de definir funciones JavaScript personalizadas y llamarlas dentro del`JavascriptAction`.

#### P: ¿Aspose.PDF para .NET admite eventos de JavaScript distintos de los mencionados en este tutorial?

 R: Sí, Aspose.PDF para .NET admite una amplia gama de eventos de JavaScript, incluidos`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , y`OnMouseUp`, entre otros. Puede utilizar estos eventos para activar acciones de JavaScript basadas en las interacciones del usuario.

#### P: ¿Puedo usar Aspose.PDF para .NET para extraer código JavaScript de documentos PDF existentes?

 R: Aspose.PDF para .NET brinda la capacidad de extraer código JavaScript de documentos PDF existentes. Puedes usar el`JavascriptAction` class y otros métodos relevantes para acceder y analizar acciones de JavaScript en formato PDF.