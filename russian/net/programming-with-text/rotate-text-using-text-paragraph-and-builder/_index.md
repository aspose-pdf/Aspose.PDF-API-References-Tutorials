---
title: Поворот текста с помощью текстового абзаца и конструктора
linktitle: Поворот текста с помощью текстового абзаца и конструктора
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как повернуть текст с помощью текстового абзаца и компоновщика в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 410
url: /ru/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поворота текста с помощью текстовых абзацев и компоновщиков. Предоставленный исходный код C# демонстрирует пошаговый процесс.

## Предпосылки

Прежде чем приступить к обучению, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования С#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете получить его с веб-сайта Aspose или использовать NuGet для установки в своем проекте.

## Шаг 1: Настройте проект

Начните с создания нового проекта C# в выбранной вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен

Добавьте следующие директивы using в начало файла C#, чтобы импортировать необходимые пространства имен:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Шаг 3: Создайте PDF-документ

 Инициализировать`Document` объект для создания нового документа PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

## Шаг 4: Добавьте страницу

 Получить определенную страницу из документа с помощью`Pages.Add()` метод:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Шаг 5: Создайте и поверните текстовые абзацы

 Создать`for` цикл для создания нескольких текстовых абзацев с разным поворотом:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Отрегулируйте значения положения и поворота в соответствии с вашими требованиями.

## Шаг 6: Создайте и настройте текстовые фрагменты

 Создать несколько`TextFragment`объектов, задайте их текст и свойства:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
```

Отрегулируйте текст и другие свойства по желанию.

## Шаг 7: Добавьте текстовые фрагменты к абзацу

 Добавьте созданные текстовые фрагменты к абзацу с помощью`AppendLine` метод:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Шаг 8: Создайте TextBuilder и добавьте абзац

 Создать`TextBuilder` объект с помощью`pdfPage` и добавьте текстовый абзац на страницу PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## Шаг 9: Сохраните PDF-документ

 Сохраните измененный PDF-документ в файл с помощью`Save` метод:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 Обязательно замените`"TextFragmentTests_Rotated4_out.pdf"` с желаемым именем выходного файла.

## Заключение

Поздравляем! Вы успешно научились поворачивать текст, используя текстовые абзацы и компоновщики в документе PDF, используя Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от создания документа до сохранения измененной версии. Теперь вы можете включить этот код в свои собственные проекты C# для управления поворотом текста в файлах PDF.

### Пример исходного кода для поворота текста с использованием текстового абзаца и построителя с использованием Aspose.PDF для .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Инициализировать объект документа
Document pdfDocument = new Document();
// Получить конкретную страницу
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Укажите поворот
	paragraph.Rotation = i * 90 + 45;
	// Создать текстовый фрагмент
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Создать текстовый фрагмент
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Создать текстовый фрагмент
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Установить свойства текста
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Создать текстовый фрагмент
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// Установить свойства текста
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// Создать объект TextBuilder
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Добавить текстовый фрагмент на страницу PDF
	textBuilder.AppendParagraph(paragraph);
}
// Сохранить документ
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```