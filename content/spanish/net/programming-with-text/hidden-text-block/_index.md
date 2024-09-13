---
title: Bloque de texto oculto en archivo PDF
linktitle: Bloque de texto oculto en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear bloques de texto ocultos en archivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 230
url: /es/net/programming-with-text/hidden-text-block/
---
En este tutorial, explicaremos cómo crear un bloque de texto oculto en un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. Un bloque de texto oculto es un texto flotante que se vuelve visible cuando el cursor del mouse se desplaza sobre un área específica. Repasaremos el proceso paso a paso para crear el bloque de texto oculto utilizando el código fuente de C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Un conocimiento básico de programación en C#.

## Paso 1: Configurar el directorio de documentos

 Primero, debes establecer la ruta al directorio donde deseas guardar el archivo PDF generado. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Crear un documento de muestra

En este paso, creamos un documento PDF de muestra y le agregamos un fragmento de texto. El fragmento de texto servirá como disparador para mostrar el bloque de texto oculto.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Paso 3: Abra el documento

 Ahora, abrimos el documento creado anteriormente utilizando el`Document` clase.

```csharp
Document document = new Document(outputFile);
```

## Paso 4: Encuentra el fragmento de texto

 Usamos un`TextFragmentAbsorber`Objeto para buscar el fragmento de texto que activará la visualización del bloque de texto oculto. En este caso, buscamos el texto exacto "Mueva el cursor del mouse aquí para mostrar el texto flotante".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Paso 5: Crea el campo de texto oculto

 Creamos una`TextBoxField` Objeto que representa el campo de texto oculto. Este campo contendrá el texto que se vuelve visible cuando el cursor del mouse se desplaza sobre el texto del disparador.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Paso 6: Agregue el campo de texto oculto al documento

Agregamos el campo de texto oculto a la colección de formularios del documento.

```csharp
document.Form.Add(floatingField);
```

## Paso 7: Crea el botón invisible

Creamos un campo de botón invisible que se ubicará sobre el fragmento de texto del disparador. Este campo de botón tendrá acciones asociadas con los eventos de entrada y salida del mouse.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Paso 8: Guardar el documento

Finalmente, guardamos el documento modificado con el bloque de texto oculto.

```csharp
document. Save(outputFile);
```

### Código fuente de muestra para bloque de texto oculto con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Crear un documento de muestra con texto
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Abrir documento con texto
Document document = new Document(outputFile);
//Cree un objeto TextAbsorber para encontrar todas las frases que coincidan con la expresión regular
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Acepta el absorbedor para las páginas del documento.
document.Pages.Accept(absorber);
// Obtener el primer fragmento de texto extraído
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Crear un campo de texto oculto para texto flotante en el rectángulo especificado de la página
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Establecer el texto que se mostrará como valor del campo
floatingField.Value = "This is the \"floating text field\".";
// Recomendamos que el campo sea 'de solo lectura' para este escenario.
floatingField.ReadOnly = true;
// Establezca la bandera 'oculta' para hacer que el campo sea invisible al abrir el documento
floatingField.Flags |= AnnotationFlags.Hidden;
// No es necesario establecer un nombre de campo único, pero está permitido
floatingField.PartialName = "FloatingField_1";
// No es necesario configurar las características de apariencia del campo, pero lo hace mejor.
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Agregar campo de texto al documento
document.Form.Add(floatingField);
// Crear un botón invisible en la posición del fragmento de texto
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Crear una nueva acción de ocultar para el campo especificado (anotación) y una bandera de invisibilidad.
// (También puede hacer referencia al campo flotante por el nombre si lo especificó anteriormente).
// Agregar acciones al ingresar/salir del mouse en el campo del botón invisible
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Añadir campo de botón al documento
document.Form.Add(buttonField);
// Guardar documento
document.Save(outputFile);
```

## Conclusión

En este tutorial, aprendió a crear un bloque de texto oculto con la biblioteca Aspose.PDF para .NET. Si sigue la guía paso a paso, podrá generar un documento PDF con un campo de texto oculto que se vuelve visible cuando el cursor del mouse se desplaza sobre un área específica. Puede personalizar la apariencia y el comportamiento del bloque de texto oculto según sus requisitos.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Bloque de texto oculto en archivo PDF"?

A: El tutorial "Bloque de texto oculto en archivo PDF" explica cómo crear un bloque de texto oculto en un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. Un bloque de texto oculto es un texto flotante que se vuelve visible cuando el cursor del mouse se desplaza sobre un área específica. Este tutorial proporciona una guía paso a paso utilizando el código fuente de C#.

#### P: ¿Por qué querría crear un bloque de texto oculto en un archivo PDF?

R: Crear un bloque de texto oculto puede ser útil para documentos PDF interactivos en los que desea proporcionar información o contexto adicional que solo se vuelve visible cuando un usuario pasa el cursor del mouse sobre un área designada.

#### P: ¿Cómo configuro el directorio de documentos?

A: Para configurar el directorio de documentos:

1.  Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta al directorio donde desea guardar el archivo PDF generado.

#### P: ¿Cómo puedo crear un documento de muestra y agregarle un fragmento de texto?

 A: En el tutorial, utilizas el`Document` Clase para crear un documento PDF de muestra y agregar un fragmento de texto. Este fragmento de texto sirve como disparador para mostrar el bloque de texto oculto.

#### P: ¿Cómo encuentro el fragmento de texto que activa el bloque de texto oculto?

 A: El tutorial demuestra cómo utilizar un`TextFragmentAbsorber` Objeto para encontrar el fragmento de texto que activa la visualización del bloque de texto oculto. Busca una cadena de texto específica dentro del documento PDF.

#### P: ¿Cómo puedo crear y personalizar el campo de texto oculto?

 A: Creas una`TextBoxField`objeto para representar el campo de texto oculto. El tutorial proporciona código para configurar varias propiedades, como la posición, el valor, la apariencia y el comportamiento del campo de texto oculto.

#### P: ¿Cómo puedo crear un botón invisible asociado al bloque de texto oculto?

 A: Se crea un campo de botón invisible utilizando el`ButtonField` Clase. Este campo de botón se ubica sobre el fragmento de texto del disparador y tiene acciones asociadas con los eventos de entrada y salida del mouse. Estas acciones controlan la visibilidad del bloque de texto oculto.

#### P: ¿Puedo personalizar la apariencia del bloque de texto oculto y el área de activación?

R: Sí, puedes personalizar varias propiedades tanto del campo de texto oculto como del botón invisible, incluida la fuente, el color, el tamaño y la posición.

#### P: ¿Cómo guardo el documento modificado con el bloque de texto oculto?

 A: El tutorial demuestra cómo guardar el documento modificado usando el`Save` método de la`Document` clase.