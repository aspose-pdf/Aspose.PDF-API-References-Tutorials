---
title: Orientación de la página según las dimensiones de la imagen
linktitle: Orientación de la página según las dimensiones de la imagen
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para configurar la orientación de la página según las dimensiones de la imagen con Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/document-conversion/page-orientation-according-image-dimensions/
---

En este tutorial, lo guiaremos a través del proceso de configuración de la orientación de la página según las dimensiones de una imagen usando Aspose.PDF para .NET. Recorreremos una lista de imágenes JPG en un directorio determinado y ajustaremos automáticamente la orientación de la página según el ancho de cada imagen. Siga los pasos a continuación para lograr esto.

## requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Biblioteca Aspose.PDF para .NET instalada en su sistema.
- Un entorno de desarrollo como Visual Studio.

## Paso 1: Examinar imágenes JPG
En este paso, buscaremos todas las imágenes JPG en un directorio determinado. Siga el código a continuación:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear un nuevo documento PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//Recupere los nombres de todos los archivos JPG en un directorio en particular
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Asegúrese de reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio real donde se encuentran sus imágenes JPG.

## Paso 2: Creación de la página y la imagen
Después de navegar por los archivos JPG, crearemos una página y una imagen para cada archivo. Usa el siguiente código:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Crear un objeto de página
Aspose.Pdf.Page page = doc.Pages.Add();

// Crear un objeto de imagen
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Paso 3: Comprobación de las dimensiones de la imagen
Ahora vamos a comprobar las dimensiones de cada imagen para determinar la orientación de la página. Usa el siguiente código:

```csharp
// Cree un objeto BitMap para obtener información del archivo de imagen
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Compruebe si el ancho de la imagen es mayor que el ancho de la página o no
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Si el ancho de la imagen es menor que el ancho de la página, establezca la orientación de la página en vertical
page.PageInfo.IsLandscape = false;
```

## Paso 4: agregar la imagen al documento PDF
Después de verificar las dimensiones de la imagen, agregaremos la imagen a la colección de párrafos del documento PDF. Usa el siguiente código:

```csharp
//Agregue la imagen a la colección de párrafos del documento PDF
page.Paragraphs.Add(image1);
```

## Paso 5: Guardar el archivo PDF
Una vez que hayamos agregado todas las imágenes al documento PDF, ahora podemos guardar el archivo PDF resultante. Aquí está el último paso:

```csharp
// Guarde el archivo PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con el directorio deseado donde desea guardar el archivo PDF de salida.

### Ejemplo de código fuente para la orientación de la página según las dimensiones de la imagen usando Aspose.Words para .NET

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Recupere los nombres de todos los archivos JPG en un directorio en particular
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Crear un objeto de página
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Crear un objeto de imagen
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Cree un objeto BitMap para obtener la información del archivo de imagen
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Compruebe si el ancho del archivo de imagen es mayor que el ancho de la página o no
	if (myimage.Width > page.PageInfo.Width)
		// Si el ancho de la imagen es mayor que el ancho de la página, establezca la orientación de la página en Horizontal
		page.PageInfo.IsLandscape = true;
	else
		// Si el ancho de la imagen es menor que el ancho de la página, establezca la orientación de la página en Vertical
		page.PageInfo.IsLandscape = false;
	// Agregue la imagen a la colección de párrafos del documento PDF
	page.Paragraphs.Add(image1);
}
// Guarde el archivo PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Conclusión
En este tutorial, cubrimos el proceso paso a paso de configurar la orientación de la página según las dimensiones de una imagen usando Aspose.PDF para .NET. Siguiendo las instrucciones descritas anteriormente, ahora debería poder crear un documento PDF con la orientación de página correcta para cada imagen. Esta característica es útil cuando tiene imágenes de diferentes tamaños y desea incrustarlas en un documento PDF.