---
title: Заменить текстовую страницу
linktitle: Заменить текстовую страницу
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как заменить текст на определенной странице документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 370
url: /ru/net/programming-with-text/replace-text-page/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для замены текста на определенной странице документа PDF. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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

## Шаг 3: Загрузите PDF-документ

 Укажите путь к каталогу вашего PDF-документа и загрузите документ, используя`Document` сорт:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

 Обязательно замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

## Шаг 4. Найдите и замените текст

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Заменять`"text"` с фактическим текстом, который вы хотите найти и заменить.

## Шаг 5: Укажите целевую страницу

 Примите поглотитель для конкретной страницы, открыв`Pages` коллекция`pdfDocument` объект и вызов`Accept` метод:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Заменять`2` с номером страницы, где вы хотите заменить текст. Обратите внимание, что номера страниц начинаются с нуля, поэтому`0` представляет первую страницу.

## Шаг 6: Получить извлеченные текстовые фрагменты

Получить извлеченные текстовые фрагменты с помощью`TextFragments` собственность`TextFragmentAbsorber` объект:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Шаг 7: Повторите текстовые фрагменты

Прокрутите полученные текстовые фрагменты и обновите текст и другие свойства по желанию:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 В приведенном выше фрагменте кода замените`"New Phrase"` с текстом замены, который вы хотите использовать. Вы также можете настроить другие свойства, такие как шрифт, размер шрифта, цвет переднего плана и цвет фона.

## Шаг 8: Сохраните измененный PDF

 Сохраните измененный PDF-документ в новый файл с помощью кнопки`Save` метод:

```csharp
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

 Обязательно замените`"ReplaceTextPage_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для замены текстовой страницы с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
//Создайте объект TextAbsorber, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//Принять поглотитель для конкретной страницы
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Получить извлеченные текстовые фрагменты
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Перебрать фрагменты
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Обновление текста и других свойств
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

## Заключение

Поздравляем! Вы успешно научились заменять текст на определенной странице документа PDF с помощью Aspose.PDF для .NET. В этом учебнике представлено пошаговое руководство от загрузки документа до сохранения измененной версии. Теперь вы можете включить этот код в свои собственные проекты C#, чтобы автоматизировать замену текста в файлах PDF.