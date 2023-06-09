---
title: Поиск текста и рисование прямоугольника
linktitle: Поиск текста и рисование прямоугольника
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как искать текст в PDF, рисовать прямоугольники вокруг найденного текста и сохранять измененный документ с помощью Aspose.PDF для .NET.
type: docs
weight: 460
url: /ru/net/programming-with-text/search-text-and-draw-rectangle/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска определенного текста в документе PDF, рисования прямоугольника вокруг найденного текста и сохранения измененного документа. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Заменять`"SearchAndGetTextFromAll.pdf"` с фактическим именем вашего файла PDF.

## Шаг 5: Создайте TextFragmentAbsorber

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Заменять`@"[\S]+"` с желаемым шаблоном регулярного выражения.

## Шаг 6. Включите поиск по регулярному выражению

Включите поиск по регулярному выражению, установив`TextSearchOptions` свойство поглотителя:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Шаг 7. Поиск на всех страницах

Принять поглотитель для всех страниц документа:

```csharp
document.Pages.Accept(textAbsorber);
```

## Шаг 8: Нарисуйте прямоугольник вокруг найденного текста

 Создать`PdfContentEditor` объект и прокручивать извлеченные текстовые фрагменты, рисуя прямоугольник вокруг каждого текстового сегмента:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Шаг 9: Сохраните измененный документ

Сохраните измененный документ:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Обязательно замените`"SearchTextAndDrawRectangle_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для поиска текста и рисования прямоугольника с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Создайте объект TextAbsorber, чтобы найти все фразы, соответствующие регулярному выражению.
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы успешно научились искать определенный текст в документе PDF, рисовать прямоугольник вокруг найденного текста и сохранять измененный документ с помощью Aspose.PDF для .NET. В этом учебнике представлено пошаговое руководство, от настройки проекта до выполнения необходимых действий. Теперь вы можете включить этот код в свои собственные проекты C# для управления текстом и рисования прямоугольников в файлах PDF.