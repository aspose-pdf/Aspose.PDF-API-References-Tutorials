---
title: Texto a PDF
linktitle: Texto a PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Conversión simple y eficiente de archivos de texto a PDF utilizando Aspose.PDF para .NET.
type: docs
weight: 300
url: /es/net/document-conversion/text-to-pdf/
---

Este tutorial lo guiará a través de los pasos para convertir un archivo de texto en un archivo PDF usando Aspose.PDF para .NET. Aspose.PDF ofrece una solución simple y eficaz para convertir texto sin formato a PDF conservando el formato y la presentación del texto. Siga los pasos a continuación para realizar esta conversión.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Leer el archivo de texto
 El primer paso es leer el contenido del archivo de texto usando el`StreamReader` clase. Usa el siguiente código:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Leer el archivo de texto
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo de texto.

## Paso 2: Crear el documento PDF
 El segundo paso es crear un`Document` objeto que representará el documento PDF final. Usa el siguiente código:

```csharp
// Crear un objeto de documento
Document doc = new Document();
```

## Paso 3: Agregar texto al documento
El tercer paso es agregar el texto leído a la página del documento PDF. Usa el siguiente código:

```csharp
// Agregar una nueva página al documento
Page page = doc.Pages.Add();

//Cree un objeto TextFragment y pase el texto leído como argumento
TextFragment text = new TextFragment(tr.ReadToEnd());

// Agregar el párrafo de texto a la página
page.Paragraphs.Add(text);
```

## Paso 4: Guardar el archivo PDF
Finalmente, guarde el archivo PDF resultante especificando la ruta y el nombre de archivo deseados. Usa el siguiente código:

```csharp
// Guarde el archivo PDF resultante
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Asegúrese de especificar la ruta y el nombre de archivo deseados para el archivo PDF resultante.

### Ejemplo de código fuente para Texto a PDF usando Aspose.PDF para .NET

```csharp
try
{
	
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Leer el archivo de texto fuente
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Crea una instancia de un objeto Document llamando a su constructor vacío
	Document doc = new Document();

	// Agregar una nueva página en la colección de páginas del documento
	Page page = doc.Pages.Add();

	// Cree una instancia de TextFragmet y pase el texto del objeto del lector a su constructor como argumento
	TextFragment text = new TextFragment(tr.ReadToEnd());
	// Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Agregue un nuevo párrafo de texto en la colección de párrafos y pase el objeto TextFragment
	page.Paragraphs.Add(text);

	// Guardar el archivo PDF resultante
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión
En este tutorial, aprendimos cómo convertir un archivo de texto en un archivo PDF usando Aspose.PDF para .NET. Siguiendo los pasos dados anteriormente, puede realizar fácilmente esta conversión. Utilice este método para convertir sus archivos de texto a PDF y disfrute de la flexibilidad y calidad de Aspose.PDF.