---
title: Извлечение текста с помощью текстового устройства
linktitle: Извлечение текста с помощью текстового устройства
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как извлечь текст из документа PDF с помощью текстового устройства в Aspose.PDF для .NET.
type: docs
weight: 210
url: /ru/net/programming-with-text/extract-text-using-text-device/
---

Это руководство проведет вас через процесс извлечения текста из PDF-документа с помощью текстового устройства в Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файл кода, из которого вы хотите извлечь текст, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Откройте PDF-документ
 Откройте существующий PDF-документ с помощью`Document` конструктор и передать путь к входному файлу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Шаг 5. Извлеките текст с помощью текстового устройства.
 Создать`StringBuilder` объект для хранения извлеченного текста. Переберите каждую страницу документа и используйте`TextDevice` для извлечения текста с каждой страницы.

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

## Шаг 6: Сохраните извлеченный текст
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
// Строка для хранения извлеченного текста
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Создать текстовое устройство
		TextDevice textDevice = new TextDevice();
		//Установить параметры извлечения текста — установить режим извлечения текста (Raw или Pure).
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Преобразование определенной страницы и сохранение текста в поток
		textDevice.Process(pdfPage, textStream);
		// Преобразование определенной страницы и сохранение текста в поток
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Закрыть поток памяти
		textStream.Close();
		// Получить текст из потока памяти
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Сохраните извлеченный текст в текстовом файле
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Заключение
Вы успешно извлекли текст из документа PDF с помощью текстового устройства в Aspose.PDF для .NET. Извлеченный текст был сохранен в указанный выходной файл.