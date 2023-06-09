---
title: Поиск текста и добавление гиперссылки
linktitle: Поиск текста и добавление гиперссылки
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как искать текст в PDF, добавлять гиперссылки к найденному тексту и сохранять измененный документ с помощью Aspose.PDF для .NET.
type: docs
weight: 450
url: /ru/net/programming-with-text/search-text-and-add-hyperlink/
---

В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска определенного текста в документе PDF, добавления гиперссылки к найденному тексту и сохранения измененного документа. Предоставленный исходный код C# демонстрирует пошаговый процесс.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Шаг 3: Установите путь к каталогу документов

 Укажите путь к папке с документами с помощью`dataDir` переменная:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

## Шаг 4: Создайте TextFragmentAbsorber

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Заменять`"\\d{4}-\\d{4}"` с желаемым шаблоном регулярного выражения.

## Шаг 5. Включите поиск по регулярному выражению.

Включите поиск по регулярному выражению, установив`TextSearchOptions` свойство поглотителя:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Шаг 6: Откройте и свяжите документ PDF

 Создать`PdfContentEditor` объект и привязать его к исходному файлу PDF:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Заменять`"SearchRegularExpressionPage.pdf"` с фактическим именем вашего файла PDF.

## Шаг 7: Примите поглотитель для страницы

Примите абсорбер для нужной страницы документа:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Заменять`1` с нужным номером страницы.

## Шаг 8: Добавьте гиперссылки к найденному тексту

Прокрутите полученные фрагменты текста и добавьте к ним гиперссылки:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Создайте прямоугольник на основе положения текстового фрагмента
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    // Добавьте веб-ссылку в прямоугольник
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Заменять`"http://www.aspose.com"` с желаемым URL-адресом гиперссылки.

## Шаг 9: Сохраните и закройте измененный документ

Сохраните измененный документ и закройте редактор:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Обязательно замените`"SearchTextAndAddHyperlink_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для поиска текста и добавления гиперссылки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создайте объект-поглотитель, чтобы найти все экземпляры входной поисковой фразы.
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Включить поиск по регулярному выражению
absorber.TextSearchOptions = new TextSearchOptions(true);
// Открыть документ
PdfContentEditor editor = new PdfContentEditor();
//Привязать исходный PDF-файл
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Принять поглотитель для страницы
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Перебрать фрагменты
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, синий, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы успешно научились искать определенный текст в документе PDF, добавлять гиперссылки к найденному тексту и сохранять измененный документ с помощью Aspose.PDF для .NET. В этом учебнике представлено пошаговое руководство, от настройки проекта до выполнения необходимых действий. Теперь вы можете включить этот код в свои собственные проекты C# для управления текстом и добавления гиперссылок в PDF-файлы.