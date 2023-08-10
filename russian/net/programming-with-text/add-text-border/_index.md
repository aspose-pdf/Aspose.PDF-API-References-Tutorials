---
title: Добавить границу текста
linktitle: Добавить границу текста
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить текстовую рамку в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-text/add-text-border/
---

Это руководство проведет вас через процесс добавления рамки текста с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файле кода, где вы хотите добавить текстовую границу, добавьте следующую директиву using вверху файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Создайте новый объект документа
 Создать новый`Document` объекта, добавив следующую строку кода:

```csharp
Document pdfDocument = new Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью кнопки`Add` метод`Pages` коллекция. В предоставленном коде новая страница назначается переменной`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Шаг 6: Создайте TextFragment
 Создать`TextFragment`объект и предоставить желаемый текст. Задайте положение фрагмента текста с помощью`Position` свойство. В предоставленном коде текст установлен как «основной текст» и расположен в (100, 600) на странице.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Шаг 7: Установите свойства текста
Настройте свойства текста, такие как размер шрифта, тип шрифта, цвет фона, цвет переднего плана и т. д. В предоставленном коде для текстового фрагмента задаются такие свойства, как размер шрифта, шрифт, цвет фона, цвет переднего плана и цвет обводки.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Шаг 8. Включите рамку текста
 Чтобы включить текстовую рамку, установите`DrawTextRectangleBorder` свойство фрагмента текста`TextState` к`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Шаг 9: Добавьте TextFragment на страницу
 Использовать`TextBuilder` класс, чтобы добавить`TextFragment` объект на странице.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Шаг 10: Сохраните PDF-документ
 Сохраните документ PDF с помощью`Save` метод`Document` объект. Укажите путь к выходному файлу, заданный на шаге 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Пример исходного кода для добавления границы текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать новый объект документа
Document pdfDocument = new Document();
// Получить конкретную страницу
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Создать текстовый фрагмент
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Установить свойства текста
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Установите свойство StrokingColor для рисования границы (обводки) вокруг текстового прямоугольника
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Установите для свойства DrawTextRectangleBorder значение true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Сохраните документ
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Заключение
Вы успешно добавили текстовую рамку в документ PDF с помощью Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.