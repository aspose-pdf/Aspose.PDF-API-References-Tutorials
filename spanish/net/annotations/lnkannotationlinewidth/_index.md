---
title: Ancho de línea de anotación lnk
linktitle: Ancho de línea de anotación lnk
second_title: Referencia de API de Aspose.PDF para .NET
description: Este artículo proporciona una guía paso a paso para configurar el ancho de línea de la anotación lnk usando Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF es una herramienta poderosa y ampliamente utilizada para trabajar con archivos PDF en aplicaciones .NET. Proporciona una variedad de funciones para crear, editar y manipular archivos PDF, incluida la capacidad de agregar anotaciones a las páginas. En este tutorial, explicaremos cómo configurar el ancho de línea de una anotación de enlace usando Aspose.PDF para .NET.

Una vez que tenga estos requisitos previos, cree un nuevo proyecto de aplicación de consola en Visual Studio. Luego, agregue una referencia a la biblioteca Aspose.PDF para .NET haciendo clic con el botón derecho en el proyecto en el Explorador de soluciones, seleccionando "Administrar paquetes NuGet" y buscando "Aspose.PDF" en el Administrador de paquetes NuGet.

Para agregar una anotación lnk a un documento PDF, siga estos pasos:

##  Paso 1: Crear un nuevo`Document` object.
```csharp
Document doc = new Document();
```
## Paso 2: agregue una nueva página al documento.
```csharp
doc.Pages.Add();
```
##  Paso 3: Crea una lista de`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Paso 4: Crea una nueva`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
## Paso 5: Crea una nueva`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Paso 6: Agregue el gesto a la lista de gestos de tinta.
```csharp
inkList.Add(gesture);
```
##  Paso 7: Crear un nuevo`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Paso 8: establezca el asunto y el título de la anotación.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Paso 9: establece el color de la anotación.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Paso 10: Crea un nuevo`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Paso 11: agregue la anotación a la página.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Paso 12: Guarde el documento en un archivo.
```csharp
// Guardar archivo de salida
doc.Save(dataDir);


```
### El ejemplo muestra el ancho de línea de anotación lnk con Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Guardar archivo de salida
doc.Save(dataDir);
```
