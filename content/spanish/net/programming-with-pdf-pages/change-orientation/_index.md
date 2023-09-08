---
title: Cambiar orientación
linktitle: Cambiar orientación
second_title: Aspose.PDF para referencia de API .NET
description: Guía paso a paso para cambiar la orientación de la página de un PDF con Aspose.PDF para .NET. Fácil de seguir e implementar en sus proyectos.
type: docs
weight: 10
url: /es/net/programming-with-pdf-pages/change-orientation/
---
En este tutorial, lo guiaremos paso a paso para cambiar la orientación de la página de un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarle a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo cambiar la orientación de la página de sus documentos PDF usando Aspose.PDF para .NET.

## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#.
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: definir el directorio de documentos
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
Ahora vamos a revisar cada página del documento y cambiar su orientación. Para cada página, modificamos las dimensiones del cuadro de medios (`MediaBox`) intercambiando el ancho y el alto, luego ajustamos las coordenadas del cuadro de medios para mantener la posición de la página. Finalmente, configuramos la rotación de la página a 90 grados.

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

## Paso 4: guarde el documento PDF modificado
 Finalmente, puede guardar el documento PDF modificado en un archivo de salida usando el`Save()` método de la`Document`clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para cambiar la orientación usando Aspose.PDF para .NET 

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
	// Debemos mover la página hacia arriba para compensar el cambio de tamaño de página.
	// (el borde inferior de la página es 0,0 y la información generalmente se coloca desde el
	// Parte superior de la página. Es por eso que movemos el borde del amante hacia arriba en la diferencia entre
	// Altura vieja y nueva.
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
En este tutorial, aprendimos cómo cambiar la orientación de la página de un documento PDF usando Aspose.PDF para .NET. Si sigue los pasos descritos anteriormente, podrá implementar fácilmente esta funcionalidad en sus propios proyectos. No dude en explorar más la documentación de Aspose.PDF para descubrir otras funciones útiles para trabajar con archivos PDF.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de cambiar la orientación de la página en un documento PDF?

R: Cambiar la orientación de la página en un documento PDF le permite rotar el contenido de la página 90 grados. Esto puede resultar útil en situaciones en las que el contenido original debe mostrarse o imprimirse en una orientación diferente, como cambiar del modo vertical al horizontal o viceversa.

#### P: ¿Puedo cambiar la orientación de páginas específicas en el documento PDF?

 R: Sí, puedes cambiar la orientación de páginas específicas en el documento PDF. En el código fuente de C# proporcionado, el`foreach` El bucle se utiliza para recorrer cada página del documento y cambiar su orientación. Si solo desea cambiar la orientación de páginas específicas, puede modificar el bucle para apuntar a esas páginas según sus números de página u otros criterios.

#### P: ¿Cambiar la orientación de la página afecta el diseño del contenido de la página?

R: Sí, cambiar la orientación de la página afectará el diseño del contenido de la página. El contenido se rotará 90 grados y se intercambiará el ancho y el alto de la página. Como resultado, la ubicación y alineación del contenido de la página pueden cambiar.

#### P: ¿Puedo girar la página en un ángulo distinto de 90 grados?

 R: En el código fuente de C# proporcionado, la rotación de la página se establece en 90 grados usando`page.Rotate = Rotate.on90;` . Sin embargo, puede cambiar el ángulo de rotación a otros valores si es necesario. Por ejemplo, puedes usar`Rotate.on180` para rotar la página 180 grados o`Rotate.on270` para girarlo 270 grados.

#### P: ¿Cómo manejo el contenido de la página que se desborda después de cambiar la orientación?

R: Al cambiar la orientación de la página, las dimensiones de la página pueden cambiar, lo que puede provocar un desbordamiento de contenido. Para solucionar esto, es posible que deba ajustar el diseño y el formato del contenido de la página. Puede utilizar las funciones proporcionadas por Aspose.PDF para .NET, como cambiar el tamaño de los elementos, ajustar los márgenes o reorganizar el contenido, para garantizar que el contenido de la página se ajuste correctamente después del cambio de orientación.