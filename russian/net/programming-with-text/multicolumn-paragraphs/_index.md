---
title: Многоколоночные абзацы
linktitle: Многоколоночные абзацы
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как работать с абзацами из нескольких столбцов в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 250
url: /ru/net/programming-with-text/multicolumn-paragraphs/
---

В этом руководстве мы объясним, как работать с многоколоночными абзацами в документе PDF с использованием библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс управления и доступа к абзацам с несколькими столбцами, используя предоставленный исходный код C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором находится ваш входной PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir`переменная с путем к вашему файлу PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите PDF-документ

 Затем мы загружаем входной PDF-документ, используя`Document` класс из библиотеки Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## Шаг 3: Доступ к абзацам с несколькими столбцами

 Мы используем`ParagraphAbsorber`класс, чтобы поглощать и посещать параграфы в документе PDF. Затем мы извлекаем разметку страницы и получаем доступ к многоколоночным абзацам.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## Шаг 4. Работа с многоколоночными абзацами

Мы получаем доступ к определенным разделам и абзацам в многоколоночной структуре и печатаем их текст.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Доступ к последнему абзацу в разделе
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Доступ к первому абзацу в разделе
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Включение многоколоночных абзацев
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Доступ к последнему абзацу в разделе после включения абзацев с несколькими столбцами
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Доступ к первому абзацу в разделе после включения абзацев с несколькими столбцами
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Пример исходного кода для абзацев с несколькими столбцами с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## Заключение

В этом руководстве вы узнали, как работать с многоколоночными абзацами в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете получить доступ к абзацам с несколькими столбцами в документе PDF и управлять ими.