---
title: Agregar información sobre herramientas al texto
linktitle: Agregar información sobre herramientas al texto
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar información sobre herramientas al texto en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-text/add-tooltip-to-text/
---

Este tutorial lo guiará a través del proceso de agregar información sobre herramientas al texto en un documento PDF usando Aspose.PDF para .NET. El código fuente de C# proporcionado demuestra los pasos necesarios.

## Requisitos
Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier otro compilador de C# instalado en su máquina.
- Aspose.PDF para la biblioteca .NET. Puede descargarlo del sitio web oficial de Aspose o usar un administrador de paquetes como NuGet para instalarlo.

## Paso 1: configurar el proyecto
1. Cree un nuevo proyecto de C# en su entorno de desarrollo preferido.
2. Agregue una referencia a la biblioteca Aspose.PDF para .NET.

## Paso 2: importa los espacios de nombres requeridos
En el archivo de código en el que desea agregar información sobre herramientas al texto, agregue las siguientes directivas using en la parte superior del archivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Paso 3: establecer el directorio de documentos
 En el código, busque la línea que dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` y reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta al directorio donde se almacenan sus documentos.

## Paso 4: Cree un documento de muestra con texto
 Crear un nuevo`Document` objeto y agregar páginas con fragmentos de texto. En el código proporcionado, se agregan dos fragmentos de texto al documento con el texto de información sobre herramientas respectivo.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Paso 5: abre el documento y encuentra los fragmentos de texto
 Cargue el documento creado usando el`Document` constructor y encuentre los fragmentos de texto que necesitan información sobre herramientas usando`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Paso 6: agregue información sobre herramientas a los fragmentos de texto
 Recorra los fragmentos de texto extraídos y cree botones invisibles en sus posiciones. Asigne el texto de información sobre herramientas deseado al`AlternateName` propiedad de la`ButtonField`. Agregue los campos de botón al formulario del documento.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Paso 7: repita para fragmentos de texto adicionales con información sobre herramientas larga
Repita los pasos 5 y 6 para fragmentos de texto con información sobre herramientas larga. Modifique los criterios de búsqueda y el texto de información sobre herramientas en consecuencia.

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
 Guarde el documento PDF modificado usando el`Save` metodo de la`Document` objeto.

```csharp
document. Save(outputFile);
```

### Ejemplo de código fuente para Agregar información sobre herramientas al texto usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Crear documento de muestra con texto
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Abrir documento con texto
Document document = new Document(outputFile);
// Cree un objeto TextAbsorber para encontrar todas las frases que coincidan con la expresión regular
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Acepte el absorbedor para las páginas del documento.
document.Pages.Accept(absorber);
// Obtener los fragmentos de texto extraídos
TextFragmentCollection textFragments = absorber.TextFragments;
// Bucle a través de los fragmentos
foreach (TextFragment fragment in textFragments)
{
	//Crear botón invisible en la posición del fragmento de texto
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// El valor AlternateName se mostrará como información sobre herramientas en una aplicación de visualización
	field.AlternateName = "Tooltip for text.";
	// Agregar campo de botón al documento
	document.Form.Add(field);
}
// El siguiente será una muestra de información sobre herramientas muy larga
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
Ha agregado con éxito información sobre herramientas al texto en un documento PDF utilizando Aspose.PDF para .NET. El archivo PDF resultante ahora se puede encontrar en la ruta del archivo de salida especificado.