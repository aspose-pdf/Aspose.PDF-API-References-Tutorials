---
title: Извлечение текста с помощью текстового устройства
linktitle: Извлечение текста с помощью текстового устройства
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как извлечь текст из PDF-документа с помощью текстового устройства в Aspose.PDF для .NET.
type: docs
weight: 210
url: /ru/net/programming-with-text/extract-text-using-text-device/
---
Это руководство проведет вас через процесс извлечения текста из PDF-документа с помощью текстового устройства в Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файл кода, из которого вы хотите извлечь текст, добавьте следующие директивы в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Откройте PDF-документ.
 Откройте существующий PDF-документ с помощью`Document`конструктор и передав путь к входному PDF-файлу.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Шаг 5. Извлеките текст с помощью текстового устройства
 Создать`StringBuilder` объект для хранения извлеченного текста. Перебирайте каждую страницу документа и используйте`TextDevice` для извлечения текста с каждой страницы.

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
 Укажите путь к выходному файлу и сохраните извлеченный текст в текстовый файл, используя команду`File.WriteAllText` метод.

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
		// Установить параметры извлечения текста — установить режим извлечения текста (Raw или Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Конвертируйте определенную страницу и сохраняйте текст в поток.
		textDevice.Process(pdfPage, textStream);
		// Конвертируйте определенную страницу и сохраняйте текст в поток.
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Закрыть поток памяти
		textStream.Close();
		// Получить текст из потока памяти
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Сохраните извлеченный текст в текстовый файл
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Заключение
Вы успешно извлекли текст из PDF-документа с помощью текстового устройства в Aspose.PDF для .NET. Извлеченный текст был сохранен в указанный выходной файл.

### Часто задаваемые вопросы

#### Вопрос: Какова цель этого урока?

О: В этом руководстве представлены инструкции по извлечению текста из PDF-документа с использованием функции текстового устройства в Aspose.PDF для .NET. Сопровождающий исходный код C# демонстрирует необходимые шаги для решения этой задачи.

#### Вопрос: Какие пространства имен мне следует импортировать?

О: В файле кода, из которого вы планируете извлечь текст, включите в начало файла следующие директивы using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Вопрос: Как указать каталог документа?

 О: В коде найдите строку, в которой написано`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как открыть существующий PDF-документ?

 О: На шаге 4 вы откроете существующий PDF-документ, используя`Document` конструктор и указав путь к входному PDF-файлу.

#### Вопрос: Как извлечь текст с помощью текстового устройства?

 О: Шаг 5 предполагает создание`StringBuilder` объект для хранения извлеченного текста. Затем вы будете перебирать каждую страницу документа и использовать`TextDevice` вместе с`TextExtractionOptions` для извлечения текста с каждой страницы.

#### Вопрос: Как сохранить извлеченный текст в файл?

 О: На шаге 6 вы укажете путь к выходному файлу и воспользуетесь`File.WriteAllText`метод сохранения извлеченного текста в текстовый файл.

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы узнали, как использовать функцию текстового устройства в Aspose.PDF для .NET для извлечения текста из PDF-документа. Извлеченный текст сохраняется в указанном выходном файле, что позволяет вам манипулировать и использовать извлеченный контент по мере необходимости.