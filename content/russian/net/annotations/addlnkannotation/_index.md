---
title: Добавить аннотацию lnk
linktitle: Добавить аннотацию lnk
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавить функцию рукописных аннотаций в PDF-документы на C# с помощью Aspose.PDF для .NET, с пошаговым руководством и полным исходным кодом.
type: docs
weight: 20
url: /ru/net/annotations/addlnkannotation/
---
Aspose.PDF для .NET — это мощная библиотека, позволяющая разработчикам выполнять различные операции с PDF. Одной из таких операций является добавление рукописных аннотаций в PDF-документы. В этой статье мы предоставим пошаговое руководство, объясняющее исходный код C# для добавления рукописных аннотаций с использованием Aspose.PDF для .NET. Давайте начнем!

## Понимание функции рукописных аннотаций Aspose.PDF для .NET

Прежде чем углубляться в исходный код C#, давайте сначала разберемся, что такое рукописные аннотации и как они используются.

Рукописные аннотации — это способ создания рукописных аннотаций произвольной формы в PDF-документах. Он позволяет создавать аннотации с помощью стилуса или мыши. Эта функция полезна в ситуациях, когда вам нужно нарисовать диаграммы, эскизы или другие типы аннотаций.

## Шаг 1. Создание нового документа

Первым шагом в добавлении рукописной аннотации в PDF-документ является создание нового экземпляра класса Document. Это достигается с помощью следующего фрагмента кода:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Здесь мы создаем новый экземпляр класса Document и добавляем к нему новую страницу.

## Шаг 2. Создание рукописной аннотации

Следующим шагом будет создание экземпляра класса InkAnnotation. Это делается с помощью следующего фрагмента кода:

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

Здесь мы сначала создаем прямоугольник, используя класс System.Drawing.Rectangle, и преобразуем его в Aspose.Pdf.Rectangle, используя метод FromRect. Затем мы создаем экземпляр класса InkAnnotation, используя прямоугольник, список точек и страницу, на которую добавляется аннотация.

Затем мы устанавливаем различные свойства InkAnnotation, такие как заголовок, цвет, стиль шапки, граница и непрозрачность. Наконец, мы добавляем аннотацию на страницу, используя метод Annotations.Add.

## Шаг 3: Сохранение документа

Последний шаг — сохранить документ PDF с добавленной рукописной аннотацией. Это достигается с помощью следующего фрагмента кода:

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

В этом уроке мы рассмотрели, как добавить рукописные аннотации в PDF-документ с помощью Aspose.PDF для .NET. Следуя пошаговому руководству и предоставленному исходному коду C#, разработчики могут легко реализовать функцию рукописных аннотаций в своих приложениях для обработки PDF-файлов.

### Часто задаваемые вопросы

#### Вопрос: Что такое рукописная аннотация в PDF-документе?

О: Рукописная аннотация в PDF-документе позволяет пользователям рисовать рукописные аннотации произвольной формы с помощью стилуса или мыши. Обычно он используется для добавления в PDF-файл нарисованных от руки эскизов, диаграмм или других аннотаций от руки.

#### Вопрос: Могу ли я настроить внешний вид рукописной аннотации?

О: Да, Aspose.PDF для .NET предоставляет различные свойства для настройки внешнего вида рукописной аннотации, такие как цвет, непрозрачность, стиль заглавия, ширина границы и т. д. Разработчики могут настроить эти свойства в соответствии со своими конкретными требованиями.

#### Вопрос: Можно ли добавить несколько рукописных аннотаций на одну страницу PDF?

О: Да, вы можете добавить несколько рукописных аннотаций на одну страницу PDF, используя Aspose.PDF для .NET. Каждая рукописная аннотация может иметь собственный набор точек и индивидуальный внешний вид.

#### Вопрос: Могу ли я добавлять рукописные аннотации к существующим PDF-документам?

О: Да, Aspose.PDF для .NET позволяет добавлять рукописные аннотации как к вновь создаваемым PDF-документам, так и к существующим PDF-файлам. Вы можете открыть существующий PDF-файл, добавить рукописные аннотации и сохранить обновленный документ.

#### Вопрос: Каковы наиболее распространенные случаи использования рукописных аннотаций в документах PDF?

Ответ: Рукописные аннотации полезны для широкого спектра приложений, включая добавление подписей или рукописных заметок в формы PDF, аннотирование архитектурных чертежей или инженерных чертежей, а также разметку документов для совместного просмотра.