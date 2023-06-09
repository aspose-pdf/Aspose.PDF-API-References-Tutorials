---
title: Заменить шрифты
linktitle: Заменить шрифты
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как заменить шрифты в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 340
url: /ru/net/programming-with-text/replace-fonts/
---

В этом руководстве мы объясним, как заменить определенные шрифты в документе PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим пошаговый процесс загрузки PDF-документа, поиска текстовых фрагментов, определения шрифтов для замены, замены шрифтов и сохранения измененного PDF-файла с использованием предоставленного исходного кода C#.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором находится входной PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к вашему файлу PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите PDF-документ

 Затем мы загружаем PDF-документ с помощью`Document` класс из библиотеки Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Шаг 3: Поиск и замена шрифтов

 Мы создаем`TextFragmentAbsorber` объект и установите параметр редактирования, чтобы удалить неиспользуемые шрифты. Затем принимаем поглотитель для всех страниц документа PDF для поиска текстовых фрагментов.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Шаг 4: Замените шрифты

Проходим по всем фрагментам текста, идентифицированным поглотителем. Если имя шрифта фрагмента текста совпадает с желаемым шрифтом для замены, мы заменяем его новым шрифтом.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Шаг 5: Сохраните измененный PDF-файл

Наконец, мы сохраняем измененный PDF-документ в указанный выходной файл.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Пример исходного кода для замены шрифтов с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузить исходный PDF-файл
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Найдите текстовые фрагменты и установите параметр редактирования, чтобы удалить неиспользуемые шрифты.
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Примите поглотитель для всех страниц
	pdfDocument.Pages.Accept(absorber);
	//Пройдите через все TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Если имя шрифта ArialMT, замените имя шрифта на Arial.
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Сохранить обновленный документ
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Заключение

В этом руководстве вы узнали, как заменить определенные шрифты в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете загружать PDF-документ, искать текстовые фрагменты, идентифицировать и заменять определенные шрифты, а также сохранять измененный PDF-файл.