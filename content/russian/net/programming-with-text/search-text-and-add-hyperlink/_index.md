---
title: Поиск текста и добавление гиперссылки
linktitle: Поиск текста и добавление гиперссылки
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как искать текст в PDF-файле, добавлять гиперссылки к найденному тексту и сохранять измененный документ с помощью Aspose.PDF для .NET.
type: docs
weight: 450
url: /ru/net/programming-with-text/search-text-and-add-hyperlink/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска определенного текста в документе PDF, добавления гиперссылки на найденный текст и сохранения измененного документа. Предоставленный исходный код C# демонстрирует процесс шаг за шагом.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Шаг 3: Укажите путь к каталогу документов.

 Задайте путь к каталогу ваших документов с помощью`dataDir` переменная:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

## Шаг 4: Создание TextFragmentAbsorber

 Создать`TextFragmentAbsorber` объект для поиска всех вхождений введенной поисковой фразы:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Заменять`"\\d{4}-\\d{4}"` с желаемым шаблоном регулярного выражения.

## Шаг 5: Включите поиск по регулярным выражениям

 Включите поиск по регулярному выражению, установив`TextSearchOptions` Свойство поглотителя:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Шаг 6: Откройте и свяжите PDF-документ

 Создать`PdfContentEditor` объект и привяжите его к исходному PDF-файлу:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Заменять`"SearchRegularExpressionPage.pdf"` на фактическое имя вашего PDF-файла.

## Шаг 7: Примите поглотитель для страницы.

Принять поглотитель для нужной страницы документа:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Заменять`1` с нужным номером страницы.

## Шаг 8: Добавьте гиперссылки к найденному тексту.

Просмотрите извлеченные фрагменты текста и добавьте к ним гиперссылки:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Создайте прямоугольник на основе положения текстового фрагмента.
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Добавьте веб-ссылку в прямоугольник
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Заменять`"http://www.aspose.com"` с желаемым URL-адресом гиперссылки.

## Шаг 9: Сохраните и закройте измененный документ.

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
// Создать объект-абсорбер для поиска всех вхождений входной поисковой фразы
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Включить поиск по регулярным выражениям
absorber.TextSearchOptions = new TextSearchOptions(true);
// Открыть документ
PdfContentEditor editor = new PdfContentEditor();
// Привязать исходный PDF-файл
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Принять поглотитель для страницы
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Просмотрите фрагменты
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

Поздравляем! Вы успешно научились искать определенный текст в документе PDF, добавлять гиперссылки к найденному тексту и сохранять измененный документ с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от настройки проекта до выполнения требуемых действий. Теперь вы можете включить этот код в свои собственные проекты C# для управления текстом и добавления гиперссылок в файлы PDF.

### Часто задаваемые вопросы

#### В: Какова цель руководства «Поиск текста и добавление гиперссылки»?

A: Учебник "Поиск текста и добавление гиперссылки" призван продемонстрировать, как использовать библиотеку Aspose.PDF для .NET для поиска определенного текста в документе PDF, добавлять гиперссылки к найденному тексту и затем сохранять измененный документ. Учебник содержит подробное руководство и примеры кода C# для иллюстрации пошагового процесса.

#### В: Как это руководство помогает добавлять гиперссылки на определенный текст в PDF-документе?

A: Это руководство проведет вас через процесс использования библиотеки Aspose.PDF для поиска определенного текста в документе PDF, применения гиперссылки к идентифицированному тексту и сохранения измененного PDF. Оно охватывает основные шаги, такие как настройка проекта, загрузка документа, включение поиска по регулярным выражениям и добавление гиперссылок к найденному тексту.

#### В: Какие предварительные условия необходимы для прохождения этого урока?

A: Прежде чем начать, у вас должно быть базовое понимание языка программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF for .NET, которую можно получить на веб-сайте Aspose или установить с помощью NuGet в вашем проекте.

#### В: Как мне настроить свой проект, следуя этому руководству?

A: Начните с создания нового проекта C# в предпочитаемой вами интегрированной среде разработки (IDE). Затем добавьте ссылку на библиотеку Aspose.PDF для .NET, что позволит вам использовать возможности библиотеки в вашем проекте.

#### В: Могу ли я добавлять гиперссылки на определенный текст, используя это руководство?

A: Да, этот урок специально посвящен добавлению гиперссылок на определенный текст в документе PDF. Он демонстрирует, как найти и извлечь нужный текст с помощью регулярных выражений, создать гиперссылки, связанные с фрагментами текста, и сохранить измененный PDF.

#### В: Как определить текст, который я хочу найти, и добавить гиперссылку на него?

 A: Чтобы указать текст, который вы хотите найти, и добавить гиперссылку, создайте`TextFragmentAbsorber` объект и задайте его шаблон с помощью`Text` параметр. Заменить шаблон по умолчанию`"\\d{4}-\\d{4}"` в коде учебника с желаемым шаблоном регулярного выражения.

#### В: Как включить поиск текста по регулярным выражениям?

 A: Поиск по регулярному выражению включается путем создания`TextSearchOptions` объект и установка его значения`true` . Назначьте этот объект`TextSearchOptions` собственность`TextFragmentAbsorber` экземпляр. Это гарантирует, что шаблон регулярного выражения будет применен во время текстового поиска.

#### В: Как добавить гиперссылки к найденному тексту?

 A: После идентификации фрагментов текста с помощью`TextFragmentAbsorber` , учебник предоставляет цикл для итерации по этим фрагментам. Для каждого текстового фрагмента учебник демонстрирует, как установить синий цвет текста и создать гиперссылку с помощью`CreateWebLink` метод.

#### В: Каковы шаги, чтобы сохранить измененный PDF-файл с гиперссылками?

 A: После добавления гиперссылок на нужные фрагменты текста используйте`PdfContentEditor` класс для сохранения измененного документа. Пример кода учебника демонстрирует, как сохранить отредактированный PDF, закрыть редактор и отобразить сообщение об успешном завершении.