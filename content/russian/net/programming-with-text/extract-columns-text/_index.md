---
title: Извлечь текст столбцов в файл PDF
linktitle: Извлечь текст столбцов в файл PDF
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как извлечь текст столбцов в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 150
url: /ru/net/programming-with-text/extract-columns-text/
---
Этот урок проведет вас через процесс извлечения текста столбцов в файле PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, где вы хотите извлечь текст столбцов, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Шаг 3: Укажите каталог документа
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

## Шаг 4: Откройте PDF-документ.
 Откройте существующий PDF-документ с помощью`Document` конструктор и передача пути к входному PDF-файлу.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Шаг 5: Отрегулируйте размер шрифта.
Уменьшите размер шрифта текстовых фрагментов в 0,7 раза, чтобы улучшить читаемость и лучше представить столбчатый текст.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Шаг 6: Извлечение текста из столбцов
 Сохраните измененный PDF-документ в поток памяти и перезагрузите его как новый документ. Затем используйте`TextAbsorber` класс для извлечения текста из столбцов.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Шаг 7: Сохраните извлеченный текст.
Сохраните извлеченный текст в текстовый файл по указанному пути выходного файла.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Пример исходного кода для извлечения текста столбцов с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Необходимо уменьшить размер шрифта как минимум на 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Заключение
Вы успешно извлекли текст столбцов из документа PDF с помощью Aspose.PDF для .NET. Извлеченный текст был сохранен в указанном выходном файле.

### Часто задаваемые вопросы

#### В: Какова цель этого урока?

A: Этот учебник предлагает пошаговое руководство по извлечению столбцов текста из файла PDF с помощью Aspose.PDF для .NET. Сопутствующий исходный код C# обеспечивает практическую демонстрацию требуемых процедур.

#### В: Какие пространства имен мне следует импортировать?

A: В файле кода, где вы собираетесь извлекать столбцы текста, включите следующие директивы using в начале файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### В: Как указать каталог документа?

 A: Найдите линию`string dataDir = "YOUR DOCUMENT DIRECTORY";` в коде и замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

#### В: Как открыть существующий PDF-документ?

 A: На шаге 4 вы откроете существующий PDF-документ с помощью`Document` конструктор и указание пути к входному PDF-файлу.

#### В: Почему размер шрифта изменен?

A: Шаг 5 включает уменьшение размера шрифта фрагментов текста на коэффициент 0,7. Эта корректировка улучшает читаемость и более точно представляет столбчатый текст.

#### В: Как извлечь текст из столбцов?

 A: Шаг 6 состоит из сохранения измененного PDF-документа в потоке памяти, повторной загрузки его как нового документа, а затем использования`TextAbsorber` класс для извлечения текста из столбцов.

#### В: Какова цель сохранения извлеченного текста?

A: На шаге 7 вы сохраните извлеченный текст в текстовый файл по указанному пути выходного файла.

#### В: Зачем уменьшать размер шрифта перед извлечением?

A: Уменьшение размера шрифта помогает обеспечить правильное выравнивание извлеченного текста в столбцах, обеспечивая более точное представление исходного макета.

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы приобрели знания и навыки, необходимые для извлечения столбцов текста из документа PDF с помощью Aspose.PDF для .NET. Полученный текст был сохранен в указанном выходном файле.