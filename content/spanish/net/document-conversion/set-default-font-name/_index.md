---
title: Establecer nombre de fuente predeterminado
linktitle: Establecer nombre de fuente predeterminado
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para configurar el nombre de fuente predeterminado en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 270
url: /es/net/document-conversion/set-default-font-name/
---
En este tutorial, le mostraremos cómo configurar el nombre de fuente predeterminado en un archivo PDF usando Aspose.PDF para .NET. A veces, cuando extraes imágenes de un archivo PDF, puedes encontrarte con problemas de fuentes que faltan. Al especificar un nombre de fuente predeterminado, puede asegurarse de que el texto extraído se muestre correctamente. Siga los pasos a continuación para configurar el nombre de fuente predeterminado en un archivo PDF.

## Requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: cargar el documento PDF
 El primer paso es cargar el documento PDF en un`Document` objeto. Utilice el siguiente código:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Código para agregar
}
```

 Asegúrate de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentra su archivo PDF.

## Paso 2: establecer el nombre de fuente predeterminado
 A continuación, configuraremos el nombre de fuente predeterminado usando el`DefaultFontName` opción de la`RenderingOptions` objeto. Utilice el siguiente código:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Código para agregar
     }
}
```

 Asegúrate de reemplazar`"Arial"` con el nombre de fuente deseado.

## Paso 3: Extracción de imágenes
A continuación, extraeremos la imagen de la página especificada del documento PDF. Utilice el siguiente código:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Asegúrese de especificar el número de página correcto en`pdfDocument.Pages[1]`.

### Código fuente de ejemplo para establecer el nombre de fuente predeterminado usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Conclusión
En este tutorial, aprendimos cómo configurar el nombre de fuente predeterminado en un archivo PDF usando Aspose.PDF para .NET. Al especificar un nombre de fuente predeterminado, puede asegurarse de que el texto extraído se muestre correctamente. Utilice este método para resolver problemas de fuentes faltantes al extraer imágenes de archivos PDF.

### Preguntas frecuentes

#### P: ¿Qué es Aspose.PDF para .NET?

R: Aspose.PDF para .NET es una potente biblioteca que permite a los desarrolladores trabajar con documentos PDF en aplicaciones C#. Ofrece varias funcionalidades, incluida la configuración del nombre de fuente predeterminado en un archivo PDF.

#### P: ¿Por qué necesitaría configurar el nombre de fuente predeterminado en un archivo PDF?

R: Configurar el nombre de fuente predeterminado es útil al extraer texto de un documento PDF. Si el PDF contiene texto con fuentes que no están disponibles en la máquina de extracción, especificar un nombre de fuente predeterminado garantiza una visualización correcta del texto.

#### P: ¿Cómo puedo cargar un documento PDF y configurar el nombre de fuente predeterminado usando Aspose.PDF para .NET?

 R: Para cargar un documento PDF y establecer el nombre de fuente predeterminado, puede utilizar el`Document`clase para cargar el archivo PDF y el`RenderingOptions.DefaultFontName` propiedad para especificar el nombre de fuente predeterminado deseado.

#### P: ¿Puedo elegir cualquier fuente como nombre de fuente predeterminado?

R:Sí, puede elegir cualquier fuente que esté disponible en la máquina de extracción como nombre de fuente predeterminado. Utilice una fuente que coincida estrechamente con las fuentes que faltan en el PDF original para garantizar una representación precisa del texto.

#### P: ¿Establecer el nombre de fuente predeterminado es un cambio permanente en el archivo PDF?

R: No, configurar el nombre de fuente predeterminado usando Aspose.PDF para .NET es un cambio temporal que se realiza durante la extracción de texto. No modifica el archivo PDF original.