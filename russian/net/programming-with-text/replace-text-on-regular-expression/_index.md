---
title: Заменить текст в регулярном выражении
linktitle: Заменить регулярное выражение Texton
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как заменить текст на основе регулярного выражения в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 360
url: /ru/net/programming-with-text/replace-text-on-regular-expression/
---

В этом руководстве мы объясним, как заменить текст на основе регулярного выражения в документе PDF с помощью библиотеки Aspose.PDF для .NET. Мы предоставим пошаговое руководство вместе с необходимым исходным кодом C#.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Укажите путь к каталогу, в котором находится входной PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir`переменная с путем к вашему файлу PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите PDF-документ

 Загрузите документ PDF с помощью`Document` класс из библиотеки Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Шаг 3. Поиск и замена текста с помощью регулярного выражения

 Создать`TextFragmentAbsorber` объект и укажите шаблон регулярного выражения, чтобы найти все фразы, соответствующие шаблону. Установите параметр текстового поиска, чтобы разрешить использование регулярных выражений.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Вроде 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Шаг 4: Замените текст

Прокрутите извлеченные текстовые фрагменты и замените текст по мере необходимости. Обновите текст и другие свойства, такие как шрифт, размер шрифта, цвет переднего плана и цвет фона.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Шаг 5: Сохраните измененный PDF-файл

Сохраните измененный документ PDF в указанный выходной файл.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Пример исходного кода для замены регулярного выражения Texton с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Создайте объект TextAbsorber, чтобы найти все фразы, соответствующие регулярному выражению.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Вроде 1999-2000
// Установите параметр текстового поиска, чтобы указать использование регулярного выражения
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Примите поглотитель для одной страницы
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Получить извлеченные текстовые фрагменты
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебрать фрагменты
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Обновление текста и других свойств
	textFragment.Text = "New Phrase";
	// Установите экземпляр объекта.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве вы узнали, как заменить текст на основе регулярного выражения в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы сможете загрузить PDF-документ, выполнить поиск текста с помощью регулярного выражения, заменить его и сохранить измененный PDF-файл.