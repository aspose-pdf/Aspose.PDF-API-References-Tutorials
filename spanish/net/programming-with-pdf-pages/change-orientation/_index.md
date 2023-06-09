---
title: Cambiar Orientación
linktitle: Cambiar Orientación
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para cambiar la orientación de página de un PDF con Aspose.PDF para .NET. Fácil de seguir e implementar en tus proyectos.
type: docs
weight: 10
url: /es/net/programming-with-pdf-pages/change-orientation/
---
En este tutorial, lo guiaremos a través del proceso paso a paso para cambiar la orientación de la página de un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo cambiar la orientación de la página de sus documentos PDF usando Aspose.PDF para .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde se encuentra su archivo PDF de entrada y donde desea guardar su archivo PDF de salida modificado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento PDF
 Luego puede cargar el documento PDF desde el archivo de entrada usando el`Document` clase de Aspose.PDF. Asegúrese de especificar la ruta correcta al archivo PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 3: cambiar la orientación de la página
Ahora vamos a recorrer cada página del documento y cambiar su orientación. Para cada página, modificamos las dimensiones del cuadro de medios (`MediaBox`) intercambiando el ancho y el alto, luego ajustamos las coordenadas del cuadro de medios para mantener la posición de la página. Finalmente, configuramos la rotación de la página a 90 grados.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Paso 4: Guarde el documento PDF modificado
 Finalmente, puede guardar el documento PDF modificado en un archivo de salida utilizando el`Save()` metodo de la`Document`clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para Change Orientation usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Debemos mover la página hacia arriba para compensar el cambio de tamaño de página
	// (el borde inferior de la página es 0,0 y la información generalmente se coloca desde el
	// Parte superior de la página. Es por eso que movemos el borde del amante hacia arriba en la diferencia entre
	// Vieja y nueva altura.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// A veces también necesitamos configurar CropBox (si se configuró en el archivo original)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Configuración del ángulo de rotación de la página
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Guardar archivo de salida
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Conclusión
En este tutorial, aprendimos cómo cambiar la orientación de la página de un documento PDF usando Aspose.PDF para .NET. Siguiendo los pasos descritos anteriormente, puede implementar fácilmente esta funcionalidad en sus propios proyectos. Siéntase libre de explorar más la documentación de Aspose.PDF para descubrir otras características útiles para trabajar con archivos PDF.