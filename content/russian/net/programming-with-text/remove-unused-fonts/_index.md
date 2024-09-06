---
title: Удалить неиспользуемые шрифты в PDF-файле
linktitle: Удалить неиспользуемые шрифты в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как удалить неиспользуемые шрифты в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 300
url: /ru/net/programming-with-text/remove-unused-fonts/
---
В этом уроке мы объясним, как удалить неиспользуемые шрифты в файле PDF с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс загрузки PDF, определения и удаления неиспользуемых шрифтов и сохранения обновленного PDF с помощью предоставленного исходного кода C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовые знания программирования на C#.

## Шаг 1: Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, где находятся ваши PDF-файлы. Заменить`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменную с путем к вашим PDF-файлам.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите исходный PDF-файл

 Далее мы загружаем исходный PDF-документ с помощью`Document` класс из библиотеки Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Шаг 3: Определите и удалите неиспользуемые шрифты

 Мы создаем`TextFragmentAbsorber` объект с`TextEditOptions` параметр установлен на`TextEditOptions.FontReplace.RemoveUnusedFonts` . Эта опция позволяет нам идентифицировать и удалять неиспользуемые шрифты в документе PDF. Затем мы перебираем все`TextFragments` и установите нужный шрифт.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Шаг 4: Сохраните обновленный PDF-файл.

Наконец, мы сохраняем обновленный PDF-документ в указанный выходной файл.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Пример исходного кода для удаления неиспользуемых шрифтов с помощью Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузить исходный PDF-файл
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Перебрать все фрагменты текста
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Сохранить обновленный документ
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Заключение

В этом уроке вы узнали, как удалить неиспользуемые шрифты из документа PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете загрузить PDF, определить и удалить неиспользуемые шрифты и сохранить обновленный PDF.

### Часто задаваемые вопросы

#### В: Какова цель руководства «Удаление неиспользуемых шрифтов в PDF-файле»?

A: Учебник "Удаление неиспользуемых шрифтов в файле PDF" объясняет, как использовать библиотеку Aspose.PDF для .NET для удаления неиспользуемых шрифтов из документа PDF. Учебник проведет вас через процесс загрузки PDF, определения и удаления неиспользуемых шрифтов и сохранения обновленного PDF.

#### В: Зачем мне удалять неиспользуемые шрифты из PDF-документа?

A: Удаление неиспользуемых шрифтов из документа PDF может помочь уменьшить размер файла и оптимизировать документ для лучшей производительности. Это особенно полезно при работе с файлами PDF, содержащими встроенные шрифты, которые фактически не используются в содержимом документа.

#### В: Как настроить каталог документов?

A: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, где находятся ваши PDF-файлы.

#### В: Как удалить неиспользуемые шрифты из PDF-документа с помощью библиотеки Aspose.PDF?

A: Учебное пособие проведет вас через весь процесс шаг за шагом:

1.  Откройте PDF-документ с помощью`Document` сорт.
2.  Создать`TextFragmentAbsorber` объект с`TextEditOptions` установлен на`FontReplace.RemoveUnusedFonts`.
3. Примите меры по выявлению и удалению неиспользуемых шрифтов из PDF-файла.
4.  Повторить все`TextFragments` и установите нужный шрифт.
5. Сохраните обновленный PDF-документ.

####  В: Какова цель`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 А:`TextEditOptions.FontReplace.RemoveUnusedFonts` параметр указывает`TextFragmentAbsorber`для выявления и удаления неиспользуемых шрифтов из PDF-документа.

#### В: Могу ли я заменить неиспользуемые шрифты шрифтом по своему выбору?

A: Да, вы можете изменить код, чтобы заменить неиспользуемые шрифты шрифтом по вашему выбору. В предоставленном примере кода в качестве замены используется шрифт "Arial, Bold".

####  В: Как работает`TextFragmentAbsorber` work to remove unused fonts?

 А:`TextFragmentAbsorber` настроен с помощью`TextEditOptions.FontReplace.RemoveUnusedFonts` параметр, который определяет неиспользуемые шрифты в текстовых фрагментах PDF. После поглощения вы можете выполнить итерацию по`TextFragments` и установите для них желаемые шрифты замены.

#### В: Каков ожидаемый результат выполнения предоставленного кода?

A: Следуя инструкциям и запустив предоставленный код C#, вы удалите неиспользуемые шрифты из входного PDF-документа и сохраните обновленную версию как выходной PDF-файл.

#### В: Могу ли я изменить код, чтобы удалить шрифты только с определенных страниц или областей?

A: Предоставленный код фокусируется на удалении неиспользуемых шрифтов из всего документа PDF. Если вы хотите выбрать определенные страницы или области для удаления шрифтов, вам нужно будет изменить подход и использовать более сложную логику для определения неиспользуемых шрифтов в этих областях.