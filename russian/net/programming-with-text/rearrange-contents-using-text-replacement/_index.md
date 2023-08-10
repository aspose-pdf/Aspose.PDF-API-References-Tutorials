---
title: Изменить порядок содержимого с помощью замены текста
linktitle: Изменить порядок содержимого с помощью замены текста
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как изменить порядок содержимого в документе PDF с помощью замены текста с помощью Aspose.PDF для .NET.
type: docs
weight: 270
url: /ru/net/programming-with-text/rearrange-contents-using-text-replacement/
---

В этом руководстве мы объясним, как изменить порядок содержимого в документе PDF с помощью замены текста с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим пошаговый процесс загрузки PDF-файла, поиска определенных текстовых фрагментов, замены текста и сохранения измененного PDF-файла с использованием предоставленного исходного кода C#.

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
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Шаг 3: Поиск и замена текстовых фрагментов

 Мы создаем`TextFragmentAbsorber` объект с регулярным выражением для поиска определенных фрагментов текста. Затем мы перебираем текстовые фрагменты, настраиваем их шрифт, размер, цвет и заменяем текст.

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

## Шаг 4: Сохраните измененный PDF-файл

Наконец, мы сохраняем измененный PDF-документ в указанный выходной файл.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Пример исходного кода для переупорядочивания содержимого с помощью замены текста с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузить исходный PDF-файл
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	//Создайте объект TextFragment Absorber с регулярным выражением
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
		// Замените текст строкой большего размера, чем заполнитель
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Сохранить полученный PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Заключение

В этом руководстве вы узнали, как изменить порядок содержимого в документе PDF с помощью замены текста с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете искать определенные фрагменты текста, настраивать их внешний вид и заменять текст в документе PDF.