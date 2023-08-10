---
title: Заменить первое вхождение
linktitle: Заменить первое вхождение
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как заменить первое вхождение текста в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 330
url: /ru/net/programming-with-text/replace-first-occurrence/
---

В этом руководстве мы объясним, как заменить первое вхождение определенного текста в документе PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим пошаговый процесс открытия PDF-документа, нахождения первого вхождения искомой фразы, замены текста, обновления свойств и сохранения измененного PDF-файла с использованием предоставленного исходного кода C#.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором находится входной PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir`переменная с путем к вашему файлу PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте PDF-документ

 Затем мы открываем документ PDF с помощью`Document` класс из библиотеки Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Шаг 3. Найдите первое вхождение искомой фразы

 Мы создаем`TextFragmentAbsorber` объект и принять его для всех страниц PDF-документа, чтобы найти все экземпляры поисковой фразы.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 4: Замените текст

Если искомая фраза найдена в документе PDF, мы извлекаем первое вхождение текстового фрагмента и обновляем его свойства новым текстом и форматированием.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## Шаг 5: Сохраните измененный PDF-файл

Наконец, мы сохраняем измененный PDF-документ в указанный выходной файл.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Пример исходного кода для замены первого вхождения с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
//Создайте объект TextAbsorber, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Примите поглотитель для всех страниц
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Получить извлеченные текстовые фрагменты
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// Получить первое вхождение текста и заменить
	TextFragment textFragment = textFragmentCollection[1];
	// Обновление текста и других свойств
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## Заключение

В этом руководстве вы узнали, как заменить первое вхождение определенного текста в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы сможете открыть PDF-документ, найти первое вхождение искомой фразы, заменить текст, обновить свойства и сохранить измененный PDF-файл.