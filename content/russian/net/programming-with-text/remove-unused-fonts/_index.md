---
title: Удалить неиспользуемые шрифты в PDF-файле
linktitle: Удалить неиспользуемые шрифты в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как удалить неиспользуемые шрифты в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 300
url: /ru/net/programming-with-text/remove-unused-fonts/
---
В этом уроке мы объясним, как удалить неиспользуемые шрифты в файле PDF с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс загрузки PDF-файла, определения и удаления неиспользуемых шрифтов и сохранения обновленного PDF-файла с использованием предоставленного исходного кода C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором находятся ваши PDF-файлы. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к вашим PDF-файлам.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный PDF-файл

 Затем мы загружаем исходный PDF-документ, используя`Document` класс из библиотеки Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Шаг 3. Определите и удалите неиспользуемые шрифты

 Мы создаем`TextFragmentAbsorber` объект с`TextEditOptions` параметр установлен на`TextEditOptions.FontReplace.RemoveUnusedFonts` . Эта опция позволяет нам идентифицировать и удалять неиспользуемые шрифты в PDF-документе. Затем мы перебираем все`TextFragments` и установите нужный шрифт.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Шаг 4. Сохраните обновленный PDF-файл.

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
	// Перебрать все TextFragments
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

В этом уроке вы узнали, как удалить неиспользуемые шрифты из PDF-документа с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы можете загрузить PDF-файл, определить и удалить неиспользуемые шрифты, а также сохранить обновленный PDF-файл.

### Часто задаваемые вопросы

#### Вопрос: Какова цель урока «Удалить неиспользуемые шрифты из PDF-файла»?

О: В учебнике «Удаление неиспользуемых шрифтов из PDF-файла» объясняется, как использовать библиотеку Aspose.PDF для .NET для удаления неиспользуемых шрифтов из PDF-документа. Учебное пособие проведет вас через процесс загрузки PDF-файла, определения и удаления неиспользуемых шрифтов, а также сохранения обновленного PDF-файла.

#### Вопрос: Зачем мне удалять неиспользуемые шрифты из PDF-документа?

О: Удаление неиспользуемых шрифтов из PDF-документа может помочь уменьшить размер файла и оптимизировать документ для повышения производительности. Это особенно полезно при работе с PDF-файлами, содержащими встроенные шрифты, которые фактически не используются в содержимом документа.

#### Вопрос: Как настроить каталог документов?

О: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, в котором находятся ваши PDF-файлы.

#### Вопрос: Как удалить неиспользуемые шрифты из PDF-документа с помощью библиотеки Aspose.PDF?

Ответ: Учебное пособие шаг за шагом проведет вас через весь процесс:

1.  Откройте PDF-документ с помощью`Document` сорт.
2.  Создать`TextFragmentAbsorber` объект с`TextEditOptions` установлен в`FontReplace.RemoveUnusedFonts`.
3. Примите поглотитель, чтобы идентифицировать и удалить неиспользуемые шрифты из PDF-файла.
4.  Перебрать все`TextFragments` и установите нужный шрифт.
5. Сохраните обновленный PDF-документ.

####  Вопрос: Какова цель`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 А:`TextEditOptions.FontReplace.RemoveUnusedFonts` параметр указывает`TextFragmentAbsorber` для идентификации и удаления неиспользуемых шрифтов из PDF-документа.

#### Вопрос: Могу ли я заменить неиспользуемые шрифты шрифтом по своему выбору?

О: Да, вы можете изменить код, чтобы заменить неиспользуемые шрифты шрифтами по вашему выбору. В предоставленном примере кода в качестве замены используется шрифт «Arial, Bold».

####  Вопрос: Как`TextFragmentAbsorber` work to remove unused fonts?

 А:`TextFragmentAbsorber` настроен с помощью`TextEditOptions.FontReplace.RemoveUnusedFonts` параметр, который идентифицирует неиспользуемые шрифты в текстовых фрагментах PDF-файла. После поглощения вы можете перебирать`TextFragments` и установите для них нужные заменяющие шрифты.

#### Вопрос: Каков ожидаемый результат выполнения предоставленного кода?

О: Следуя инструкциям и запустив предоставленный код C#, вы удалите неиспользуемые шрифты из входного PDF-документа и сохраните обновленную версию как выходной PDF-файл.

#### Вопрос: Могу ли я изменить код, чтобы удалить шрифты только с определенных страниц или областей?

О: Предоставленный код направлен на удаление неиспользуемых шрифтов из всего PDF-документа. Если вы хотите настроить таргетинг на удаление шрифтов на определенных страницах или регионах, вам придется изменить подход и использовать более сложную логику для выявления неиспользуемых шрифтов в этих областях.