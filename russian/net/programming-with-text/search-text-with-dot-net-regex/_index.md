---
title: Поиск текста с помощью Dot Net Regex
linktitle: Поиск текста с помощью Dot Net Regex
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как искать текст с помощью регулярных выражений .NET в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 480
url: /ru/net/programming-with-text/search-text-with-dot-net-regex/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска текста с использованием регулярных выражений .NET в документе PDF. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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

## Шаг 4. Создайте объект .NET Regex

 Создать`.NET Regex` объект для определения шаблона поиска:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Заменять`@"[\S]+"` с желаемым шаблоном регулярного выражения.

## Шаг 5: Загрузите PDF-документ

 Загрузите документ PDF с помощью`Document` сорт:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Заменять`"SearchTextRegex.pdf"` с фактическим именем вашего файла PDF.

## Шаг 6. Получите конкретную страницу

Получить нужную страницу документа:

```csharp
Page page = document.Pages[1];
```

 Заменять`1` с желаемым номером страницы (индекс на основе 1).

## Шаг 7: Создайте TextFragmentAbsorber

 Создать`TextFragmentAbsorber`объект, чтобы найти все экземпляры входного регулярного выражения:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Шаг 8: Примите поглотитель для страницы

Примите поглотитель для страницы:

```csharp
page.Accept(textFragmentAbsorber);
```

## Шаг 9: Получите извлеченные текстовые фрагменты

Получить извлеченные текстовые фрагменты с помощью`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 10: Прокрутите текстовые фрагменты

Прокрутите полученные текстовые фрагменты и выполните нужные действия:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Измените код внутри цикла, чтобы при необходимости выполнять дальнейшие действия над каждым текстовым фрагментом.

### Пример исходного кода для поиска текста с регулярным выражением Dot Net с использованием Aspose.PDF для .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создайте объект Regex, чтобы найти все слова
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Открыть документ
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Получить конкретную страницу
Page page = document.Pages[1];
// Создайте объект TextAbsorber, чтобы найти все экземпляры входного регулярного выражения.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Принять поглотитель для страницы
page.Accept(textFragmentAbsorber);
// Получить извлеченные текстовые фрагменты
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебрать фрагменты
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Заключение

Поздравляем! Вы успешно научились искать текст с помощью регулярных выражений .NET в документе PDF, используя Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство, от настройки проекта до доступа к извлеченным фрагментам текста. Теперь вы можете включить этот код в свои собственные проекты C# для выполнения расширенного текстового поиска в файлах PDF.