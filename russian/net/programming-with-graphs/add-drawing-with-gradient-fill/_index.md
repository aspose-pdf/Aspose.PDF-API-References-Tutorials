---
title: Добавить рисунок с градиентной заливкой
linktitle: Добавить рисунок с градиентной заливкой
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить рисунок с градиентной заливкой с помощью Aspose.PDF для .NET. Пошаговое руководство по созданию привлекательных PDF-документов.
type: docs
weight: 20
url: /ru/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
В этом руководстве мы шаг за шагом проведем вас через следующий исходный код C#, чтобы добавить рисунок с градиентной заливкой к программированию с графикой с использованием Aspose.PDF для .NET.

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
Page page = doc.Pages.Add();
```

## Шаг 3: Создание объекта графика и добавление его на страницу

Мы создаем объект Graph с указанными размерами и добавляем его в коллекцию абзацев страницы.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Шаг 4: Создайте прямоугольный объект и добавьте его в диаграмму

Мы создаем объект Rectangle с указанными размерами и добавляем его в коллекцию фигур диаграммы.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Шаг 5: Настройка градиентной заливки

Мы настраиваем градиентную заливку прямоугольника с помощью класса GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Это создает градиентную заливку от красного к синему, от точки (0, 0) до точки (300, 300).

## Шаг 6: Сохранение PDF-файла

Наконец, мы сохраняем полученный файл PDF с именем «AddDrawingWithGradientFill_out.pdf» в указанном каталоге.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Пример исходного кода для добавления рисунка с градиентной заливкой с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Заключение

В этом уроке мы шаг за шагом объяснили, как добавить рисунок с градиентной заливкой в программирование с графикой с использованием Aspose.PDF для .NET. Теперь вы можете использовать эти знания для создания привлекательных PDF-документов с индивидуальным дизайном и градиентной заливкой.