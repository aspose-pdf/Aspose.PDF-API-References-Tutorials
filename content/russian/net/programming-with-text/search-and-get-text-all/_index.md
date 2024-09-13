---
title: Поиск и получение текста
linktitle: Поиск и получение текста
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как искать и извлекать текст со всех страниц PDF-документа с помощью Aspose.PDF для .NET.
type: docs
weight: 420
url: /ru/net/programming-with-text/search-and-get-text-all/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска и получения текста со всех страниц документа PDF. Предоставленный исходный код C# демонстрирует процесс шаг за шагом.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 4: Поиск и извлечение текста

 Создать`TextFragmentAbsorber` объект для поиска всех вхождений введенной поисковой фразы:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Заменять`"text"` с фактическим текстом, который вы хотите найти.

## Шаг 5: Поиск на всех страницах

Принять поглотитель для всех страниц документа:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Шаг 6: получение извлеченных фрагментов текста

 Получите извлеченные фрагменты текста с помощью`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 7: Просмотрите фрагменты текста.

Пройдитесь по фрагментам текста getd и получите доступ к их свойствам:

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

### Пример исходного кода для поиска и получения всего текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Создайте объект TextAbsorber для поиска всех вхождений введенной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Поздравляем! Вы успешно научились искать и получать текст со всех страниц документа PDF с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от загрузки документа до доступа к извлеченным фрагментам текста. Теперь вы можете включить этот код в свои собственные проекты C# для анализа и обработки текстового содержимого в файлах PDF.

### Часто задаваемые вопросы

#### В: Какова цель руководства «Поиск и получение всего текста»?

A: Учебник "Search And Get Text All" демонстрирует, как использовать библиотеку Aspose.PDF для .NET для поиска и извлечения текста со всех страниц документа PDF. Учебник содержит пошаговые инструкции вместе с примером кода C# для выполнения поиска и извлечения текста.

#### В: Как это руководство поможет извлечь текст из PDF-документов?

A: Этот урок проведет вас через процесс извлечения текста со всех страниц документа PDF. Он использует библиотеку Aspose.PDF для поиска определенных текстовых фраз и получения связанной информации, такой как положение, свойства шрифта и цвета.

#### В: Каковы предварительные условия для прохождения этого урока?

A: Перед началом этого руководства у вас должно быть базовое понимание языка программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF for .NET. Вы можете получить ее на веб-сайте Aspose или использовать NuGet для интеграции в свой проект.

#### В: Как мне настроить свой проект, следуя этому руководству?

A: Чтобы начать, создайте новый проект C# в предпочитаемой вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET. Это позволит вам получить доступ к функциональным возможностям библиотеки в вашем проекте.

#### В: Как найти определенный текст в PDF-документе?

 О: Вы можете использовать`TextFragmentAbsorber`класс для поиска экземпляров определенной поисковой фразы в документе PDF. Создав экземпляр этого класса и указав целевой текст, вы можете захватить все вхождения этого текста.

#### В: Могу ли я искать текст на всех страницах PDF-документа?

 A: Да, в руководстве показано, как искать текст на всех страницах документа PDF.`pdfDocument.Pages.Accept(textFragmentAbsorber)` Метод используется для приема поглотителя для всех страниц, что позволяет искать нужный текст на каждой странице.

#### В: Как получить доступ к извлеченным фрагментам текста?

 A: После поиска текста вы можете получить доступ к извлеченным фрагментам текста с помощью`TextFragments` собственность`TextFragmentAbsorber` объект. Это свойство обеспечивает доступ к коллекции`TextFragment` объекты, содержащие извлеченный текст и связанную с ним информацию.

#### В: Какую информацию я могу извлечь из извлеченных фрагментов текста?

A: Вы можете извлечь различные данные из извлеченных текстовых фрагментов, такие как фактическое содержимое текста, положение (координаты X и Y), информацию о шрифте (имя, размер, цвет и т. д.) и многое другое. Пример кода руководства демонстрирует, как получить доступ к этим данным и распечатать их.

#### В: Могу ли я выполнять дальнейшие действия с извлеченными фрагментами текста?

A: Конечно. После того, как вы извлекли фрагменты текста, вы можете изменить код в цикле, чтобы выполнить пользовательские действия с каждым фрагментом. Это может включать сохранение извлеченного текста, анализ текстовых шаблонов или применение изменений форматирования.