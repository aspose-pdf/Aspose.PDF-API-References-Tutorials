---
title: Переупорядочение содержимого с помощью замены текста
linktitle: Переупорядочение содержимого с помощью замены текста
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как изменить порядок содержимого в PDF-документе с помощью замены текста с помощью Aspose.PDF для .NET.
type: docs
weight: 270
url: /ru/net/programming-with-text/rearrange-contents-using-text-replacement/
---
В этом уроке мы объясним, как изменить порядок содержимого в PDF-документе, используя замену текста с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс загрузки PDF-файла, поиска определенных фрагментов текста, замены текста и сохранения измененного PDF-файла, используя предоставленный исходный код C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором находятся ваши PDF-файлы. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к вашим PDF-файлам.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный PDF-файл

 Затем мы загружаем исходный PDF-документ, используя`Document` класс из библиотеки Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Шаг 3. Поиск и замена фрагментов текста

 Мы создаем`TextFragmentAbsorber` объект с регулярным выражением для поиска определенных фрагментов текста. Затем перебираем фрагменты текста, настраиваем их шрифт, размер, цвет и заменяем текст.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Шаг 4. Сохраните измененный PDF-файл.

Наконец, мы сохраняем измененный PDF-документ в указанный выходной файл.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Пример исходного кода для изменения порядка содержимого с помощью замены текста с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузить исходный PDF-файл
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// Создайте объект TextFragment Absorber с регулярным выражением.
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Замените каждый TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Установить шрифт заменяемого фрагмента текста
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Установить размер шрифта
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Замените текст строкой большей, чем заполнитель.
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Сохранить полученный PDF-файл
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Заключение

В этом руководстве вы узнали, как изменить порядок содержимого в PDF-документе, используя замену текста с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы сможете искать определенные фрагменты текста, настраивать их внешний вид и заменять текст в PDF-документе.

### Часто задаваемые вопросы

#### Вопрос: Какова цель урока «Изменение содержимого с помощью замены текста»?

О: Учебное пособие «Изменение содержимого с помощью замены текста» демонстрирует, как использовать библиотеку Aspose.PDF для .NET для изменения порядка содержимого в PDF-документе путем выполнения замены текста. Учебное пособие содержит пошаговое руководство и исходный код C#, которые помогут вам загрузить PDF-файл, выполнить поиск определенных фрагментов текста, заменить текст и сохранить измененный PDF-файл.

#### Вопрос: Зачем мне менять порядок содержимого в PDF-документе?

О: Изменение содержимого PDF-документа может быть полезно для различных целей, например для обновления текста, переформатирования макета или внесения исправлений. Этот метод позволяет динамически изменять содержимое PDF-файла, сохраняя его структуру и внешний вид.

#### Вопрос: Как настроить каталог документов?

О: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, в котором находятся ваши PDF-файлы.

#### Вопрос: Как выполнить замену текста в PDF-документе?

 О: В этом руководстве рассказывается о процессе поиска определенных фрагментов текста в PDF-файле с помощью`TextFragmentAbsorber`сорт. Демонстрируется, как настроить внешний вид текстовых фрагментов и заменить их содержимое.

#### Вопрос: Могу ли я настроить шрифт, размер и цвет заменяемого текста?

 О: Да, вы можете настроить шрифт, размер и цвет заменяемого текста, изменив`TextState` свойства`TextFragment` объект. В учебнике приведен пример установки шрифта, размера шрифта и цвета переднего плана текста.

#### Вопрос: Как сохранить измененный PDF-документ?

 О: После выполнения замены текста и настройки фрагментов текста вы можете сохранить измененный PDF-документ с помощью`Save` метод`Document` сорт. Укажите желаемый путь к выходному файлу в качестве аргумента`Save` метод.

#### Вопрос: Каков ожидаемый результат этого руководства?

О: Следуя инструкциям и выполнив предоставленный код C#, вы создадите модифицированный PDF-документ, в котором определенные фрагменты текста будут заменены и настроены в соответствии с вашими требованиями.

#### Вопрос: Могу ли я использовать разные регулярные выражения для текстового поиска?

 О: Да, вы можете использовать разные регулярные выражения для поиска определенных фрагментов текста в PDF-документе. Пример, представленный в руководстве, демонстрирует, как создать`TextFragmentAbsorber`объект с определенным регулярным выражением для поиска и замены текста.

#### Вопрос: Требуется ли для работы с этим руководством действующая лицензия Aspose?

О: Да, для корректной работы этого руководства требуется действующая лицензия Aspose. Вы можете приобрести полную лицензию или получить 30-дневную временную лицензию на веб-сайте Aspose.