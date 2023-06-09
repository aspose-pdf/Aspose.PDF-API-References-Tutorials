---
title: Извлечь текст всего
linktitle: Извлечь текст всего
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как извлечь весь текст из документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 180
url: /ru/net/programming-with-text/extract-text-all/
---

Этот учебник проведет вас через процесс извлечения всего текста из документа PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Шаг 5: Извлеките весь текст
 Создать`TextAbsorber` объект для извлечения текста из документа. Затем примите абсорбер для всех страниц.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Шаг 6: Получите извлеченный текст
 Получите доступ к извлеченному тексту из`TextAbsorber` объект.

```csharp
string extractedText = textAbsorber.Text;
```

## Шаг 7: Сохраните извлеченный текст
 Создать`TextWriter` и откройте файл, в котором вы хотите сохранить извлеченный текст. Запишите извлеченный текст в файл и закройте поток.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Пример исходного кода для извлечения текста с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Создайте объект TextAbsorber для извлечения текста
TextAbsorber textAbsorber = new TextAbsorber();
// Примите поглотитель для всех страниц
pdfDocument.Pages.Accept(textAbsorber);
// Получить извлеченный текст
string extractedText = textAbsorber.Text;
// Создайте писатель и откройте файл
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Записать строку текста в файл
tw.WriteLine(extractedText);
// Закрыть поток
tw.Close();
```

## Заключение
Вы успешно извлекли весь текст из документа PDF, используя Aspose.PDF для .NET. Извлеченный текст был сохранен в указанный выходной файл.