---
title: lnk Ширина линии аннотации
linktitle: lnk Ширина линии аннотации
second_title: Справочник по Aspose.PDF для .NET API
description: В этой статье представлено пошаговое руководство по настройке ширины линии аннотации lnk с использованием Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF — мощный и широко используемый инструмент для работы с PDF-файлами в .NET-приложениях. Он предоставляет множество функций для создания, редактирования и управления PDF-файлами, включая возможность добавлять аннотации к страницам. В этом уроке мы объясним, как установить ширину линии аннотации ссылки с помощью Aspose.PDF для .NET.

Если у вас есть эти предварительные условия, создайте новый проект консольного приложения в Visual Studio. Затем добавьте ссылку на библиотеку Aspose.PDF для .NET, щелкнув правой кнопкой мыши проект в обозревателе решений, выбрав «Управление пакетами NuGet» и выполнив поиск «Aspose.PDF» в диспетчере пакетов NuGet.

Чтобы добавить аннотацию lnk в документ PDF, выполните следующие действия:

##  Шаг 1. Создайте новый`Document` object.
```csharp
Document doc = new Document();
```
## Шаг 2. Добавьте в документ новую страницу.
```csharp
doc.Pages.Add();
```
##  Шаг 3. Создайте список`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Шаг 4. Создайте новый`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Шаг 5: Создайте новый`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Шаг 6. Добавьте жест в список рукописных жестов.
```csharp
inkList.Add(gesture);
```
##  Шаг 7: Создайте новый`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Шаг 8: Установите тему и название аннотации.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Шаг 9: Установите цвет аннотации.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Шаг 10: Создайте новый`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Шаг 11: Добавьте аннотацию на страницу.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Шаг 12: Сохраните документ в файл.
```csharp
// Сохранить выходной файл
doc.Save(dataDir);


```
### В примере показана ширина линии аннотации lnk с помощью Aspose.PDF для .NET.

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

## Заключение

В этом уроке мы узнали, как установить ширину линии аннотации ссылки в PDF-документе с помощью Aspose.PDF для .NET. Aspose.PDF для .NET предоставляет широкий набор инструментов и функций для работы с PDF-документами, включая возможность создавать и настраивать аннотации ссылок. Следуя пошаговому руководству и используя предоставленный исходный код C#, разработчики могут легко добавлять интерактивные ссылки в свои PDF-документы, улучшая взаимодействие с пользователем и повышая интерактивность своих приложений. Aspose.PDF для .NET — это универсальная библиотека, которая позволяет .NET-разработчикам эффективно и результативно работать с файлами PDF.

### Часто задаваемые вопросы

#### Вопрос: Что такое аннотация ссылки в PDF-документе?

О: Аннотация ссылки в документе PDF — это интерактивный элемент, который позволяет создавать гиперссылки или действия, которые направляют пользователя в другое место в том же документе, на внешний веб-сайт или в другой документ PDF.

#### Вопрос: Как установить ширину линии аннотации ссылки с помощью Aspose.PDF для .NET?

О: Чтобы установить ширину линии аннотации ссылки с помощью Aspose.PDF для .NET, вы можете создать`InkAnnotation` объект и укажите свойство ширины линии.

#### Вопрос: Какие свойства можно настроить для аннотации ссылки в Aspose.PDF для .NET?

О: Вы можете настроить различные свойства аннотации ссылки в Aspose.PDF для .NET, такие как ее расположение, размер, цвет, свойства границы (ширина, стиль, штриховой узор и эффект), тему, заголовок и видимость.

#### Вопрос: Могу ли я создать аннотацию к ссылке, содержащую несколько рукописных жестов?

 О: Да, вы можете создать аннотацию ссылки, содержащую несколько рукописных жестов, добавив несколько`Point` массивы в`InkAnnotation` объект.

#### Вопрос: Как добавить аннотацию ссылки на определенную страницу PDF-документа?

 О: Чтобы добавить аннотацию ссылки на определенную страницу PDF-документа, вам необходимо указать номер страницы при создании`InkAnnotation` объект. Например,`new InkAnnotation(doc.Pages[1], ...)` добавляет аннотацию ссылки на первую страницу.