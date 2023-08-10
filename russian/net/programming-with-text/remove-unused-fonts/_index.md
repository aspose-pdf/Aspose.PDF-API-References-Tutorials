---
title: Удалить неиспользуемые шрифты
linktitle: Удалить неиспользуемые шрифты
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как удалить неиспользуемые шрифты из документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 300
url: /ru/net/programming-with-text/remove-unused-fonts/
---

В этом руководстве мы объясним, как удалить неиспользуемые шрифты из документа PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим пошаговый процесс загрузки PDF-файла, определения и удаления неиспользуемых шрифтов и сохранения обновленного PDF-файла с использованием предоставленного исходного кода C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором находятся ваши PDF-файлы. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к вашим файлам PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный PDF-файл

 Затем мы загружаем исходный PDF-документ, используя`Document` класс из библиотеки Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Шаг 3. Определите и удалите неиспользуемые шрифты

 Мы создаем`TextFragmentAbsorber` объект с`TextEditOptions` параметр установлен на`TextEditOptions.FontReplace.RemoveUnusedFonts` Эта опция позволяет нам идентифицировать и удалять неиспользуемые шрифты в документе PDF. Затем мы перебираем все`TextFragments` и установите шрифт на желаемый шрифт.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Шаг 4. Сохраните обновленный PDF-файл

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

В этом руководстве вы узнали, как удалить неиспользуемые шрифты из документа PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы сможете загрузить PDF-файл, определить и удалить неиспользуемые шрифты и сохранить обновленный PDF-файл.