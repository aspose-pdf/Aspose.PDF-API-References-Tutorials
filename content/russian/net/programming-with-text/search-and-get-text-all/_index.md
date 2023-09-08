---
title: Искать и получать весь текст
linktitle: Искать и получать весь текст
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как искать и получать текст со всех страниц PDF-документа с помощью Aspose.PDF для .NET.
type: docs
weight: 420
url: /ru/net/programming-with-text/search-and-get-text-all/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска и получения текста со всех страниц PDF-документа. Приведенный исходный код C# демонстрирует процесс шаг за шагом.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

## Шаг 4. Найдите и извлеките текст

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Заменять`"text"` с фактическим текстом, который вы хотите найти.

## Шаг 5. Поиск на всех страницах.

Примите поглотитель для всех страниц документа:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 6: получите извлеченные фрагменты текста

Получите извлеченные фрагменты текста, используя`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 7: Прокрутите фрагменты текста

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

### Пример исходного кода для поиска и получения текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Создайте объект TextAbsorber, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Поздравляем! Вы успешно научились искать и получать текст со всех страниц PDF-документа с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство: от загрузки документа до доступа к извлеченным фрагментам текста. Теперь вы можете включить этот код в свои собственные проекты C# для анализа и обработки текстового содержимого в файлах PDF.

### Часто задаваемые вопросы

#### Вопрос: Какова цель руководства «Найти и получить весь текст»?

О: Учебное пособие «Поиск и получение всего текста» демонстрирует, как использовать библиотеку Aspose.PDF для .NET для поиска и извлечения текста со всех страниц PDF-документа. В руководстве представлены пошаговые инструкции, а также пример кода C# для выполнения поиска и извлечения текста.

#### Вопрос: Как это руководство поможет извлечь текст из PDF-документов?

О: Это руководство проведет вас через процесс извлечения текста со всех страниц PDF-документа. Он использует библиотеку Aspose.PDF для поиска определенных текстовых фраз и получения связанной информации, такой как положение, свойства шрифта и цвета.

#### Вопрос: Каковы необходимые условия для изучения этого руководства?

О: Прежде чем приступить к изучению этого руководства, вы должны иметь базовое представление о языке программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF for .NET. Вы можете получить его с веб-сайта Aspose или использовать NuGet для интеграции в свой проект.

#### Вопрос: Как мне настроить свой проект для использования этого руководства?

О: Для начала создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET. Это позволит вам получить доступ к функциям библиотеки в вашем проекте.

#### Вопрос: Как выполнить поиск определенного текста в PDF-документе?

О: Вы можете использовать`TextFragmentAbsorber`для поиска экземпляров определенной поисковой фразы в PDF-документе. Создав экземпляр этого класса и указав целевой текст, вы можете захватить все вхождения этого текста.

#### Вопрос: Могу ли я искать текст на всех страницах PDF-документа?

 О: Да, в руководстве показано, как искать текст на всех страницах PDF-документа.`pdfDocument.Pages.Accept(textFragmentAbsorber)` Метод используется для принятия поглотителя для всех страниц, что позволяет искать нужный текст на каждой странице.

#### Вопрос: Как получить доступ к извлеченным фрагментам текста?

 О: После поиска текста вы можете получить доступ к извлеченным фрагментам текста с помощью`TextFragments` собственность`TextFragmentAbsorber` объект. Это свойство обеспечивает доступ к коллекции`TextFragment` объекты, содержащие извлеченный текст и связанную с ним информацию.

#### Вопрос: Какую информацию я могу получить из извлеченных фрагментов текста?

О: Из извлеченных фрагментов текста вы можете получить различные детали, такие как фактическое текстовое содержимое, положение (координаты X и Y), информацию о шрифте (имя, размер, цвет и т. д.) и многое другое. Пример кода руководства демонстрирует, как получить доступ к этим сведениям и распечатать их.

#### Вопрос: Могу ли я выполнять дальнейшие действия над извлеченными фрагментами текста?

А: Абсолютно. Получив извлеченные фрагменты текста, вы можете изменить код внутри цикла, чтобы выполнять специальные действия над каждым фрагментом. Это может включать сохранение извлеченного текста, анализ текстовых шаблонов или применение изменений форматирования.