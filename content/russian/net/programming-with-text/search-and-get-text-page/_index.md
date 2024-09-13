---
title: Поиск и получение текстовой страницы в файле PDF
linktitle: Поиск и получение текстовой страницы в файле PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как искать и извлекать текст с определенной страницы PDF-файла с помощью Aspose.PDF для .NET.
type: docs
weight: 430
url: /ru/net/programming-with-text/search-and-get-text-page/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска и получения текста с определенной страницы в файле PDF. Предоставленный исходный код C# демонстрирует процесс шаг за шагом.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 4: Поиск и извлечение текста со страницы

 Создать`TextFragmentAbsorber`объект для поиска всех вхождений введенной поисковой фразы на определенной странице:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Заменять`"Figure"` с фактическим текстом, который вы хотите найти.

## Шаг 5: Поиск на определенной странице

Принять поглотитель для определенной страницы документа:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 6: получение извлеченных фрагментов текста

 Получите извлеченные фрагменты текста с помощью`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 7: Просмотрите фрагменты и сегменты текста.

Пройдитесь по фрагментам текста getd и их сегментам и получите доступ к их свойствам:

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

Вы можете изменить код внутри цикла, чтобы выполнить дополнительные действия с каждым текстовым сегментом.

### Пример исходного кода для страницы поиска и получения текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Создайте объект TextAbsorber для поиска всех вхождений введенной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Принять поглотитель для всех страниц
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Получить извлеченные фрагменты текста
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Просмотрите фрагменты
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

Поздравляем! Вы успешно научились искать и получать текст с определенной страницы документа PDF с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от загрузки документа до доступа к извлеченным текстовым сегментам. Теперь вы можете включить

### Часто задаваемые вопросы

#### В: Какова цель руководства «Поиск и получение текстовой страницы»?

A: Учебник "Search And Get Text Page" призван проиллюстрировать, как использовать библиотеку Aspose.PDF для .NET для поиска и извлечения текста с определенной страницы в файле PDF. Учебник содержит подробные инструкции и пример кода C# для демонстрации процесса.

#### В: Как это руководство поможет извлечь текст с определенной страницы PDF-документа?

A: Этот учебник проведет вас через процесс извлечения текста из определенной страницы документа PDF с использованием библиотеки Aspose.PDF. Он описывает необходимые шаги и предоставляет код C# для поиска указанной текстовой фразы на выбранной странице и извлечения связанных текстовых сегментов.

#### В: Каковы предварительные условия для прохождения этого урока?

A: Перед началом этого руководства у вас должно быть базовое понимание языка программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF for .NET. Вы можете получить ее на веб-сайте Aspose или использовать NuGet для интеграции в свой проект.

#### В: Как мне настроить свой проект, следуя этому руководству?

A: Чтобы начать, создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET. Это позволит вам использовать возможности библиотеки в вашем проекте.

#### В: Могу ли я искать текст на определенной странице PDF-документа?

A: Да, этот урок демонстрирует, как искать текст на определенной странице документа PDF. Он включает использование`TextFragmentAbsorber` класс для поиска экземпляров определенной текстовой фразы на выбранной странице.

#### В: Как получить доступ к извлеченным текстовым сегментам с определенной страницы?

 A: После поиска текста на указанной странице вы можете получить доступ к извлеченным текстовым сегментам с помощью`TextSegments` собственность`TextFragment` объект. Это свойство обеспечивает доступ к коллекции`TextSegment` объекты, содержащие извлеченный текст и связанную с ним информацию.

#### В: Какую информацию я могу извлечь из извлеченных текстовых сегментов?

A: Вы можете извлечь различные данные из извлеченных текстовых сегментов, включая текстовое содержимое, положение (координаты X и Y), информацию о шрифте (имя, размер, цвет и т. д.) и многое другое. Пример кода руководства демонстрирует, как получить доступ к этим данным и распечатать их для каждого текстового сегмента.

#### В: Могу ли я выполнять пользовательские действия с извлеченными текстовыми сегментами?

A: Конечно. После того, как вы извлекли текстовые сегменты, вы можете настроить код внутри цикла для выполнения дополнительных действий с каждым сегментом. Это может включать сохранение извлеченного текста, анализ текстовых шаблонов или применение изменений форматирования.