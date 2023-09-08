---
title: Страница поиска текстовых сегментов в PDF-файле
linktitle: Страница поиска текстовых сегментов в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как искать текстовые сегменты на странице в PDF-файле и получать их свойства с помощью Aspose.PDF для .NET.
type: docs
weight: 470
url: /ru/net/programming-with-text/search-text-segments-page/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска определенных текстовых сегментов на странице PDF-файла и получения их свойств. Приведенный исходный код C# демонстрирует процесс шаг за шагом.

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

## Шаг 3. Установите путь к каталогу документов.

 Задайте путь к каталогу вашего документа, используя`dataDir` переменная:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

## Шаг 4. Загрузите PDF-документ.

 Загрузите PDF-документ, используя`Document` сорт:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Заменять`"SearchTextSegmentsPage.pdf"` с фактическим именем вашего PDF-файла.

## Шаг 5. Создайте TextFragmentAbsorber

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Заменять`"text"` с желаемой поисковой фразой.

## Шаг 6. Примите поглотитель для конкретной страницы.

Примите поглотитель на нужную страницу документа:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Заменять`2` с желаемым номером страницы (индекс от 1).

## Шаг 7. Получите извлеченные фрагменты текста.

 Получите извлеченные текстовые сегменты, используя`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 8. Прокрутите текстовые сегменты

Прокрутите полученные текстовые сегменты и получите доступ к их свойствам:

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

Измените код внутри цикла, чтобы при необходимости выполнять дальнейшие действия над каждым сегментом текста.

### Пример исходного кода для страницы поиска текстовых сегментов с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Создайте объект TextAbsorber, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Примите поглотитель для всех страниц
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Получить извлеченные фрагменты текста
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебирать фрагменты
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

Поздравляем! Вы успешно научились искать определенные текстовые сегменты на странице PDF-документа с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство: от загрузки документа до доступа к извлеченным текстовым сегментам. Теперь вы можете включить этот код в свои собственные проекты C# для выполнения расширенного поиска текстовых сегментов в файлах PDF.

### Часто задаваемые вопросы

#### Вопрос: Какова цель руководства «Поиск текстовых сегментов на странице в PDF-файле»?

Ответ: Учебное пособие «Поиск текстовых сегментов на странице в PDF-файле» представляет собой подробное руководство по использованию библиотеки Aspose.PDF для .NET для поиска определенных текстовых сегментов на определенной странице PDF-документа. Он охватывает процесс настройки проекта, загрузки PDF-документа, поиска текстовых сегментов и получения их свойств с помощью кода C#.

#### Вопрос: Как это руководство помогает при поиске определенных текстовых сегментов в PDF-документе?

О: В этом руководстве демонстрируется процесс поиска и извлечения определенных текстовых сегментов на определенной странице PDF-документа. Следуя предоставленным инструкциям и примерам кода, пользователи могут эффективно искать нужные сегменты текста и получать информацию об их свойствах.

#### Вопрос: Какие предварительные условия необходимы для изучения этого руководства?

О: Прежде чем приступить к изучению руководства, вы должны иметь базовое представление о языке программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF for .NET. Вы можете получить его с веб-сайта Aspose или установить в свой проект с помощью NuGet.

#### Вопрос: Как мне настроить свой проект для использования этого руководства?

О: Для начала создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET. Это позволит вам использовать возможности библиотеки для поиска и работы с PDF-документами.

#### Вопрос: Могу ли я использовать это руководство для поиска определенных фрагментов текста на любой странице PDF-файла?

О: Да, в этом руководстве представлены инструкции по поиску определенных фрагментов текста на выбранной странице PDF-документа. Он помогает пользователям настроить проект, загрузить PDF-файл и использовать библиотеку Aspose.PDF для поиска и получения свойств нужных текстовых сегментов.

#### Вопрос: Как мне указать текст, который я хочу найти в этом уроке?

 О: Чтобы указать текст, который вы хотите найти, создайте`TextFragmentAbsorber` объект и установите его параметр поиска, используя`Text` свойство. Заменить значение по умолчанию`"text"` в коде руководства с желаемой поисковой фразой.

#### Вопрос: Как получить свойства извлеченных текстовых сегментов?

После принятия`TextFragmentAbsorber` для конкретной страницы PDF-файла вы можете получить извлеченные фрагменты текста, используя команду`TextFragments` свойство объекта-поглотителя. Это обеспечивает доступ к коллекции текстовых фрагментов, каждый из которых содержит несколько текстовых сегментов.

#### Вопрос: Могу ли я настроить код для выполнения дополнительных действий над каждым сегментом текста?

А: Абсолютно. Пример кода руководства предоставляет цикл для перебора извлеченных текстовых сегментов. Вы можете настроить код в этом цикле для выполнения дополнительных действий над каждым текстовым сегментом в зависимости от требований вашего проекта.

#### Вопрос: Как сохранить измененный PDF-документ после извлечения текстовых сегментов?

О: В этом руководстве основное внимание уделяется поиску текстовых сегментов и получению их свойств. Если вы собираетесь внести изменения в PDF-файл, вы можете обратиться к другой документации Aspose.PDF, чтобы узнать, как манипулировать и сохранять документ в соответствии с вашими конкретными потребностями.