---
title: Создайте прямоугольник с альфа-цветом
linktitle: Создайте прямоугольник с альфа-цветом
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как создать прямоугольник с прозрачным цветом, используя Aspose.PDF для .NET. Пошаговое руководство по настройке прозрачности.
type: docs
weight: 60
url: /ru/net/programming-with-graphs/create-rectangle-with-alpha-color/
---

В этом руководстве мы шаг за шагом проведем вас через следующий исходный код C#, чтобы создать прямоугольник с альфа-цветом, используя Aspose.PDF для .NET.

Прежде чем начать, убедитесь, что вы установили библиотеку Aspose.PDF и настроили среду разработки. Также есть базовые знания программирования на C#.

## Шаг 1: Настройка каталога документов

В предоставленном исходном коде вам необходимо указать каталог, в котором вы хотите сохранить полученный PDF-файл. Измените переменную «dataDir» на нужный каталог.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создание экземпляра объекта документа и добавление страницы

Мы создаем экземпляр класса Document и добавляем в этот документ страницу.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Шаг 3: Создание графического объекта и прямоугольника

Мы создаем объект Graph с указанными размерами и прямоугольник с определенными размерами.

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

Мы добавляем прямоугольник в коллекцию фигур объекта Graph.

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

## Шаг 7: Добавление объекта графика на страницу

Мы добавляем объект Graph в коллекцию Paragraph объекта Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Шаг 8: Сохранение полученного PDF-файла

Наконец, мы сохраняем полученный файл PDF с именем «CreateRectangleWithAlphaColor_out.pdf» в указанном каталоге.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Пример исходного кода для создания прямоугольника с альфа-цветом с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр документа
Document doc = new Document();
// Добавить страницу в коллекцию страниц файла PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Создать экземпляр графа
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Создать прямоугольный объект с определенными размерами
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Установите цвет заливки графика из структуры System.Drawing.Color из 32-битного значения ARGB.
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
//Добавить прямоугольный объект в коллекцию фигур экземпляра Graph
canvas.Shapes.Add(rect);
// Создайте второй прямоугольный объект
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
