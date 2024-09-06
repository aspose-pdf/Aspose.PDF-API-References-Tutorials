---
title: Линия рисования
linktitle: Линия рисования
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как нарисовать линию на странице с помощью Aspose.PDF для .NET. Пошаговое руководство по созданию пользовательских линий.
type: docs
weight: 80
url: /ru/net/programming-with-graphs/drawing-line/
---
В этом уроке мы шаг за шагом разберем следующий исходный код C#, как нарисовать линию с помощью Aspose.PDF для .NET.

Убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки, прежде чем начать. Также имейте базовые знания программирования на C#.

## Шаг 1: Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором вы хотите сохранить полученный PDF-файл. Измените переменную "dataDir" на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание экземпляра документа и добавление страницы

Мы создаем экземпляр класса Document и добавляем страницу в этот документ.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Шаг 3: Установка полей страницы

Мы устанавливаем поля страницы на 0 со всех сторон.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Шаг 4: Создание графического объекта и первой линии

Создаем объект Graph с размерами, равными размерам страницы, и рисуем первую линию, идущую из нижнего левого угла в верхний правый угол страницы.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Шаг 5: Рисование второй линии

Рисуем вторую линию, идущую из верхнего левого угла в нижний правый угол страницы.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Шаг 6: Добавление объекта «График» на страницу

Мы добавляем объект Graph в коллекцию абзацев страницы.

```csharp
pg.Paragraphs.Add(graph);
```

## Шаг 7: Сохранение полученного PDF-файла

Наконец, сохраняем полученный PDF-файл под именем «DrawingLine_out.pdf» в указанном каталоге.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Пример исходного кода для рисования линии с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр документа
Document pDoc = new Document();
// Добавить страницу в коллекцию страниц документа PDF
Page pg = pDoc.Pages.Add();
// Установить поля страницы со всех сторон равными 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Создать объект Graph с шириной и высотой, равными размерам страницы.
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Создайте первый линейный объект, начиная с нижнего левого угла страницы и до правого верхнего угла.
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Добавить линию в коллекцию фигур объекта Graph
graph.Shapes.Add(line);
// Проведите линию от верхнего левого угла страницы до нижнего правого угла страницы.
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Добавить линию в коллекцию фигур объекта Graph
graph.Shapes.Add(line2);
// Добавить объект Graph в коллекцию абзацев страницы
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Сохранить PDF-файл
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Заключение

В этом уроке мы объяснили, как нарисовать линию с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для создания геометрических фигур с пользовательскими линиями в ваших файлах PDF.

### Часто задаваемые вопросы

#### В: Какова цель этого урока?

A: Цель этого руководства — провести вас через процесс рисования линий с помощью Aspose.PDF для .NET. Вы узнаете, как создавать линии на странице PDF и настраивать их внешний вид.

#### В: Какие предварительные условия необходимы перед началом работы?

A: Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также рекомендуются базовые знания программирования на C#.

#### В: Как указать каталог для сохранения PDF-файла?

A: Измените переменную «dataDir» в предоставленном исходном коде, чтобы указать каталог, в котором вы хотите сохранить полученный PDF-файл.

#### В: Как создать линии на странице PDF-файла?

A: В руководстве показано создание объекта Graph с размерами страницы, а затем добавление к нему объектов Line. Измените координаты и свойства объектов Line, чтобы создать нужные линии.

#### В: Могу ли я настроить внешний вид линий?

A: Да, вы можете настроить внешний вид линий, изменив свойства объектов Line. Это включает изменение их координат, цвета, толщины и других графических атрибутов.

#### В: Как сохранить PDF-документ после рисования линий?

 A: После добавления объекта «График» с объектами «Линия» на страницу вы можете сохранить полученный PDF-документ с помощью`pDoc.Save(dataDir + "DrawingLine_out.pdf");` строка в предоставленном исходном коде.

#### В: Могу ли я рисовать линии под разными углами и в разных направлениях?

A: Да, вы можете рисовать линии под разными углами и в разных ориентациях, изменяя координаты и свойства объектов Line в графике.