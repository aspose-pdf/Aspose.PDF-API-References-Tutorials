---
title: Agregar información sobre herramientas al texto en un archivo PDF
linktitle: Agregar información sobre herramientas al texto en un archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar información sobre herramientas al texto en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-text/add-tooltip-to-text/
---
Este tutorial le guiará a través del proceso de agregar información sobre herramientas al texto de un archivo PDF mediante Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Biblioteca Aspose.PDF para .NET. Puede descargarla desde el sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarla.

## Paso 1: Configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En el archivo de código donde desea agregar información sobre herramientas al texto, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Paso 3: Establezca el directorio del documento
 En el código, localiza la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Crea un documento de muestra con texto
 Crear uno nuevo`Document` objeto y agregar páginas con fragmentos de texto. En el código proporcionado, se agregan dos fragmentos de texto al documento con el texto de información sobre herramientas correspondiente.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Paso 5: Abra el documento y busque los fragmentos de texto
 Cargue el documento creado utilizando el`Document` constructor y busque los fragmentos de texto que necesitan información sobre herramientas utilizando`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Paso 6: Agregar información sobre herramientas a los fragmentos de texto
 Recorra los fragmentos de texto extraídos y cree botones invisibles en sus posiciones. Asigne el texto de información sobre herramientas deseado a los botones.`AlternateName` propiedad de la`ButtonField`. Agregue los campos de botón al formulario del documento.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Paso 7: Repita el procedimiento para fragmentos de texto adicionales con información sobre herramientas larga
Repita los pasos 5 y 6 para los fragmentos de texto con información sobre herramientas extensa. Modifique los criterios de búsqueda y el texto de la información sobre herramientas según corresponda.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Paso 8: Guarde el documento modificado
 Guarde el documento PDF modificado utilizando el`Save` método de la`Document` objeto.

```csharp
document. Save(outputFile);
```

### Código fuente de muestra para agregar información sobre herramientas al texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Crear un documento de muestra con texto
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Abrir documento con texto
Document document = new Document(outputFile);
// Cree un objeto TextAbsorber para encontrar todas las frases que coincidan con la expresión regular
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Acepta el absorbedor para las páginas del documento.
document.Pages.Accept(absorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragments = absorber.TextFragments;
// Recorrer los fragmentos
foreach (TextFragment fragment in textFragments)
{
	// Crear un botón invisible en la posición del fragmento de texto
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// El valor de AlternateName se mostrará como información sobre herramientas en una aplicación de visualización
	field.AlternateName = "Tooltip for text.";
	// Añadir campo de botón al documento
	document.Form.Add(field);
}
// A continuación habrá un ejemplo de información sobre herramientas muy larga.
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Establecer texto muy largo
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Guardar documento
document.Save(outputFile);
```

## Conclusión
Ha añadido correctamente información sobre herramientas al texto de un documento PDF con Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta de archivo de salida especificada.

## Preguntas frecuentes

#### P: ¿Cuál es el enfoque de este tutorial?

A: Este tutorial se centra en agregar información sobre herramientas al texto dentro de un archivo PDF mediante la biblioteca Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios para lograrlo.

#### P: ¿Qué espacios de nombres deben importarse para este tutorial?

R: En el archivo de código donde desea agregar información sobre herramientas al texto, importe los siguientes espacios de nombres al comienzo del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### P: ¿Cómo especifico el directorio del documento?

 A: En el código, busque la línea`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

#### P: ¿Cómo puedo crear un documento de muestra con texto?

 A: En el paso 4, crearás un nuevo`Document` objeto y agregar páginas con fragmentos de texto. El código proporcionado agrega dos fragmentos de texto con el texto de información sobre herramientas correspondiente.

#### P: ¿Cómo abro el documento y encuentro los fragmentos de texto?

 A: En el paso 5, cargará el documento creado utilizando el`Document` constructor y busque los fragmentos de texto que requieren información sobre herramientas utilizando el`TextFragmentAbsorber`.

#### P: ¿Cómo puedo agregar información sobre herramientas a los fragmentos de texto?

 A: En el paso 6, recorrerá los fragmentos de texto extraídos y creará botones invisibles en sus posiciones. El texto de la información sobre herramientas se asigna a la`AlternateName` propiedad de la`ButtonField`que se añade al formato del documento.

#### P: ¿Cómo repito el proceso para fragmentos de texto adicionales con información sobre herramientas larga?

R: Para fragmentos de texto con información sobre herramientas larga, repita los pasos 5 y 6. Modifique los criterios de búsqueda y el texto de la información sobre herramientas según corresponda.

#### P: ¿Cómo guardo el documento modificado?

 A: En el paso 8, guardará el documento PDF modificado utilizando el`Save` método de la`Document` objeto.

#### P: ¿Cuál es la principal conclusión de este tutorial?

R: Al seguir este tutorial, aprendió a mejorar su documento PDF agregando información sobre herramientas al texto mediante Aspose.PDF para .NET. Esto puede brindar información adicional valiosa para los lectores cuando interactúan con el contenido del PDF.