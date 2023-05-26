---
title: lnk Ширина линии аннотации
linktitle: lnk Ширина линии аннотации
second_title: Aspose.PDF для справочника API .NET
description: В этой статье представлено пошаговое руководство по настройке ширины линии аннотации lnk с использованием Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF — это мощный и широко используемый инструмент для работы с файлами PDF в приложениях .NET. Он предоставляет множество функций для создания, редактирования и управления PDF-файлами, включая возможность добавления аннотаций к страницам. В этом руководстве мы объясним, как установить ширину линии аннотации ссылки с помощью Aspose.PDF для .NET.

Если у вас есть эти предварительные условия, создайте новый проект консольного приложения в Visual Studio. Затем добавьте ссылку на библиотеку Aspose.PDF для .NET, щелкнув правой кнопкой мыши проект в обозревателе решений, выбрав «Управление пакетами NuGet» и выполнив поиск «Aspose.PDF» в диспетчере пакетов NuGet.

Чтобы добавить аннотацию lnk в документ PDF, выполните следующие действия:

##  Создать новый`Document` object.
```csharp
Document doc = new Document();
```
## Добавьте новую страницу в документ.
```csharp
doc.Pages.Add();
```
##  Создайте список`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Создать новый`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Создать новый`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Добавьте жест в список рукописных жестов.
```csharp
inkList.Add(gesture);
```
##  Создать новый`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Установите тему и заголовок аннотации.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Установите цвет аннотации.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Создать новый`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Добавьте аннотацию на страницу.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Сохраните документ в файл.
```c// Save output file
doc.Save(dataDir);


```
### В примере показана ширина строки аннотации lnk с Aspose.PDF для .NET.

```csharp


// Путь к каталогу документов.
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
// Сохранить выходной файл
doc.Save(dataDir);


```
