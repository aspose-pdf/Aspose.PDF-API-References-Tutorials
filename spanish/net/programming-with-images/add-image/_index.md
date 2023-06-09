---
title: Añadir imagen
linktitle: Añadir imagen
second_title: Referencia de API de Aspose.PDF para .NET
description: Agregue fácilmente una imagen a un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 10
url: /es/net/programming-with-images/add-image/
---

Esta guía lo guiará paso a paso sobre cómo agregar una imagen a un documento PDF utilizando Aspose.PDF para .NET. Asegúrese de que ya ha configurado su entorno y siga los pasos a continuación:

## Paso 1: Definir el directorio de documentos

 Antes de comenzar, asegúrese de configurar el directorio correcto para los documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta al directorio donde se encuentra su documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: abre el documento

 En este paso, abriremos el documento PDF usando el`Document` clase de Aspose.PDF. Utilizar el`Document` constructor y pase la ruta al documento PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Paso 3: establecer las coordenadas de la imagen

 Establezca las coordenadas de la imagen que desea agregar. las variables`lowerLeftX`, `lowerLeftY`, `upperRightX` y`upperRightY` representan las coordenadas de la esquina inferior izquierda y la esquina superior derecha de la imagen respectivamente.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Paso 4: Obtener la página donde se debe agregar la imagen

Para agregar la imagen a una página específica del documento PDF, primero debemos recuperar esa página. En este ejemplo, agregamos la imagen a la segunda página (índice 1) del documento.

```csharp
Page page = pdfDocument.Pages[1];
```

## Paso 5: Cargue la imagen desde una secuencia

Ahora cargaremos la imagen que queremos agregar al documento PDF. Este ejemplo asume que tiene un archivo de imagen llamado`aspose-logo.jpg` en el mismo directorio que su documento. Reemplace el nombre del archivo si es necesario.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Paso 6: agregue la imagen a los recursos de la página

Para usar la imagen en el documento PDF, debemos agregarla a la colección de imágenes de recursos de la página.

```csharp
page.Resources.Images.Add(imageStream);
```

## Paso 7: Guardar el estado actual de los gráficos

 Antes de dibujar la imagen, necesitamos guardar el estado actual de los gráficos usando el`GSave` operador. Esto garantiza que los cambios en el estado de los gráficos se puedan revertir más tarde.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Paso 8: Crear objetos Rectángulo y Matriz

 Ahora crearemos un`Rectangle` objeto y un`Matrix` objeto. El rectángulo representa la posición y el tamaño de la imagen, mientras que la matriz define cómo debe colocarse la imagen.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Paso 9: matriz de concatenación para la colocación de imágenes

 Para especificar cómo debe colocarse la imagen en el rectángulo, usamos el`ConcatenateMatrix`operador. Este operador define la matriz de transformación que asigna el espacio de coordenadas de la imagen al espacio de coordenadas de la página.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Paso 10: Dibujar la imagen

 En este paso dibujaremos la imagen en la página usando el`Do` operador. El`Do` El operador toma el nombre de la imagen de los recursos y lo dibuja en la página.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Paso 11: restaurar el estado de los gráficos

 Después de dibujar la imagen, necesitamos restaurar el estado gráfico anterior usando el`GRestore` operador.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Paso 12: Guarde el documento actualizado

 Finalmente, guardaremos el documento actualizado en un archivo nuevo. Actualizar el`dataDir` variable con el directorio de salida deseado y el nombre de archivo.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Agregar imagen usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Establecer coordenadas
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Obtener la página donde se debe agregar la imagen
Page page = pdfDocument.Pages[1];
// Cargar imagen en flujo
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Agregar imagen a la colección de imágenes de los recursos de la página
page.Resources.Images.Add(imageStream);
// Usando el operador GSave: este operador guarda el estado actual de los gráficos
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Crear objetos Rectángulo y Matriz
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//Usando el operador ConcatenateMatrix (matriz concatenada): define cómo se debe colocar la imagen
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Usando el operador Do: este operador dibuja la imagen
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Usando el operador GRestore: este operador restaura el estado de los gráficos
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Guardar documento actualizado
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Conclusión

En este tutorial, aprendimos cómo agregar una imagen a un documento PDF usando Aspose.PDF para .NET. Cubrimos cada paso en detalle, desde abrir el documento hasta guardar la versión actualizada. Al seguir esta guía, ahora debería poder incrustar imágenes en sus archivos PDF mediante programación usando C# y Aspose.PDF.