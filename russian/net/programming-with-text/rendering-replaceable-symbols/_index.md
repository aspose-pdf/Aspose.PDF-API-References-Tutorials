---
title: Отображение заменяемых символов
linktitle: Отображение заменяемых символов
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как визуализировать заменяемые символы в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 310
url: /ru/net/programming-with-text/rendering-replaceable-symbols/
---

В этом руководстве мы объясним, как визуализировать заменяемые символы в документе PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим пошаговый процесс создания PDF-файла, добавления текстового фрагмента с маркерами новой строки, настройки свойств текста, позиционирования текста и сохранения PDF-файла с использованием предоставленного исходного кода C#.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором вы хотите сохранить сгенерированный файл PDF. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к нужному каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте PDF-документ и страницу

Далее мы создаем новый PDF-документ и добавляем в него страницу с помощью`Document` класс и`Page` класс из библиотеки Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Шаг 3: добавьте фрагмент текста с маркерами новой строки

 Мы создаем`TextFragment` объект и установите его текст, чтобы он включал маркеры новой строки (`Environment.NewLine`) для представления нескольких строк текста.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Шаг 4: Установите свойства текстового фрагмента

При желании мы можем установить различные свойства для текстового фрагмента, такие как размер шрифта, шрифт, цвет фона и цвет переднего плана.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Шаг 5: Создайте текстовый абзац и позицию

 Мы создаем`TextParagraph` объект, добавить текстовый фрагмент к абзацу и установить положение абзаца на странице.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Шаг 6: Добавьте текстовый абзац на страницу

 Мы создаем`TextBuilder` объект со страницей и добавьте текстовый абзац в построитель текста.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Шаг 7: Сохраните PDF-документ

Наконец, мы сохраняем документ PDF в указанный выходной файл.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Пример исходного кода для рендеринга заменяемых символов с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Инициализировать новый TextFragment текстом, содержащим необходимые маркеры новой строки
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// При необходимости задайте свойства текстового фрагмента
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Создать объект TextParagraph
TextParagraph par = new TextParagraph();
// Добавить новый TextFragment в абзац
par.AppendLine(textFragment);
// Установить позицию абзаца
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Создать объект TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Добавьте TextParagraph с помощью TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве вы узнали, как визуализировать заменяемые символы в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете создать PDF-файл, добавить текст с маркерами новой строки, задать свойства текста, расположить текст на странице и сохранить PDF-файл.