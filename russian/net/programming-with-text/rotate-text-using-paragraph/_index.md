---
title: Поворот текста с помощью абзаца
linktitle: Поворот текста с помощью абзаца
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как повернуть текст с помощью абзацев в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 380
url: /ru/net/programming-with-text/rotate-text-using-paragraph/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поворота текста с помощью абзацев. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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

## Шаг 5: Создайте текстовый абзац

 Создать`TextParagraph` объект и установить его положение на странице:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Отрегулируйте значения положения в соответствии с вашими требованиями.

## Шаг 6: Создайте и настройте текстовые фрагменты

 Создать несколько`TextFragment`объекты и установить их текст и свойства:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
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
```

## Шаг 9: Сохраните PDF-документ

 Сохраните измененный PDF-документ в файл с помощью`Save` метод:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 Обязательно замените`"TextFragmentTests_Rotated2_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для поворота текста с помощью абзаца с использованием Aspose.PDF для .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Инициализировать объект документа
Document pdfDocument = new Document();
// Получить конкретную страницу
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Создать текстовый фрагмент
TextFragment textFragment1 = new TextFragment("rotated text");
// Установить свойства текста
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Установить вращение
textFragment1.TextState.Rotation = 45;
// Создать текстовый фрагмент
TextFragment textFragment2 = new TextFragment("main text");
// Установить свойства текста
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Создать текстовый фрагмент
TextFragment textFragment3 = new TextFragment("another rotated text");
// Установить свойства текста
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Установить вращение
textFragment3.TextState.Rotation = -45;
// Присоединить фрагменты текста к абзацу
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Создать объект TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Добавить текстовый абзац на страницу PDF
textBuilder.AppendParagraph(paragraph);
// Сохранить документ
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Заключение

Поздравляем! Вы успешно научились поворачивать текст с помощью абзацев в документе PDF с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от создания документа до сохранения измененной версии. Теперь вы можете включить этот код в свои собственные проекты C# для управления поворотом текста в файлах PDF.