---
title: Поиск регулярного выражения в файле PDF
linktitle: Поиск регулярного выражения в файле PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как искать и извлекать текст с помощью регулярных выражений в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 440
url: /ru/net/programming-with-text/search-regular-expression/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска и извлечения текста, соответствующего регулярному выражению в файле PDF. Предоставленный исходный код C# демонстрирует процесс шаг за шагом.

## Предпосылки

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете получить ее с сайта Aspose или использовать NuGet для установки в свой проект.

## Шаг 1: Настройте проект

Начните с создания нового проекта C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен

Добавьте следующие директивы using в начало файла C#, чтобы импортировать необходимые пространства имен:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Загрузите PDF-документ.

 Укажите путь к каталогу вашего PDF-документа и загрузите документ с помощью`Document` сорт:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 4: Поиск с использованием регулярного выражения

 Создать`TextFragmentAbsorber` объект и задайте шаблон регулярного выражения, чтобы найти все фразы, соответствующие шаблону:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Как 1999-2000
```

 Заменять`"\\d{4}-\\d{4}"` с желаемым шаблоном регулярного выражения.

## Шаг 5: Установите параметры текстового поиска

 Создать`TextSearchOptions` объект и установите его в`TextSearchOptions` собственность`TextFragmentAbsorber` объект для включения использования регулярных выражений:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Шаг 6: Поиск на всех страницах

Принять поглотитель для всех страниц документа:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 7: Извлечение извлеченных фрагментов текста.

Получите извлеченные фрагменты текста с помощью`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 8: Просмотрите фрагменты текста.

Пройдитесь по извлеченным фрагментам текста и получите доступ к их свойствам:

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

Вы можете изменить код внутри цикла для выполнения дальнейших действий над каждым фрагментом текста.

### Пример исходного кода для поиска регулярных выражений с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Создайте объект TextAbsorber для поиска всех фраз, соответствующих регулярному выражению.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Как 1999-2000
// Установите параметр текстового поиска, чтобы указать использование регулярных выражений
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Принять поглотитель для всех страниц
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Получить извлеченные фрагменты текста
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Просмотрите фрагменты
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

Поздравляем! Вы успешно научились искать и извлекать текст, соответствующий регулярному выражению в документе PDF, используя Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от загрузки документа до доступа к извлеченным фрагментам текста. Теперь вы можете включить этот код в свои собственные проекты C# для выполнения расширенного поиска текста в файлах PDF.

### Часто задаваемые вопросы

#### В: Какова цель руководства «Поиск регулярных выражений в PDF-файле»?

A: Учебник "Поиск регулярного выражения в файле PDF" призван продемонстрировать, как использовать библиотеку Aspose.PDF для .NET для поиска и извлечения текста, соответствующего указанному шаблону регулярного выражения в файле PDF. Учебник предоставляет исчерпывающее руководство и пример кода C# для демонстрации процесса.

#### В: Как это руководство помогает в поиске текста с использованием регулярных выражений в PDF-документе?

A: В этом руководстве представлен пошаговый подход к использованию библиотеки Aspose.PDF для проведения текстового поиска в документе PDF на основе шаблона регулярного выражения. В нем подробно описывается, как настроить проект, загрузить документ PDF, определить шаблон регулярного выражения и извлечь соответствующие фрагменты текста.

#### В: Каковы предварительные условия для прохождения этого урока?

A: Перед началом этого руководства у вас должно быть базовое понимание языка программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF for .NET. Вы можете получить ее на веб-сайте Aspose или использовать NuGet для интеграции в свой проект.

#### В: Как мне настроить свой проект, следуя этому руководству?

A: Для начала создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET. Это позволит вам использовать возможности библиотеки в вашем проекте.

#### В: Могу ли я использовать регулярные выражения для поиска текста в PDF-документе?

 A: Да, этот урок демонстрирует, как использовать регулярные выражения для поиска и извлечения текста из документа PDF. Он включает использование`TextFragmentAbsorber` класс и указание шаблона регулярного выражения для поиска фраз, соответствующих предоставленному шаблону.

#### В: Как определить шаблон регулярного выражения для текстового поиска?

 A: Чтобы определить шаблон регулярного выражения для текстового поиска, создайте`TextFragmentAbsorber` объект и задайте его шаблон с помощью`Text` параметр. Заменить шаблон по умолчанию`"\\d{4}-\\d{4}"` в коде учебника с желаемым шаблоном регулярного выражения.

#### В: Как включить использование регулярных выражений для текстового поиска?

 A: Использование регулярных выражений включается путем создания`TextSearchOptions` объект и установка его значения`true` . Назначьте этот объект`TextSearchOptions` собственность`TextFragmentAbsorber` экземпляр. Это гарантирует, что шаблон регулярного выражения будет применен во время текстового поиска.

#### В: Могу ли я получить фрагменты текста, соответствующие шаблону регулярного выражения?

 A: Конечно. После применения поиска по регулярному выражению к документу PDF вы можете получить извлеченные фрагменты текста с помощью`TextFragments` собственность`TextFragmentAbsorber` объект. Эти текстовые фрагменты содержат текстовые сегменты, соответствующие указанному шаблону регулярного выражения.

#### В: К какой информации я могу получить доступ из извлеченных фрагментов текста?

A: Из извлеченных текстовых фрагментов вы можете получить доступ к различным свойствам, таким как сопоставленное текстовое содержимое, положение (координаты X и Y), информация о шрифте (имя, размер, цвет) и т. д. Пример кода в цикле руководства демонстрирует, как получить доступ к этим свойствам и отобразить их.

#### В: Как настроить действия с извлеченными фрагментами текста?

A: После того, как вы извлекли фрагменты текста, вы можете настроить код внутри цикла для выполнения дополнительных действий над каждым фрагментом текста. Это может включать сохранение извлеченного текста, анализ шаблонов или реализацию изменений форматирования на основе ваших требований.