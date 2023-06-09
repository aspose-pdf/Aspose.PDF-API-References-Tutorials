---
title: Definir alineación
linktitle: Definir alineación
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar fácilmente la alineación del texto en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-stamps-and-watermarks/define-alignment/
---
En este tutorial, lo guiaremos paso a paso sobre cómo configurar la alineación del texto en un documento PDF utilizando Aspose.PDF para .NET. Le mostraremos cómo utilizar el código fuente de C# proporcionado para crear un sello de texto centrado en el documento PDF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo .NET instalado.
- La biblioteca Aspose.PDF para .NET descargada y referenciada en su proyecto.

## Paso 2: Cargar el documento PDF

El primer paso es cargar el documento PDF existente en su proyecto. Así es cómo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear una instancia de un objeto Documento con el archivo de entrada
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real al directorio donde se encuentra su documento PDF.

## Paso 3: Definición de la alineación

Ahora que ha cargado el documento PDF, puede establecer la alineación del sello de texto. Así es cómo:

```csharp
// Crea una instancia de un objeto FormattedText con la cadena de ejemplo
FormattedText text = new FormattedText("This");

// Agregar una nueva línea de texto a FormattedText
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// Cree un objeto TextStamp usando FormattedText
TextStamp stamp = new TextStamp(text);

// Especificar la alineación horizontal del búfer de texto como centrado
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Especificar la alineación vertical del búfer de texto como centrado
stamp.VerticalAlignment = VerticalAlignment.Center;

// Especificar la alineación horizontal del texto en el TextStamp como centrado
stamp.TextAlignment = HorizontalAlignment.Center;

// Establecer el margen superior para el objeto de búfer
stamp. TopMargin = 20;

// Agregue el objeto de sello a la primera página del documento
doc.Pages[1].AddStamp(stamp);
```

El código anterior crea un búfer de texto centrado usando la clase FormattedText para especificar el contenido y establece la alineación horizontal y vertical del búfer de texto.

## Paso 4: Guarde el documento de salida

Una vez que haya configurado la alineación del sello de texto, puede guardar el documento PDF modificado. Así es cómo:

```csharp
// Guardar el documento actualizado
doc.Save(dataDir);
```

El código anterior guarda el documento PDF editado en el directorio especificado.

### Ejemplo de código fuente para Definir alineación usando Aspose.PDF para .NET 
```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Instanciar objeto de documento con archivo de entrada
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// Crear una instancia del objeto FormattedText con una cadena de muestra
FormattedText text = new FormattedText("This");

// Agregar nueva línea de texto a FormattedText
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// Crear objeto TextStamp usando FormattedText
TextStamp stamp = new TextStamp(text);

// Especifique la Alineación horizontal del sello de texto como Alineado al centro
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Especifique la Alineación vertical del sello de texto como Alineado al centro
stamp.VerticalAlignment = VerticalAlignment.Center;

// Especifique la alineación horizontal del texto de TextStamp como alineado al centro
stamp.TextAlignment = HorizontalAlignment.Center;

// Establecer el margen superior para el objeto de sello
stamp.TopMargin = 20;

// Agregue el objeto de sello sobre la primera página del documento
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// Guardar el documento actualizado
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## Conclusión

¡Felicidades! Ha aprendido a configurar la alineación del texto en un documento PDF utilizando Aspose.PDF para .NET. Ahora puede aplicar este conocimiento para crear sellos de texto con diferentes alineaciones en sus documentos PDF.
