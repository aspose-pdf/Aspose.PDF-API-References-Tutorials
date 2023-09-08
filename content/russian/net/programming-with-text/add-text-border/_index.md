---
title: Добавить текстовую рамку в PDF-файл
linktitle: Добавить текстовую рамку в PDF-файл
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавить рамку текста в файл PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-text/add-text-border/
---
Это руководство проведет вас через процесс добавления текстовой границы в PDF-файл с помощью Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файле кода, в который вы хотите добавить текстовую рамку, добавьте следующую директиву using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Создайте новый объект документа.
 Создать экземпляр нового`Document` объект, добавив следующую строку кода:

```csharp
Document pdfDocument = new Document();
```

## Шаг 5. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью`Add` метод`Pages`коллекция. В предоставленном коде новая страница присваивается переменной`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Шаг 6. Создайте TextFragment
 Создать`TextFragment` объект и укажите желаемый текст. Задайте положение фрагмента текста с помощью`Position` свойство. В предоставленном коде для текста установлено значение «основной текст» и он расположен на странице (100, 600).

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Шаг 7. Установите свойства текста
Настройте свойства текста, такие как размер шрифта, тип шрифта, цвет фона, цвет переднего плана и т. д. В предоставленном коде для фрагмента текста задаются такие свойства, как размер шрифта, шрифт, цвет фона, цвет переднего плана и цвет обводки.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Шаг 8. Включите текстовую рамку
 Чтобы включить рамку текста, установите`DrawTextRectangleBorder`свойство текстового фрагмента`TextState` к`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Шаг 9. Добавьте TextFragment на страницу.
 Использовать`TextBuilder` класс, чтобы добавить`TextFragment` объект на странице.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Шаг 10. Сохраните PDF-документ.
 Сохраните PDF-документ, используя`Save` метод`Document` объект. Укажите путь к выходному файлу, который вы установили на шаге 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Пример исходного кода для добавления текстовой границы с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать новый объект документа
Document pdfDocument = new Document();
// Получить конкретную страницу
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Создать фрагмент текста
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Установить свойства текста
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Установите свойство StrokingColor для рисования границы (обводки) вокруг текстового прямоугольника.
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Установите для свойства DrawTextRectangleBorder значение true.
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Сохраните документ
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Заключение
Вы успешно добавили текстовую рамку в свой PDF-документ с помощью Aspose.PDF для .NET. Полученный PDF-файл теперь можно найти по указанному пути к выходному файлу.

### Часто задаваемые вопросы

#### Вопрос: Какова основная цель этого урока?

О: В этом руководстве вы узнаете, как добавить рамку текста в PDF-файл с помощью библиотеки Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги для достижения этой цели.

#### Вопрос: Какие пространства имен мне нужно импортировать для работы с этим руководством?

О: В файле кода, в который вы хотите добавить рамку текста, импортируйте следующие пространства имен в начало файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Вопрос: Как указать каталог документа?

 О: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как создать объект «Документ»?

 О: На шаге 4 вы создадите новый экземпляр`Document` объект, используя следующую строку кода:

```csharp
Document pdfDocument = new Document();
```

#### Вопрос: Как добавить страницу в документ?

 О: На шаге 5 вы добавите в документ новую страницу, используя`Add` метод`Pages` коллекция:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Вопрос: Как создать TextFragment и установить его положение?

 О: На шаге 6 вы создадите`TextFragment`объект и установите его положение на странице с помощью`Position` свойство:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Вопрос: Как настроить свойства текста, включая рамку текста?

О: На шаге 7 вы настроите различные свойства текста, такие как размер шрифта, тип шрифта, цвет фона, цвет переднего плана и границу текста:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Вопрос: Как добавить TextFragment в документ PDF?

 О: На шаге 9 вы будете использовать`TextBuilder` класс, чтобы добавить`TextFragment` объект на странице:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Вопрос: Как сохранить полученный PDF-документ?

 О: После добавления текста с рамкой используйте`Save` метод`Document` объект для сохранения PDF-документа:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы успешно научились улучшать свой PDF-документ, добавляя текстовую рамку с помощью Aspose.PDF для .NET. Это может быть особенно полезно для выделения определенного текстового содержимого в файлах PDF.