---
title: Поиск текстовых сегментов на странице в файле PDF
linktitle: Поиск текстовых сегментов на странице в файле PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как искать текстовые сегменты на странице PDF-файла и извлекать их свойства с помощью Aspose.PDF для .NET.
type: docs
weight: 470
url: /ru/net/programming-with-text/search-text-segments-page/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска определенных текстовых сегментов на странице PDF-файла и извлечения их свойств. Предоставленный исходный код C# демонстрирует процесс шаг за шагом.

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

## Шаг 3: Укажите путь к каталогу документов.

 Задайте путь к каталогу ваших документов с помощью`dataDir` переменная:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 4: Загрузите PDF-документ.

 Загрузите PDF-документ с помощью`Document` сорт:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Заменять`"SearchTextSegmentsPage.pdf"` на фактическое имя вашего PDF-файла.

## Шаг 5: Создайте TextFragmentAbsorber

 Создать`TextFragmentAbsorber` объект для поиска всех вхождений введенной поисковой фразы:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Заменять`"text"` с желаемой поисковой фразой.

## Шаг 6: Примите поглотитель для определенной страницы

Принять поглотитель для нужной страницы документа:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Заменять`2` с желаемым номером страницы (индекс начинается с 1).

## Шаг 7: Извлечение извлеченных текстовых сегментов.

 Получите извлеченные текстовые сегменты с помощью`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 8: Пройдитесь по текстовым сегментам

Пройдитесь по извлеченным текстовым сегментам и получите доступ к их свойствам:

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

При необходимости измените код внутри цикла, чтобы выполнить дополнительные действия с каждым текстовым сегментом.

### Пример исходного кода для страницы поиска текстовых сегментов с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Создайте объект TextAbsorber для поиска всех вхождений введенной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Принять поглотитель для всех страниц
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Получить извлеченные фрагменты текста
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Просмотрите фрагменты
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

Поздравляем! Вы успешно научились искать определенные текстовые сегменты на странице документа PDF с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от загрузки документа до доступа к извлеченным текстовым сегментам. Теперь вы можете включить этот код в свои собственные проекты C# для выполнения расширенного поиска текстовых сегментов в файлах PDF.

### Часто задаваемые вопросы

#### В: Какова цель руководства «Поиск текстовых сегментов на странице в файле PDF»?

A: Учебник "Search Text Segments Page In PDF File" предоставляет исчерпывающее руководство по использованию библиотеки Aspose.PDF для .NET для поиска определенных текстовых сегментов на определенной странице PDF-документа. Он охватывает процесс настройки проекта, загрузки PDF-документа, поиска текстовых сегментов и получения их свойств с помощью кода C#.

#### В: Как это руководство помогает в поиске определенных текстовых сегментов в PDF-документе?

A: В этом руководстве демонстрируется процесс поиска и извлечения определенных текстовых сегментов на определенной странице документа PDF. Следуя приведенным шагам и примерам кода, пользователи могут эффективно искать нужные текстовые сегменты и получать информацию об их свойствах.

#### В: Какие предварительные условия необходимы для прохождения этого урока?

A: Перед началом обучения у вас должно быть базовое понимание языка программирования C#. Кроме того, у вас должна быть установлена библиотека Aspose.PDF for .NET. Вы можете получить ее на веб-сайте Aspose или установить в своем проекте с помощью NuGet.

#### В: Как мне настроить свой проект, следуя этому руководству?

A: Чтобы начать, создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF for .NET. Это позволит вам использовать функции библиотеки для поиска и работы с PDF-документами.

#### В: Могу ли я использовать это руководство для поиска определенных текстовых сегментов на любой странице PDF-файла?

A: Да, этот учебник содержит инструкции по поиску определенных текстовых сегментов на выбранной странице документа PDF. Он помогает пользователям настроить проект, загрузить PDF и использовать библиотеку Aspose.PDF для поиска и извлечения свойств нужных текстовых сегментов.

#### В: Как указать текст, который я хочу найти в этом руководстве?

 A: Чтобы указать текст, который вы хотите найти, создайте`TextFragmentAbsorber` объект и задайте его параметр поиска с помощью`Text` свойство. Заменить значение по умолчанию`"text"` в коде учебника с нужной вам поисковой фразой.

#### В: Как получить свойства извлеченных текстовых сегментов?

После принятия`TextFragmentAbsorber` для определенной страницы PDF-файла вы можете извлечь извлеченные текстовые сегменты с помощью`TextFragments` свойство объекта-абсорбера. Это обеспечивает доступ к коллекции текстовых фрагментов, каждый из которых содержит несколько текстовых сегментов.

#### В: Могу ли я настроить код для выполнения дополнительных действий над каждым текстовым сегментом?

A: Конечно. Пример кода учебника предоставляет цикл для итерации по извлеченным текстовым сегментам. Вы можете настроить код в этом цикле для выполнения дополнительных действий с каждым текстовым сегментом в зависимости от требований вашего проекта.

#### В: Как сохранить измененный PDF-документ после извлечения текстовых сегментов?

A: Этот урок в первую очередь фокусируется на поиске текстовых сегментов и извлечении их свойств. Если вы собираетесь внести изменения в PDF, вы можете обратиться к другой документации Aspose.PDF, чтобы узнать, как манипулировать документом и сохранять его в соответствии с вашими конкретными потребностями.