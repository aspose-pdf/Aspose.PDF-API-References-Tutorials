---
title: Поиск регулярного выражения в PDF-файле
linktitle: Поиск регулярного выражения в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как искать и извлекать текст с помощью регулярных выражений в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 440
url: /ru/net/programming-with-text/search-regular-expression/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска и получения текста, соответствующего регулярному выражению в файле PDF. Приведенный исходный код C# демонстрирует процесс шаг за шагом.

## Предварительные условия

Прежде чем продолжить обучение, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете получить его с веб-сайта Aspose или использовать NuGet для установки в свой проект.

## Шаг 1. Настройте проект

Начните с создания нового проекта C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.

Добавьте следующие директивы using в начало файла C#, чтобы импортировать необходимые пространства имен:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3. Загрузите PDF-документ.

 Укажите путь к каталогу вашего PDF-документа и загрузите документ, используя`Document` сорт:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

## Шаг 4. Поиск с помощью регулярного выражения

 Создать`TextFragmentAbsorber` объект и установите шаблон регулярного выражения, чтобы найти все фразы, соответствующие шаблону:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Как и 1999-2000 гг.
```

 Заменять`"\\d{4}-\\d{4}"` с желаемым шаблоном регулярного выражения.

## Шаг 5. Установите параметры текстового поиска

 Создать`TextSearchOptions` объект и установите его в`TextSearchOptions` собственность`TextFragmentAbsorber` объект, чтобы включить использование регулярных выражений:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Шаг 6. Поиск на всех страницах.

Примите поглотитель для всех страниц документа:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 7. Получите извлеченные фрагменты текста.

Получите извлеченные фрагменты текста, используя`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 8: Прокрутите фрагменты текста

Прокрутите полученные фрагменты текста и получите доступ к их свойствам:

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

Вы можете изменить код внутри цикла, чтобы выполнять дальнейшие действия над каждым фрагментом текста.

### Пример исходного кода для регулярного выражения поиска с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Создайте объект TextAbsorber, чтобы найти все фразы, соответствующие регулярному выражению.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Как и 1999-2000 гг.
// Установите параметр текстового поиска, чтобы указать использование регулярных выражений
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Примите поглотитель для всех страниц
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Получить извлеченные фрагменты текста
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебирать фрагменты
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

Поздравляем! Вы успешно научились искать и получать текст, соответствующий регулярному выражению, в PDF-документе с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство: от загрузки документа до доступа к извлеченным фрагментам текста. Теперь вы можете включить этот код в свои собственные проекты C# для выполнения расширенного поиска текста в файлах PDF.

### Часто задаваемые вопросы

#### Вопрос: Какова цель руководства «Поиск по регулярному выражению в PDF-файле»?

О: Учебное пособие «Поиск по регулярному выражению в файле PDF» призвано продемонстрировать, как использовать библиотеку Aspose.PDF для .NET для поиска и извлечения текста, соответствующего заданному шаблону регулярного выражения, в файле PDF. В руководстве представлены подробные инструкции и пример кода C# для демонстрации процесса.

#### Вопрос: Как это руководство поможет в поиске текста с использованием регулярных выражений в документе PDF?

О: В этом руководстве представлен пошаговый подход к использованию библиотеки Aspose.PDF для выполнения текстового поиска в PDF-документе на основе шаблона регулярного выражения. В нем подробно описано, как настроить проект, загрузить PDF-документ, определить шаблон регулярного выражения и получить соответствующие фрагменты текста.

#### Вопрос: Каковы необходимые условия для изучения этого руководства?

О: Прежде чем приступить к изучению этого руководства, вы должны иметь базовое представление о языке программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF for .NET. Вы можете получить его с веб-сайта Aspose или использовать NuGet для интеграции в свой проект.

#### Вопрос: Как мне настроить свой проект для использования этого руководства?

О: Для начала создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET. Это позволит вам использовать возможности библиотеки в вашем проекте.

#### Вопрос: Могу ли я использовать регулярные выражения для поиска текста в PDF-документе?

 О: Да, в этом руководстве показано, как использовать регулярные выражения для поиска и извлечения текста из документа PDF. Он предполагает использование`TextFragmentAbsorber` class и указав шаблон регулярного выражения для поиска фраз, соответствующих предоставленному шаблону.

#### Вопрос: Как определить шаблон регулярного выражения для текстового поиска?

 О: Чтобы определить шаблон регулярного выражения для текстового поиска, создайте`TextFragmentAbsorber` объект и задайте его шаблон с помощью`Text` параметр. Заменить шаблон по умолчанию`"\\d{4}-\\d{4}"` в коде руководства с нужным шаблоном регулярного выражения.

#### Вопрос: Как включить использование регулярных выражений для текстового поиска?

 О: Использование регулярных выражений включается путем создания`TextSearchOptions` объект и установить его значение`true` . Назначьте этот объект`TextSearchOptions` собственность`TextFragmentAbsorber` пример. Это гарантирует, что шаблон регулярного выражения будет применяться во время текстового поиска.

#### Вопрос: Могу ли я получить фрагменты текста, соответствующие шаблону регулярного выражения?

 А: Абсолютно. После применения поиска по регулярному выражению к PDF-документу вы можете получить извлеченные фрагменты текста с помощью`TextFragments` собственность`TextFragmentAbsorber` объект. Эти текстовые фрагменты содержат текстовые сегменты, соответствующие указанному шаблону регулярного выражения.

#### Вопрос: К чему я могу получить доступ из полученных фрагментов текста?

О: Из полученных фрагментов текста вы можете получить доступ к различным свойствам, таким как совпадающее текстовое содержимое, положение (координаты X и Y), информация о шрифте (имя, размер, цвет) и многое другое. Пример кода в цикле руководства демонстрирует, как получить доступ к этим свойствам и отобразить их.

#### Вопрос: Как настроить действия над извлеченными фрагментами текста?

О: Получив извлеченные фрагменты текста, вы можете настроить код внутри цикла для выполнения дополнительных действий над каждым фрагментом текста. Это может включать сохранение извлеченного текста, анализ шаблонов или внесение изменений форматирования в соответствии с вашими требованиями.