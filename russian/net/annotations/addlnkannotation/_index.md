---
title: Добавить аннотацию ссылки
linktitle: Добавить аннотацию ссылки
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить функцию рукописных аннотаций в PDF-документы на C# с помощью Aspose.PDF для .NET с пошаговым руководством и полным исходным кодом.
type: docs
weight: 20
url: /ru/net/annotations/addlnkannotation/
---
Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам выполнять различные операции с PDF. Одной из таких операций является добавление рукописных аннотаций в документы PDF. В этой статье мы предоставим пошаговое руководство, объясняющее исходный код C# для добавления рукописной аннотации с использованием Aspose.PDF для .NET. Давайте начнем!

## Понимание функции рукописных аннотаций Aspose.PDF для .NET

Прежде чем погрузиться в исходный код C#, давайте сначала разберемся, что такое рукописная аннотация и как она используется.

Ink Annotation — это способ рисования рукописных аннотаций произвольной формы в документах PDF. Он позволяет создавать аннотации с помощью стилуса или мыши. Эта функция полезна в ситуациях, когда вам нужно рисовать диаграммы, эскизы или другие типы аннотаций.

## Шаг 1: Создание нового документа

Первым шагом в добавлении рукописной аннотации в документ PDF является создание нового экземпляра класса Document. Это достигается с помощью следующего фрагмента кода:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Здесь мы создаем новый экземпляр класса Document и добавляем к нему новую страницу.

## Шаг 2. Создание рукописной аннотации

Следующим шагом является создание экземпляра класса InkAnnotation. Это делается с помощью следующего фрагмента кода:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Здесь мы сначала создаем прямоугольник с помощью класса System.Drawing.Rectangle и преобразуем его в Aspose.Pdf.Rectangle с помощью метода FromRect. Затем мы создаем экземпляр класса InkAnnotation, используя прямоугольник, список точек и страницу, на которую добавляется аннотация.

Затем мы устанавливаем различные свойства InkAnnotation, такие как заголовок, цвет, стиль заглавных букв, границы и непрозрачность. Наконец, мы добавляем аннотацию на страницу с помощью метода Annotations.Add.

## Шаг 3: Сохранение документа

Последним шагом является сохранение документа PDF с добавленной рукописной аннотацией. Это достигается с помощью следующего фрагмента кода:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Здесь мы объединяем имя выходного файла с каталогом данных и сохраняем документ с помощью метода Save.

### Пример исходного кода для добавления рукописной аннотации с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Сохранить выходной файл
doc.Save(dataDir);
```

## Заключение

В этом руководстве мы рассмотрели, как добавить рукописные аннотации в документ PDF с помощью Aspose.PDF для .NET. Следуя пошаговому руководству и предоставленному исходному коду C#, разработчики могут легко реализовать функциональные возможности рукописных аннотаций в своих приложениях для обработки PDF.

### Часто задаваемые вопросы

#### В: Что такое рукописная аннотация в документе PDF?

О: Аннотации рукописного ввода в документе PDF позволяют пользователям рисовать рукописные аннотации произвольной формы с помощью стилуса или мыши. Он обычно используется для добавления нарисованных от руки эскизов, диаграмм или других аннотаций от руки в PDF.

#### Вопрос. Можно ли настроить внешний вид рукописной аннотации?

О: Да, Aspose.PDF для .NET предоставляет различные свойства для настройки внешнего вида рукописной аннотации, такие как цвет, непрозрачность, стиль заглавных букв, ширина границы и многое другое. Разработчики могут настроить эти свойства в соответствии со своими конкретными требованиями.

#### В: Можно ли добавить несколько рукописных аннотаций на одну страницу PDF?

О: Да, вы можете добавить несколько рукописных аннотаций на одну страницу PDF, используя Aspose.PDF для .NET. Каждая рукописная аннотация может иметь собственный набор точек и индивидуальный внешний вид.

#### Вопрос. Можно ли добавлять рукописные аннотации к существующим документам PDF?

О: Да, Aspose.PDF для .NET позволяет добавлять рукописные аннотации как во вновь созданные PDF-документы, так и в существующие PDF-файлы. Вы можете открыть существующий PDF-файл, добавить рукописные аннотации и сохранить обновленный документ.

#### Вопрос: Каковы некоторые распространенные варианты использования рукописных аннотаций в документах PDF?

О: Аннотации, сделанные чернилами, полезны для широкого круга приложений, включая добавление подписей или рукописных заметок в формы PDF, комментирование архитектурных чертежей или инженерных чертежей, а также пометки документов для совместного просмотра.