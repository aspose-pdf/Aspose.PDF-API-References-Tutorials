---
title: Создать прямоугольник с альфа-цветом
linktitle: Создать прямоугольник с альфа-цветом
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как создать прямоугольник с прозрачным цветом с помощью Aspose.PDF для .NET. Пошаговое руководство по настройке прозрачности.
type: docs
weight: 60
url: /ru/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
В этом уроке мы шаг за шагом рассмотрим следующий исходный код C#, чтобы создать прямоугольник с альфа-цветом с помощью Aspose.PDF для .NET.

Убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки, прежде чем начать. Также имейте базовые знания программирования на C#.

## Шаг 1: Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором вы хотите сохранить полученный PDF-файл. Измените переменную "dataDir" на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание объекта документа и добавление страницы

Мы создаем экземпляр класса Document и добавляем страницу в этот документ.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Шаг 3: Создание графического объекта и прямоугольника

Мы создаем объект Graph с указанными размерами и прямоугольник с указанными размерами.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Шаг 4: Настройка альфа-цвета для прямоугольника

Мы можем указать альфа-цвет для прямоугольника, используя метод FromArgb класса System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Шаг 5: Добавление прямоугольника к объекту графика

Добавляем прямоугольник в коллекцию фигур объекта Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Шаг 6: Создание второго прямоугольника с другим альфа-цветом

Мы создаем второй прямоугольник с определенными размерами и другим альфа-цветом.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Шаг 7: Добавление объекта «График» на страницу

Мы добавляем объект Graph в коллекцию Paragraph объекта Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Шаг 8: Сохранение полученного PDF-файла

Наконец, сохраняем полученный PDF-файл под именем «CreateRectangleWithAlphaColor_out.pdf» в указанном каталоге.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Пример исходного кода для создания прямоугольника с альфа-цветом с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр документа
Document doc = new Document();
// Добавить страницу в коллекцию страниц PDF-файла
Aspose.Pdf.Page page = doc.Pages.Add();
// Создать экземпляр графика
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Создать прямоугольный объект с определенными размерами
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Установить цвет заливки графика из структуры System.Drawing.Color из 32-битного значения ARGB
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Добавить объект прямоугольника в коллекцию фигур экземпляра Graph
canvas.Shapes.Add(rect);
// Создать второй прямоугольный объект
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Добавить экземпляр графика в коллекцию абзацев объекта страницы
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Сохранить PDF-файл
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Заключение

В этом уроке мы объяснили, как создать прямоугольник с альфа-цветом, используя Aspose.PDF для .NET. Теперь вы можете использовать эти знания для создания геометрических фигур с прозрачными цветами в ваших файлах PDF.

## Часто задаваемые вопросы

#### В: Какова цель этого урока?

A: Цель этого руководства — провести вас через процесс создания прямоугольника с альфа-цветом с помощью Aspose.PDF для .NET. Вы узнаете, как добавлять геометрические фигуры с прозрачными цветами в ваши файлы PDF.

#### В: Какие предварительные условия необходимы перед началом работы?

A: Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Кроме того, рекомендуется иметь базовые знания программирования на C#.

#### В: Как указать каталог для сохранения PDF-файла?

A: В предоставленном исходном коде вы можете изменить переменную «dataDir», чтобы указать каталог, в котором вы хотите сохранить полученный PDF-файл.

#### В: Каково назначение объектов «График» и «Прямоугольник»?

A: Объект «График» выступает в качестве контейнера для элементов чертежа, а «Прямоугольник» представляет собой геометрическую фигуру, которую вы добавите в PDF-файл.

#### В: Как настроить альфа-цвет для прямоугольника?

 A: Вы можете указать альфа-цвет для прямоугольника с помощью`FillColor` собственность`GraphInfo` объект и`Color.FromRgb` метод со значением ARGB.

#### В: Могу ли я создать несколько прямоугольников с разными альфа-цветами?

A: Да, вы можете создать несколько прямоугольников с разными альфа-цветами, выполнив действия, аналогичные показанным в руководстве.

#### В: Как сохранить полученный PDF-файл после создания прямоугольников с альфа-цветами?

 A: После создания прямоугольников с альфа-цветами вы можете сохранить полученный PDF-файл с помощью`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` строка в предоставленном исходном коде.