---
title: Укажите межстрочный интервал
linktitle: Укажите межстрочный интервал
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как указать межстрочный интервал в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 510
url: /ru/net/programming-with-text/specify-line-spacing/
---

В этом руководстве объясняется, как указать межстрочный интервал в документе PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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
using System.IO;
```

## Шаг 3: Установите путь к каталогу документов

 Укажите путь к папке с документами с помощью`dataDir` переменная:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

## Шаг 4: Загрузите исходный PDF-файл

 Загрузите исходный PDF-файл с помощью`Document` сорт:

```csharp
Document doc = new Document();
```

## Шаг 5: Создайте TextFormattingOptions

 Создать`TextFormattingOptions` объект и установите режим межстрочного интервала на`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Шаг 6: Создайте TextFragment

 Создать`TextFragment` объект и указать текстовое содержимое:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Шаг 7: Загрузите файл шрифта (необязательно)

 Если вы хотите использовать определенный шрифт для текста, загрузите файл шрифта TrueType в`FileStream` объект:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Заменять`"HPSimplified.TTF"`с фактическим именем файла шрифта.

## Шаг 8: Укажите положение текста и межстрочный интервал

 Установите положение фрагмента текста и назначьте`TextFormattingOptions` к`TextState.FormattingOptions` свойство:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Шаг 9: Добавьте текст в документ

 Добавьте текстовый фрагмент в документ, либо присоединив его к`TextBuilder` или прямо на страницу`Paragraphs` коллекция:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Шаг 10: Сохраните полученный PDF-документ

Сохраните измененный PDF-документ:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Обязательно замените`"SpecifyLineSpacing_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для указания межстрочного интервала с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Загрузить исходный PDF-файл
Document doc = new Document();
//Создайте TextFormattingOptions с LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Создать объект построителя текста для первой страницы документа
//TextBuilder textBuilder = новый TextBuilder (doc.Pages [1]);
// Создать текстовый фрагмент с образцом строки
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Загрузите шрифт TrueType в объект потока
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Установите имя шрифта для текстовой строки
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Укажите позицию для текстового фрагмента
		textFragment.Position = new Position(100, 600);
		//Установите TextFormattingOptions текущего фрагмента на предопределенный (который указывает на LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Добавьте текст в TextBuilder, чтобы его можно было разместить поверх файла PDF.
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Сохраните полученный PDF-документ
	doc.Save(dataDir);
}
```

## Заключение

Поздравляем! Вы успешно научились указывать межстрочный интервал в документе PDF с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от настройки проекта до сохранения измененного документа. Теперь вы можете включить этот код в свои собственные проекты C#, чтобы настроить межстрочный интервал текста в файлах PDF.