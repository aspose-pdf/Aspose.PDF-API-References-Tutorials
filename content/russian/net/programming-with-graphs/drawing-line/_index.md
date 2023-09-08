---
title: Рисование линии
linktitle: Рисование линии
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как нарисовать линию на странице с помощью Aspose.PDF для .NET. Пошаговое руководство по созданию нестандартных линий.
type: docs
weight: 80
url: /ru/net/programming-with-graphs/drawing-line/
---
В этом руководстве мы шаг за шагом познакомим вас со следующим исходным кодом C#, чтобы нарисовать линию с помощью Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

## Шаг 1. Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором вы хотите сохранить полученный PDF-файл. Измените переменную dataDir на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создание экземпляра документа и добавление страницы

Мы создаем экземпляр класса Document и добавляем страницу в этот документ.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Шаг 3. Настройка полей страницы

Мы устанавливаем поля страницы на 0 со всех сторон.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Шаг 4. Создание объекта графика и первой линии

Мы создаем объект Graph с размерами, равными размерам страницы, и рисуем первую линию, идущую из левого нижнего угла в правый верхний угол страницы.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Шаг 5: Рисуем вторую линию

Рисуем вторую линию, идущую из левого верхнего угла в правый нижний угол страницы.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Шаг 6. Добавление объекта графика на страницу

Мы добавляем объект Graph в коллекцию абзацев страницы.

```csharp
pg.Paragraphs.Add(graph);
```

## Шаг 7. Сохранение полученного PDF-файла

Наконец, сохраняем полученный PDF-файл с именем «DrawingLine_out.pdf» в указанном каталоге.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Пример исходного кода для рисования линий с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр документа
Document pDoc = new Document();
// Добавить страницу в коллекцию страниц PDF-документа
Page pg = pDoc.Pages.Add();
// Установите поля страницы со всех сторон равными 0.
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Создайте объект Graph с шириной и высотой, равными размерам страницы.
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Создайте объект первой строки, начиная с нижнего левого угла страницы и заканчивая верхним правым.
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Добавить линию в коллекцию фигур объекта Graph
graph.Shapes.Add(line);
// Нарисуйте линию от верхнего левого угла страницы до нижнего правого угла страницы.
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

В этом уроке мы объяснили, как нарисовать линию с помощью Aspose.PDF для .NET. Теперь вы можете использовать эти знания для создания геометрических фигур с произвольными линиями в ваших PDF-файлах.

### Часто задаваемые вопросы

#### Вопрос: Какова цель этого урока?

О: Цель этого руководства — провести вас через процесс рисования линий с помощью Aspose.PDF для .NET. Вы узнаете, как создавать линии на странице PDF и настраивать их внешний вид.

#### Вопрос: Какие предварительные условия необходимы перед запуском?

О: Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также приветствуются базовые знания программирования на C#.

#### Вопрос: Как указать каталог для сохранения PDF-файла?

О: Измените переменную «dataDir» в предоставленном исходном коде, чтобы указать каталог, в котором вы хотите сохранить полученный PDF-файл.

#### Вопрос: Как создать линии на странице PDF?

О: В учебнике показано создание объекта «График» с размерами страницы и последующее добавление к нему объектов «Линия». Измените координаты и свойства объектов Line, чтобы создать нужные линии.

#### Вопрос: Могу ли я настроить внешний вид линий?

О: Да, вы можете настроить внешний вид линий, изменив свойства объектов «Линия». Сюда входит изменение их координат, цвета, толщины и других графических атрибутов.

#### Вопрос: Как сохранить PDF-документ после рисования линий?

О: После добавления на страницу объекта «График» с объектами «Линия» полученный PDF-документ можно сохранить с помощью`pDoc.Save(dataDir + "DrawingLine_out.pdf");` строку в предоставленном исходном коде.

#### Вопрос: Могу ли я рисовать линии под разными углами и ориентацией?

О: Да, вы можете рисовать линии под разными углами и ориентацией, регулируя координаты и свойства объектов «Линия» на графике.