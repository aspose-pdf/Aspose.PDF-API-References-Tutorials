---
title: Заменить весь текст
linktitle: Заменить весь текст
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как заменить весь текст в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 350
url: /ru/net/programming-with-text/replace-text-all/
---

В этом руководстве мы объясним, как заменить весь текст в документе PDF с помощью библиотеки Aspose.PDF для .NET. Мы предоставим пошаговое руководство вместе с необходимым исходным кодом C#.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Шаг 3: Найдите и замените текст

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы. Примите поглотитель для всех страниц PDF-документа, чтобы извлечь текстовые фрагменты.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 4: Замените текст

Прокрутите извлеченные текстовые фрагменты и замените текст по мере необходимости. Обновите текст и другие свойства, такие как шрифт, размер шрифта, цвет переднего плана и цвет фона.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Шаг 5: Сохраните измененный PDF-файл

Сохраните измененный документ PDF в указанный выходной файл.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Пример исходного кода для замены текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
//Создайте объект TextAbsorber, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Примите поглотитель для всех страниц
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Получить извлеченные текстовые фрагменты
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебрать фрагменты
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Обновление текста и других свойств
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Сохраните полученный PDF-документ.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве вы узнали, как заменить весь текст в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете загрузить PDF-документ, найти нужный текст, заменить его и сохранить измененный PDF-файл.