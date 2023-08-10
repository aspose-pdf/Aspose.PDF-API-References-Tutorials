---
title: Поиск и получение текста все
linktitle: Поиск и получение текста все
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как выполнять поиск и получать текст со всех страниц PDF-документа с помощью Aspose.PDF для .NET.
type: docs
weight: 420
url: /ru/net/programming-with-text/search-and-get-text-all/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска и получения текста со всех страниц PDF-документа. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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

## Шаг 3: Загрузите PDF-документ

 Укажите путь к каталогу вашего PDF-документа и загрузите документ, используя`Document` сорт:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

## Шаг 4: Найдите и извлеките текст

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Заменять`"text"` с фактическим текстом, который вы хотите найти.

## Шаг 5. Поиск на всех страницах

Принять поглотитель для всех страниц документа:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 6: получить извлеченные текстовые фрагменты

Получить извлеченные текстовые фрагменты с помощью`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 7: Прокрутите текстовые фрагменты

Прокрутите полученные текстовые фрагменты и получите доступ к их свойствам:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Вы можете изменить код внутри цикла, чтобы выполнять дальнейшие действия над каждым текстовым фрагментом.

### Пример исходного кода для поиска и получения текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Создайте объект TextAbsorber, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Примите поглотитель для всех страниц
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Получить извлеченные текстовые фрагменты
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебрать фрагменты
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Заключение

Поздравляем! Вы успешно научились выполнять поиск и получать текст со всех страниц PDF-документа с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство, от загрузки документа до доступа к извлеченным фрагментам текста. Теперь вы можете включить этот код в свои собственные проекты C# для анализа и обработки текстового содержимого в файлах PDF.