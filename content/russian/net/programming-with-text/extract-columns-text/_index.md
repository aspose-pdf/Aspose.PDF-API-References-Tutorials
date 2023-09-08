---
title: Извлечь текст столбцов в PDF-файл
linktitle: Извлечь текст столбцов в PDF-файл
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как извлечь текст столбцов из PDF-файла с помощью Aspose.PDF для .NET.
type: docs
weight: 150
url: /ru/net/programming-with-text/extract-columns-text/
---
Это руководство проведет вас через процесс извлечения текста столбцов в PDF-файл с помощью Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файл кода, из которого вы хотите извлечь текст столбцов, добавьте следующие директивы в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Откройте PDF-документ.
 Откройте существующий PDF-документ с помощью`Document`конструктор и передав путь к входному PDF-файлу.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Шаг 5. Отрегулируйте размер шрифта.
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

## Шаг 6. Извлеките текст из столбцов
 Сохраните измененный PDF-документ в потоке памяти и перезагрузите его как новый документ. Затем используйте`TextAbsorber` класс для извлечения текста из столбцов.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Шаг 7: Сохраните извлеченный текст
Сохраните извлеченный текст в текстовый файл по указанному пути к выходному файлу.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Пример исходного кода для извлечения текста столбцов с использованием Aspose.PDF для .NET 
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
	// Необходимо уменьшить размер шрифта хотя бы на 70%
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
Вы успешно извлекли текст столбцов из PDF-документа с помощью Aspose.PDF для .NET. Извлеченный текст был сохранен в указанный выходной файл.

### Часто задаваемые вопросы

#### Вопрос: Какова цель этого урока?

О: В этом руководстве представлено пошаговое руководство по извлечению столбцов текста из файла PDF с помощью Aspose.PDF для .NET. Прилагаемый исходный код C# обеспечивает практическую демонстрацию необходимых процедур.

#### Вопрос: Какие пространства имен мне следует импортировать?

О: В файл кода, из которого вы собираетесь извлечь столбцы текста, включите в начало файла следующие директивы using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Вопрос: Как указать каталог документа?

 A: Найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` в коде и замените`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как открыть существующий PDF-документ?

 О: На шаге 4 вы откроете существующий PDF-документ, используя`Document` конструктор и указав путь к входному PDF-файлу.

#### Вопрос: Почему корректируется размер шрифта?

О: Шаг 5 предполагает уменьшение размера шрифта текстовых фрагментов в 0,7 раза. Эта настройка повышает читаемость и более точно представляет столбчатый текст.

#### Вопрос: Как извлечь текст из столбцов?

 О: Шаг 6 состоит из сохранения измененного PDF-документа в потоке памяти, его перезагрузки как нового документа и последующего использования`TextAbsorber` класс для извлечения текста из столбцов.

#### Вопрос: Какова цель сохранения извлеченного текста?

О: На шаге 7 вы сохраните извлеченный текст в текстовый файл по указанному пути к выходному файлу.

#### Вопрос: Зачем уменьшать размер шрифта перед извлечением?

О: Уменьшение размера шрифта помогает обеспечить правильное выравнивание извлеченного текста по столбцам, обеспечивая более точное представление исходного макета.

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы приобрели знания и навыки, необходимые для извлечения столбцов текста из PDF-документа с помощью Aspose.PDF для .NET. Полученный текст был сохранен в указанный выходной файл.