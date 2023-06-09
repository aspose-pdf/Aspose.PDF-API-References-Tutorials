---
title: Добавить прозрачный текст
linktitle: Добавить прозрачный текст
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить прозрачный текст в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-text/add-transparent-text/
---

Это руководство проведет вас через процесс добавления прозрачного текста в документ PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файл кода, в который вы хотите добавить прозрачный текст, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Создайте новый экземпляр документа
 Создать новый`Document` объекта, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью кнопки`Add` метод`Pages` коллекция. В предоставленном коде новая страница назначается переменной`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Шаг 6: Создайте объект Graph
 Создать новый`Graph` объект с определенной шириной и высотой.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Шаг 7: Создайте прямоугольник с прозрачностью
Создайте прямоугольник с определенными размерами и установите для его заливки прозрачный цвет с помощью`Color.FromRgb` метод.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Шаг 8: Добавьте объект Graph на страницу
 Добавить`Graph` возражать против коллекции абзацев страницы.

```csharp
page.Paragraphs.Add(canvas);
```

## Шаг 9: Установите положение для объекта Graph
 Установить`IsChangePosition` собственность`Graph` Возражать`false` для предотвращения изменения его положения.

```csharp
canvas. IsChangePosition = false;
```

## Шаг 10: Создайте TextFragment с прозрачностью
 Создать`TextFragment` объект и установите его содержимое в желаемый текст. Установить`ForegroundColor` собственность`TextState` к цвету с прозрачностью с помощью`Color.FromArgb` метод.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Шаг 11: Сохраните PDF-документ
 Сохраните документ PDF с помощью`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Пример исходного кода для добавления прозрачного текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр документа
Document doc = new Document();
// Создать постраничную коллекцию PDF-файла
Aspose.Pdf.Page page = doc.Pages.Add();
// Создать объект графика
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Создать экземпляр прямоугольника с определенными размерами
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Создать цветовой объект из цветового канала Alpha
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Добавить прямоугольник в коллекцию фигур объекта Graph
canvas.Shapes.Add(rect);
// Добавить объект графика в коллекцию абзацев объекта страницы
page.Paragraphs.Add(canvas);
// Установите значение, чтобы не менять позицию для графического объекта
canvas.IsChangePosition = false;
// Создайте экземпляр TextFragment с образцом значения
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Создать цветовой объект из альфа-канала
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
//Установить информацию о цвете для экземпляра текста
text.TextState.ForegroundColor = color;
// Добавить текст в коллекцию абзацев экземпляра страницы
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Заключение
Вы успешно добавили прозрачный текст в свой PDF-документ, используя Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.