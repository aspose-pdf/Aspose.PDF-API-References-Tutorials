---
title: Добавить границу текста в PDF-файл
linktitle: Добавить границу текста в PDF-файл
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как добавить рамку для текста в PDF-файл с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-text/add-text-border/
---
Этот урок проведет вас через процесс добавления текстовой границы в файл PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, где вы хотите добавить текстовую рамку, добавьте следующую директиву using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Укажите каталог документа
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

## Шаг 4: Создайте новый объект «Документ»
 Создать новый экземпляр`Document` объект, добавив следующую строку кода:

```csharp
Document pdfDocument = new Document();
```

## Шаг 5: Добавьте страницу в документ
 Добавьте новую страницу в документ, используя`Add` Метод`Pages`Коллекция. В представленном коде новая страница присваивается переменной`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Шаг 6: Создание текстового фрагмента
 Создать`TextFragment` объект и укажите нужный текст. Установите положение фрагмента текста с помощью`Position` свойство. В предоставленном коде текст установлен как «основной текст» и размещен в точке (100, 600) на странице.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Шаг 7: Задайте свойства текста
Настройте свойства текста, такие как размер шрифта, тип шрифта, цвет фона, цвет переднего плана и т. д. В предоставленном коде для фрагмента текста задаются такие свойства, как размер шрифта, шрифт, цвет фона, цвет переднего плана и цвет обводки.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Шаг 8: Включите границу текста
 Чтобы включить границу текста, установите`DrawTextRectangleBorder`свойство фрагмента текста`TextState` к`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Шаг 9: Добавьте TextFragment на страницу
 Используйте`TextBuilder` класс для добавления`TextFragment` возразить против страницы.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Шаг 10: Сохраните PDF-документ.
 Сохраните PDF-документ с помощью`Save` Метод`Document` объект. Укажите путь к выходному файлу, который вы задали в Шаге 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Пример исходного кода для добавления текстовой границы с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать новый объект документа
Document pdfDocument = new Document();
// Получить определенную страницу
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Создать фрагмент текста
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Установить свойства текста
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Установите свойство StrokingColor для рисования границы (обводки) вокруг текстового прямоугольника
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Установите для свойства DrawTextRectangleBorder значение true.
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Сохранить документ
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Заключение
Вы успешно добавили текстовую границу в ваш PDF-документ с помощью Aspose.PDF для .NET. Полученный PDF-файл теперь можно найти по указанному пути выходного файла.

### Часто задаваемые вопросы

#### В: Какова основная тема этого урока?

A: Это руководство проведет вас через процесс добавления текстовой границы в файл PDF с помощью библиотеки Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги для достижения этого.

#### В: Какие пространства имен мне необходимо импортировать для этого руководства?

A: В файле кода, куда вы хотите добавить текстовую границу, импортируйте следующие пространства имен в начале файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### В: Как указать каталог документа?

 A: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

#### В: Как создать объект «Документ»?

 A: На шаге 4 вы создадите новый экземпляр`Document` объект, используя следующую строку кода:

```csharp
Document pdfDocument = new Document();
```

#### В: Как добавить страницу в документ?

 A: На шаге 5 вы добавите новую страницу в документ с помощью`Add` Метод`Pages` коллекция:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### В: Как создать TextFragment и задать его положение?

 A: На шаге 6 вы создадите`TextFragment`объект и задайте его положение на странице с помощью`Position` свойство:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### В: Как настроить свойства текста, включая рамку текста?

A: На шаге 7 вы настроите различные свойства текста, такие как размер шрифта, тип шрифта, цвет фона, цвет переднего плана и границу текста:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### В: Как добавить TextFragment в PDF-документ?

 A: На шаге 9 вы будете использовать`TextBuilder` класс для добавления`TextFragment` возразить против страницы:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### В: Как сохранить полученный PDF-документ?

 A: После добавления текста с рамкой используйте`Save` Метод`Document` объект для сохранения PDF-документа:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы успешно узнали, как улучшить ваш PDF-документ, добавив текстовую границу с помощью Aspose.PDF для .NET. Это может быть особенно полезно для выделения определенного текстового содержимого в ваших PDF-файлах.