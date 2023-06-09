---
title: Страница поиска текстовых сегментов
linktitle: Страница поиска текстовых сегментов
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как искать текстовые сегменты на странице в документе PDF и получать их свойства с помощью Aspose.PDF для .NET.
type: docs
weight: 470
url: /ru/net/programming-with-text/search-text-segments-page/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска определенных текстовых сегментов на странице документа PDF и получения их свойств. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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

## Шаг 3: Установите путь к каталогу документов

 Укажите путь к папке с документами с помощью`dataDir` переменная:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

## Шаг 4: Загрузите PDF-документ

 Загрузите документ PDF с помощью`Document` сорт:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Заменять`"SearchTextSegmentsPage.pdf"` с фактическим именем вашего файла PDF.

## Шаг 5: Создайте TextFragmentAbsorber

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Заменять`"text"` с желаемой поисковой фразой.

## Шаг 6: Примите поглотитель для конкретной страницы

Примите абсорбер для нужной страницы документа:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Заменять`2` с желаемым номером страницы (индекс на основе 1).

## Шаг 7: Получите извлеченные текстовые сегменты

 Получите извлеченные текстовые сегменты с помощью`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 8: Прокрутите текстовые сегменты

Прокрутите извлеченные текстовые сегменты и получите доступ к их свойствам:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Измените код в цикле, чтобы при необходимости выполнять дальнейшие действия с каждым текстовым сегментом.

### Пример исходного кода для страницы «Поиск текстовых сегментов» с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Создайте объект TextAbsorber, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Примите поглотитель для всех страниц
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Получить извлеченные текстовые фрагменты
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебрать фрагменты
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Заключение

Поздравляем! Вы успешно научились искать определенные текстовые сегменты на странице PDF-документа с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство, от загрузки документа до доступа к извлеченным текстовым сегментам. Теперь вы можете включить этот код в свои собственные проекты C# для выполнения расширенного поиска текстовых сегментов в файлах PDF.