---
title: Найдите и получите текстовую страницу в PDF-файле
linktitle: Найдите и получите текстовую страницу в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как искать и получать текст с определенной страницы в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 430
url: /ru/net/programming-with-text/search-and-get-text-page/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска и получения текста с определенной страницы в файле PDF. Приведенный исходный код C# демонстрирует процесс шаг за шагом.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

## Шаг 4. Найдите и извлеките текст со страницы.

 Создать`TextFragmentAbsorber`объект, чтобы найти все экземпляры входной поисковой фразы на определенной странице:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Заменять`"Figure"` с фактическим текстом, который вы хотите найти.

## Шаг 5. Поиск на определенной странице.

Примите поглотитель для конкретной страницы документа:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 6: получите извлеченные фрагменты текста

Получите извлеченные фрагменты текста, используя`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 7. Прокрутите фрагменты и сегменты текста.

Прокрутите полученные фрагменты текста и их сегменты и получите доступ к их свойствам:

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

Вы можете изменить код внутри цикла, чтобы выполнять дальнейшие действия над каждым текстовым сегментом.

### Пример исходного кода для страницы поиска и получения текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Создайте объект TextAbsorber, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Примите поглотитель для всех страниц
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Получить извлеченные фрагменты текста
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебирать фрагменты
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Заключение

Поздравляем! Вы успешно научились искать и получать текст с определенной страницы PDF-документа с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство: от загрузки документа до доступа к извлеченным текстовым сегментам. Теперь вы можете включить

### Часто задаваемые вопросы

#### Вопрос: Какова цель руководства «Поиск и получение текстовой страницы»?

О: Учебное пособие «Поиск и получение текстовой страницы» предназначено для иллюстрации того, как использовать библиотеку Aspose.PDF для .NET для поиска и извлечения текста с определенной страницы в файле PDF. В руководстве представлены подробные инструкции и пример кода C# для демонстрации процесса.

#### Вопрос: Как это руководство поможет извлечь текст с определенной страницы PDF-документа?

О: Это руководство проведет вас через процесс извлечения текста из определенной страницы PDF-документа с помощью библиотеки Aspose.PDF. В нем описываются необходимые шаги и предоставляется код C# для поиска указанной текстовой фразы на выбранной странице и получения связанных текстовых сегментов.

#### Вопрос: Каковы необходимые условия для изучения этого руководства?

О: Прежде чем приступить к изучению этого руководства, вы должны иметь базовое представление о языке программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF for .NET. Вы можете получить его с веб-сайта Aspose или использовать NuGet для интеграции в свой проект.

#### Вопрос: Как мне настроить свой проект для использования этого руководства?

О: Для начала создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET. Это позволит вам использовать возможности библиотеки в своем проекте.

#### Вопрос: Могу ли я искать текст на определенной странице PDF-документа?

О: Да, в этом руководстве показано, как искать текст на определенной странице PDF-документа. Он предполагает использование`TextFragmentAbsorber` класс для поиска экземпляров определенной текстовой фразы на выбранной странице.

#### Вопрос: Как мне получить доступ к извлеченным фрагментам текста с определенной страницы?

 О: После поиска текста на назначенной странице вы можете получить доступ к извлеченным фрагментам текста с помощью кнопки`TextSegments` собственность`TextFragment` объект. Это свойство обеспечивает доступ к коллекции`TextSegment` объекты, содержащие извлеченный текст и связанную с ним информацию.

#### Вопрос: Какую информацию я могу получить из извлеченных текстовых сегментов?

О: Вы можете получить различную информацию из извлеченных текстовых сегментов, включая текстовое содержимое, положение (координаты X и Y), информацию о шрифте (имя, размер, цвет и т. д.) и многое другое. Пример кода руководства демонстрирует, как получить доступ к этим сведениям и распечатать их для каждого текстового сегмента.

#### Вопрос: Могу ли я выполнять дополнительные действия над извлеченными фрагментами текста?

А: Конечно. Получив извлеченные сегменты текста, вы можете настроить код внутри цикла для выполнения дополнительных действий над каждым сегментом. Это может включать сохранение извлеченного текста, анализ текстовых шаблонов или применение изменений форматирования.