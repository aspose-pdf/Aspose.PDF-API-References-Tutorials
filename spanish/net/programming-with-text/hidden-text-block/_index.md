---
title: Bloque de texto oculto
linktitle: Bloque de texto oculto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear bloques de texto ocultos en PDF usando Aspose.PDF para .NET.
type: docs
weight: 230
url: /es/net/programming-with-text/hidden-text-block/
---

En este tutorial, explicaremos cómo crear un bloque de texto oculto utilizando la biblioteca Aspose.PDF para .NET. Un bloque de texto oculto es un texto flotante que se vuelve visible cuando el cursor del mouse pasa sobre un área específica. Pasaremos por el proceso paso a paso de crear el bloque de texto oculto utilizando el código fuente de C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Conocimientos básicos de programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde desea guardar el archivo PDF generado. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta a su directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear un documento de muestra

En este paso, creamos un documento PDF de muestra y le agregamos un fragmento de texto. El fragmento de texto servirá como disparador para mostrar el bloque de texto oculto.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Paso 3: Abra el documento

 Ahora, abrimos el documento previamente creado usando el`Document` clase.

```csharp
Document document = new Document(outputFile);
```

## Paso 4: encuentra el fragmento de texto

 usamos un`TextFragmentAbsorber` objeto para encontrar el fragmento de texto que activará la visualización del bloque de texto oculto. En este caso, estamos buscando el texto exacto "Mueva el cursor del mouse aquí para mostrar el texto flotante".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Paso 5: crea el campo de texto oculto

 Creamos un`TextBoxField` objeto para representar el campo de texto oculto. Este campo contendrá el texto que se vuelve visible cuando el cursor del mouse pasa sobre el texto del disparador.

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

## Paso 6: agregue el campo de texto oculto al documento

Agregamos el campo de texto oculto a la colección de formularios del documento.

```csharp
document.Form.Add(floatingField);
```

## Paso 7: crea el botón invisible

Creamos un campo de botón invisible que se colocará encima del fragmento de texto de activación. Este campo de botón tendrá acciones asociadas con los eventos de entrada y salida del mouse.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Paso 8: Guarde el documento

Finalmente, guardamos el documento modificado con el bloque de texto oculto.

```csharp
document. Save(outputFile);
```

### Ejemplo de código fuente para el bloque de texto oculto con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Crear documento de muestra con texto
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Abrir documento con texto
Document document = new Document(outputFile);
// Cree un objeto TextAbsorber para encontrar todas las frases que coincidan con la expresión regular
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Acepte el absorbedor para las páginas del documento.
document.Pages.Accept(absorber);
// Obtener el primer fragmento de texto extraído
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Crear campo de texto oculto para texto flotante en el rectángulo especificado de la página
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Establecer el texto que se mostrará como valor de campo
floatingField.Value = "This is the \"floating text field\".";
// Recomendamos hacer el campo 'solo lectura' para este escenario
floatingField.ReadOnly = true;
// Establezca la bandera 'oculta' para hacer que el campo sea invisible al abrir el documento
floatingField.Flags |= AnnotationFlags.Hidden;
// Establecer un nombre de campo único no es necesario pero está permitido
floatingField.PartialName = "FloatingField_1";
// No es necesario establecer las características de la apariencia del campo, pero lo hace mejor
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Agregar campo de texto al documento
document.Form.Add(floatingField);
// Crear botón invisible en la posición del fragmento de texto
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Cree una nueva acción de ocultación para el campo especificado (anotación) y el indicador de invisibilidad.
//(También puede hacer referencia al campo flotante por el nombre si lo especificó anteriormente).
// Agregue acciones al ingresar/salir del mouse en el campo del botón invisible
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Agregar campo de botón al documento
document.Form.Add(buttonField);
// Guardar documento
document.Save(outputFile);
```

## Conclusión

En este tutorial, ha aprendido a crear un bloque de texto oculto utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso, puede generar un documento PDF con un campo de texto oculto que se vuelve visible cuando el cursor del mouse pasa sobre un área específica. Puede personalizar la apariencia y el comportamiento del bloque de texto oculto según sus requisitos.