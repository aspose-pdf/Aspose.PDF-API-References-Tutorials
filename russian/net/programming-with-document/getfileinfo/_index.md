---
title: Получить информацию о файле
linktitle: Получить информацию о файле
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать функцию GetFileInfo в Aspose.PDF для .NET для получения метаданных о PDF-документе.
type: docs
weight: 180
url: /ru/net/programming-with-document/getfileinfo/
---

 Aspose.PDF for .NET — это популярная библиотека для работы с PDF, которая позволяет разработчикам создавать, редактировать и преобразовывать PDF-файлы в своих приложениях .NET. Одной из функций, предлагаемых этой библиотекой, является возможность получения информации о метаданных PDF-документа. Этот учебник проведет вас через этапы использования`GetFileInfo`функция Aspose.PDF для .NET для получения информации о метаданных PDF-документа.

## Шаг 1: Установите Aspose.PDF для .NET

 Чтобы использовать Aspose.PDF для .NET в ваших .NET-приложениях, вы должны сначала установить библиотеку. Вы можете скачать последнюю версию библиотеки с сайта[Страница загрузки Aspose.PDF для .NET](https://releases.aspose.com/pdf/net).

После загрузки библиотеки извлеките содержимое ZIP-файла в папку на своем компьютере. Затем вам нужно будет добавить ссылку на Aspose.PDF для .NET DLL в ваш проект .NET.

## Шаг 2: Загрузите PDF-документ

 После того, как вы установили Aspose.PDF для .NET и добавили ссылку на DLL в свой проект .NET, вы можете начать использовать`GetFileInfo` функция для получения информации о метаданных документа PDF.

Первым шагом в использовании этой функции является загрузка документа PDF, информацию о котором вы хотите получить. Для этого можно использовать следующий код:

```csharp
// Путь к PDF-документу
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Откройте PDF-документ
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 В приведенном выше коде замените`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором находится ваш PDF-документ. Этот код загрузит документ PDF в`Document` объект, который затем можно использовать для получения информации о метаданных документа.

## Шаг 3. Получите метаданные документа

Чтобы получить информацию о метаданных PDF-документа, вы можете использовать следующий код:

```csharp
// Получить информацию о документе
DocumentInfo docInfo = pdfDocument.Info;

// Показать информацию о документе
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

В приведенном выше коде каждая строка извлекает разные свойства метаданных документа PDF и выводит их на консоль. Вы можете настроить этот код для получения только тех свойств, которые вас интересуют.

### Пример исходного кода для получения информации о файле PDF с использованием Aspose.PDF для .NET

 Вот полный исходный код для получения метаданных PDF-документа с помощью`GetFileInfo` особенность Aspose.PDF для .NET:

```csharp
// Путь к PDF-документу
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Откройте PDF-документ
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Получить информацию о документе
DocumentInfo docInfo = pdfDocument.Info;

// Показать информацию о документе
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```