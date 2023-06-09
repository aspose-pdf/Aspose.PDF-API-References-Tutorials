---
title: Поворот текста с использованием текстового фрагмента и абзаца
linktitle: Поворот текста с использованием текстового фрагмента и абзаца
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как повернуть текст, используя текстовый фрагмент и абзац в документе PDF, используя Aspose.PDF для .NET.
type: docs
weight: 400
url: /ru/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поворота текста с использованием текстового фрагмента и абзаца. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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

## Шаг 5: Создайте текстовые фрагменты

 Создать несколько`TextFragment` объектов, задать их текст и свойства, а также указать угол поворота:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Отрегулируйте текст, угол поворота и другие свойства по желанию.

## Шаг 6: Добавьте текстовые фрагменты на страницу

 Добавьте созданные текстовые фрагменты на страницу, добавив их в`Paragraphs` коллекция:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Шаг 7: Сохраните PDF-документ

 Сохраните измененный PDF-документ в файл с помощью`Save` метод:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Обязательно замените`"TextFragmentTests_Rotated3_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для поворота текста с использованием текстового фрагмента и абзаца с использованием Aspose.PDF для .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Инициализировать объект документа
Document pdfDocument = new Document();
// Получить конкретную страницу
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Создать текстовый фрагмент
TextFragment textFragment1 = new TextFragment("main text");
// Установить свойства текста
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Создать текстовый фрагмент
TextFragment textFragment2 = new TextFragment("rotated text");
// Установить свойства текста
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Установить вращение
textFragment2.TextState.Rotation = 315;
// Создать текстовый фрагмент
TextFragment textFragment3 = new TextFragment("rotated text");
// Установить свойства текста
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Установить вращение
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Сохранить документ
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Заключение

Поздравляем! Вы успешно научились поворачивать текст, используя текстовые фрагменты и абзацы в документе PDF, используя Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от создания документа до сохранения измененной версии. Теперь вы можете включить этот код в свои собственные проекты C# для управления поворотом текста в файлах PDF.