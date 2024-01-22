---
title: Bloque de texto oculto en archivo PDF
linktitle: Bloque de texto oculto en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a crear bloques de texto ocultos en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 230
url: /es/net/programming-with-text/hidden-text-block/
---
En este tutorial, explicaremos cómo crear un bloque de texto oculto en un archivo PDF usando la biblioteca Aspose.PDF para .NET. Un bloque de texto oculto es un texto flotante que se vuelve visible cuando el cursor del mouse pasa sobre un área específica. Revisaremos el proceso paso a paso de creación del bloque de texto oculto utilizando el código fuente C# proporcionado.

## Requisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- La biblioteca Aspose.PDF para .NET instalada.
- Un conocimiento básico de la programación en C#.

## Paso 1: configurar el directorio de documentos

 Primero, debe establecer la ruta al directorio donde desea guardar el archivo PDF generado. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir`variable con la ruta al directorio deseado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cree un documento de muestra

En este paso, creamos un documento PDF de muestra y le agregamos un fragmento de texto. El fragmento de texto servirá como activador para mostrar el bloque de texto oculto.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Paso 3: abra el documento

 Ahora, abrimos el documento creado previamente usando el`Document` clase.

```csharp
Document document = new Document(outputFile);
```

## Paso 4: busque el fragmento de texto

 Usamos un`TextFragmentAbsorber` objeto para encontrar el fragmento de texto que activará la visualización del bloque de texto oculto. En este caso, estamos buscando el texto exacto "Mueva el cursor del mouse aquí para mostrar texto flotante".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Paso 5: cree el campo de texto oculto

 Creamos un`TextBoxField` objeto para representar el campo de texto oculto. Este campo contendrá el texto que se vuelve visible cuando el cursor del mouse pasa sobre el texto del activador.

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

Creamos un campo de botón invisible que se colocará encima del fragmento de texto del activador. Este campo de botón tendrá acciones asociadas con eventos de entrada y salida del mouse.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Paso 8: guarde el documento

Finalmente guardamos el documento modificado con el bloque de texto oculto.

```csharp
document. Save(outputFile);
```

### Código fuente de muestra para bloque de texto oculto usando Aspose.PDF para .NET 
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
// Aceptar el absorbente para las páginas del documento.
document.Pages.Accept(absorber);
// Obtenga el primer fragmento de texto extraído
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Cree un campo de texto oculto para texto flotante en el rectángulo especificado de la página
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Establecer el texto que se mostrará como valor de campo
floatingField.Value = "This is the \"floating text field\".";
// Recomendamos hacer que el campo sea de "solo lectura" para este escenario.
floatingField.ReadOnly = true;
// Establezca la bandera 'oculta' para que el campo sea invisible al abrir el documento
floatingField.Flags |= AnnotationFlags.Hidden;
// No es necesario establecer un nombre de campo único, pero está permitido
floatingField.PartialName = "FloatingField_1";
// No es necesario configurar las características de la apariencia del campo, pero lo mejora.
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
// Agregar acciones al ingresar/salir del mouse en el campo del botón invisible
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Agregar campo de botón al documento
document.Form.Add(buttonField);
// guardar documento
document.Save(outputFile);
```

## Conclusión

En este tutorial, ha aprendido cómo crear un bloque de texto oculto utilizando la biblioteca Aspose.PDF para .NET. Siguiendo la guía paso a paso, puede generar un documento PDF con un campo de texto oculto que se vuelve visible cuando el cursor del mouse pasa sobre un área específica. Puede personalizar la apariencia y el comportamiento del bloque de texto oculto según sus requisitos.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito del tutorial "Bloque de texto oculto en un archivo PDF"?

R: El tutorial "Bloque de texto oculto en un archivo PDF" explica cómo crear un bloque de texto oculto en un archivo PDF utilizando la biblioteca Aspose.PDF para .NET. Un bloque de texto oculto es un texto flotante que se vuelve visible cuando el cursor del mouse pasa sobre un área específica. Este tutorial proporciona una guía paso a paso utilizando el código fuente de C#.

#### P: ¿Por qué querría crear un bloque de texto oculto en un archivo PDF?

R: Crear un bloque de texto oculto puede ser útil para documentos PDF interactivos en los que desea proporcionar información adicional o contexto que solo se vuelve visible cuando un usuario coloca el cursor del mouse sobre un área designada.

#### P: ¿Cómo configuro el directorio de documentos?

R: Para configurar el directorio de documentos:

1.  Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el`dataDir` variable con la ruta al directorio donde desea guardar el archivo PDF generado.

#### P: ¿Cómo creo un documento de muestra y le agrego un fragmento de texto?

R: En el tutorial, utilizas el`Document` clase para crear un documento PDF de muestra y agregar un fragmento de texto. Este fragmento de texto sirve como activador para mostrar el bloque de texto oculto.

#### P: ¿Cómo encuentro el fragmento de texto que activa el bloque de texto oculto?

 R: El tutorial muestra cómo utilizar un`TextFragmentAbsorber` objeto para encontrar el fragmento de texto que activa la visualización del bloque de texto oculto. Busca una cadena de texto específica dentro del documento PDF.

#### P: ¿Cómo creo y personalizo el campo de texto oculto?

 R: Creas un`TextBoxField` objeto para representar el campo de texto oculto. El tutorial proporciona código para establecer varias propiedades, como la posición, el valor, la apariencia y el comportamiento del campo de texto oculto.

#### P: ¿Cómo creo un botón invisible asociado con el bloque de texto oculto?

 R: Se crea un campo de botón invisible usando el`ButtonField` clase. Este campo de botón está ubicado encima del fragmento de texto del activador y tiene acciones asociadas con eventos de entrada y salida del mouse. Estas acciones controlan la visibilidad del bloque de texto oculto.

#### P: ¿Puedo personalizar la apariencia del bloque de texto oculto y el área de activación?

R: Sí, puedes personalizar varias propiedades tanto del campo de texto oculto como del botón invisible, incluida la fuente, el color, el tamaño y la posición.

#### P: ¿Cómo guardo el documento modificado con el bloque de texto oculto?

 R: El tutorial muestra cómo guardar el documento modificado usando el`Save` método de la`Document` clase.