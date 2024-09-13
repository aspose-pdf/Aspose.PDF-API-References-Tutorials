---
title: Извлечение текста с помощью текстового устройства
linktitle: Извлечение текста с помощью текстового устройства
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как извлечь текст из PDF-документа с помощью текстового устройства в Aspose.PDF для .NET.
type: docs
weight: 210
url: /ru/net/programming-with-text/extract-text-using-text-device/
---
Этот урок проведет вас через процесс извлечения текста из документа PDF с помощью текстового устройства в Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Библиотека Aspose.PDF для .NET. Вы можете загрузить ее с официального сайта Aspose или использовать менеджер пакетов, например NuGet, для ее установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Импортируйте необходимые пространства имен
В файле кода, из которого вы хотите извлечь текст, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Шаг 3: Укажите каталог документа
 В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, где хранятся ваши документы.

## Шаг 4: Откройте PDF-документ.
 Откройте существующий PDF-документ с помощью`Document`конструктор и передача пути к входному PDF-файлу.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Шаг 5: Извлечение текста с помощью текстового устройства
 Создать`StringBuilder` объект для хранения извлеченного текста. Пройдитесь по каждой странице документа и используйте`TextDevice` для извлечения текста с каждой страницы.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Шаг 6: Сохраните извлеченный текст.
 Укажите путь к выходному файлу и сохраните извлеченный текст в текстовый файл с помощью`File.WriteAllText` метод.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Пример исходного кода для извлечения текста с помощью текстового устройства с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Строка для хранения извлеченного текста
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Создать текстовое устройство
		TextDevice textDevice = new TextDevice();
		// Установить параметры извлечения текста — установить режим извлечения текста (необработанный или чистый)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Конвертировать определенную страницу и сохранить текст в поток
		textDevice.Process(pdfPage, textStream);
		// Конвертировать определенную страницу и сохранить текст в поток
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Закрыть поток памяти
		textStream.Close();
		// Получить текст из потока памяти
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Сохраните извлеченный текст в текстовом файле.
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Заключение
Вы успешно извлекли текст из документа PDF с помощью текстового устройства в Aspose.PDF для .NET. Извлеченный текст был сохранен в указанном выходном файле.

### Часто задаваемые вопросы

#### В: Какова цель этого урока?

A: В этом руководстве даются рекомендации по извлечению текста из документа PDF с помощью функции Text Device в Aspose.PDF для .NET. Сопутствующий исходный код C# демонстрирует необходимые шаги для выполнения этой задачи.

#### В: Какие пространства имен мне следует импортировать?

A: В файле кода, из которого вы планируете извлечь текст, включите следующие директивы using в начале файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### В: Как указать каталог документа?

 A: В коде найдите строку, которая гласит:`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

#### В: Как открыть существующий PDF-документ?

 A: На шаге 4 вы откроете существующий PDF-документ с помощью`Document` конструктор и указание пути к входному PDF-файлу.

#### В: Как извлечь текст с помощью текстового устройства?

 A: Шаг 5 включает создание`StringBuilder` объект для хранения извлеченного текста. Затем вы будете проходить по каждой странице документа и использовать`TextDevice` вместе с`TextExtractionOptions` для извлечения текста с каждой страницы.

#### В: Как сохранить извлеченный текст в файл?

 A: На шаге 6 вы укажете путь к выходному файлу и используете`File.WriteAllText`метод сохранения извлеченного текста в текстовый файл.

#### В: Какой главный вывод можно сделать из этого урока?

A: Следуя этому руководству, вы узнали, как использовать функцию Text Device в Aspose.PDF for .NET для извлечения текста из документа PDF. Извлеченный текст был сохранен в указанном выходном файле, что позволяет вам манипулировать извлеченным содержимым и использовать его по мере необходимости.