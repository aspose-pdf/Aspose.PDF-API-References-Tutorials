---
title: Найдите текст и добавьте гиперссылку
linktitle: Найдите текст и добавьте гиперссылку
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как искать текст в PDF-файле, добавлять гиперссылки к найденному тексту и сохранять измененный документ с помощью Aspose.PDF для .NET.
type: docs
weight: 450
url: /ru/net/programming-with-text/search-text-and-add-hyperlink/
---
В этом руководстве объясняется, как использовать Aspose.PDF для .NET для поиска определенного текста в PDF-документе, добавления гиперссылки на найденный текст и сохранения измененного документа. Приведенный исходный код C# демонстрирует процесс шаг за шагом.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Шаг 3. Установите путь к каталогу документов.

 Задайте путь к каталогу вашего документа, используя`dataDir` переменная:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

## Шаг 4. Создайте TextFragmentAbsorber

 Создать`TextFragmentAbsorber` объект, чтобы найти все экземпляры входной поисковой фразы:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Заменять`"\\d{4}-\\d{4}"` с желаемым шаблоном регулярного выражения.

## Шаг 5. Включите поиск по регулярным выражениям

 Включите поиск по регулярным выражениям, установив параметр`TextSearchOptions` свойство абсорбера:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Шаг 6. Откройте и свяжите PDF-документ.

 Создать`PdfContentEditor` объект и привяжите его к исходному PDF-файлу:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Заменять`"SearchRegularExpressionPage.pdf"` с фактическим именем вашего PDF-файла.

## Шаг 7. Примите поглотитель для страницы.

Примите поглотитель на нужную страницу документа:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Заменять`1` с желаемым номером страницы.

## Шаг 8: Добавьте гиперссылки к найденному тексту

Прокрутите полученные фрагменты текста и добавьте к ним гиперссылки:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Создайте прямоугольник на основе положения фрагмента текста.
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Добавьте веб-ссылку в прямоугольник
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Заменять`"http://www.aspose.com"` с желаемым URL-адресом гиперссылки.

## Шаг 9. Сохраните и закройте измененный документ.

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
// Перебирать фрагменты
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, синий, имя_действия);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы успешно научились искать определенный текст в PDF-документе, добавлять гиперссылки к найденному тексту и сохранять измененный документ с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство: от настройки проекта до выполнения необходимых действий. Теперь вы можете включить этот код в свои собственные проекты C# для управления текстом и добавления гиперссылок в файлы PDF.

### Часто задаваемые вопросы

#### Вопрос: Какова цель урока «Поиск в тексте и добавление гиперссылки»?

О: Учебное пособие «Поиск текста и добавление гиперссылки» призвано продемонстрировать, как использовать библиотеку Aspose.PDF для .NET для поиска определенного текста в PDF-документе, добавления гиперссылок к найденному тексту и последующего сохранения измененного документа. Учебное пособие содержит подробное руководство и примеры кода C#, иллюстрирующие пошаговый процесс.

#### Вопрос: Как это руководство поможет добавить гиперссылки на определенный текст в PDF-документе?

О: Это руководство проведет вас через процесс использования библиотеки Aspose.PDF для поиска определенного текста в PDF-документе, применения гиперссылки к определенному тексту и сохранения измененного PDF-файла. Он охватывает такие важные шаги, как настройка проекта, загрузка документа, включение поиска по регулярным выражениям и добавление гиперссылок к найденному тексту.

#### Вопрос: Какие предварительные условия необходимы для изучения этого руководства?

О: Прежде чем начать, вы должны иметь базовое представление о языке программирования C#. Кроме того, вам необходимо установить библиотеку Aspose.PDF для .NET, которую можно получить с веб-сайта Aspose или установить с помощью NuGet в вашем проекте.

#### Вопрос: Как мне настроить свой проект для использования этого руководства?

О: Начните с создания нового проекта C# в предпочитаемой вами интегрированной среде разработки (IDE). Затем добавьте ссылку на библиотеку Aspose.PDF для .NET, которая позволит вам использовать возможности библиотеки в вашем проекте.

#### Вопрос: Могу ли я добавить гиперссылки к определенному тексту с помощью этого руководства?

О: Да, в этом руководстве особое внимание уделяется добавлению гиперссылок к определенному тексту в документе PDF. Он демонстрирует, как найти и извлечь нужный текст с помощью регулярных выражений, создать гиперссылки, связанные с фрагментами текста, и сохранить измененный PDF-файл.

#### Вопрос: Как определить текст, который я хочу найти, и добавить к нему гиперссылку?

 О: Чтобы указать текст, который вы хотите найти, и добавить к нему гиперссылку, создайте`TextFragmentAbsorber` объект и задайте его шаблон с помощью`Text` параметр. Заменить шаблон по умолчанию`"\\d{4}-\\d{4}"` в коде руководства с нужным шаблоном регулярного выражения.

#### Вопрос: Как включить поиск текста по регулярным выражениям?

 О: Поиск по регулярным выражениям включается путем создания`TextSearchOptions` объект и установить его значение`true` . Назначьте этот объект`TextSearchOptions` собственность`TextFragmentAbsorber` пример. Это гарантирует, что шаблон регулярного выражения будет применяться во время текстового поиска.

#### Вопрос: Как добавить гиперссылки к найденному тексту?

 A: После идентификации фрагментов текста с помощью`TextFragmentAbsorber` , в учебнике предусмотрен цикл для перебора этих фрагментов. Для каждого фрагмента текста в учебнике показано, как установить синий цвет текста и создать гиперссылку с помощью`CreateWebLink` метод.

#### Вопрос: Как сохранить измененный PDF-файл с гиперссылками?

 О: После добавления гиперссылок на нужные фрагменты текста воспользуйтесь`PdfContentEditor` класс для сохранения измененного документа. В примере кода руководства показано, как сохранить отредактированный PDF-файл, закрыть редактор и отобразить сообщение об успехе.