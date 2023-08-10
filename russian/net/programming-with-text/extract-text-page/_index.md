---
title: Извлечь текстовую страницу
linktitle: Извлечь текстовую страницу
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как извлечь текст с определенной страницы документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 200
url: /ru/net/programming-with-text/extract-text-page/
---

Это руководство проведет вас через процесс извлечения текста из определенной страницы документа PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

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
using System.IO;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Откройте PDF-документ
 Откройте существующий PDF-документ с помощью`Document` конструктор и передать путь к входному файлу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Шаг 5. Извлеките текст с определенной страницы
 Создать`TextAbsorber` объект для извлечения текста из документа. Примите поглотитель для нужной страницы, обратившись к нему через`Pages` коллекция`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Шаг 6: Получите извлеченный текст
 Получите доступ к извлеченному тексту из`TextAbsorber` объект.

```csharp
string extractedText = textAbsorber.Text;
```

## Шаг 7: Сохраните извлеченный текст
 Создать`TextWriter` и откройте файл, в котором вы хотите сохранить извлеченный текст. Запишите извлеченный текст в файл и закройте поток.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Пример исходного кода для извлечения текстовой страницы с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Создайте объект TextAbsorber для извлечения текста
TextAbsorber textAbsorber = new TextAbsorber();
//Принять поглотитель для конкретной страницы
pdfDocument.Pages[1].Accept(textAbsorber);
// Получить извлеченный текст
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Создайте писатель и откройте файл
TextWriter tw = new StreamWriter(dataDir);
// Записать строку текста в файл
tw.WriteLine(extractedText);
// Закрыть поток
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Заключение
Вы успешно извлекли текст с определенной страницы PDF-документа, используя Aspose.PDF для .NET. Извлеченный текст был сохранен в указанный выходной файл.