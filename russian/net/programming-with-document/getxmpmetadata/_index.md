---
title: Получить метаданные XMP
linktitle: Получить метаданные XMP
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать функцию GetXmpMetadata в Aspose.PDF для .NET для извлечения метаданных XMP из документа PDF с использованием исходного кода C#.
type: docs
weight: 200
url: /ru/net/programming-with-document/getxmpmetadata/
---

 Aspose.PDF for .NET — это популярная библиотека для работы с PDF, которая позволяет разработчикам создавать, редактировать и преобразовывать PDF-файлы в своих приложениях .NET. Одной из функций, предлагаемых этой библиотекой, является возможность извлекать метаданные XMP из документа PDF. Этот учебник проведет вас через этапы использования`GetXmpMetadata` функция Aspose.PDF для .NET для извлечения метаданных XMP из документа PDF.

## Шаг 1: Установите Aspose.PDF для .NET

 Чтобы использовать Aspose.PDF для .NET в ваших .NET-приложениях, вы должны сначала установить библиотеку. Вы можете скачать последнюю версию библиотеки с сайта[Страница загрузки Aspose.PDF для .NET](https://releases.aspose.com/pdf/net).

После загрузки библиотеки извлеките содержимое ZIP-файла в папку на своем компьютере. Затем вам нужно будет добавить ссылку на Aspose.PDF для .NET DLL в ваш проект .NET.

## Шаг 2: Загрузите PDF-документ

 После того, как вы установили Aspose.PDF для .NET и добавили ссылку на DLL в свой проект .NET, вы можете начать использовать`GetXmpMetadata` функция извлечения метаданных XMP из документа PDF.

Первым шагом в использовании этой функции является загрузка документа PDF, из которого вы хотите извлечь метаданные XMP. Для этого можно использовать следующий код:

```csharp
// Путь к PDF-документу
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Откройте PDF-документ
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 В приведенном выше коде замените`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором находится ваш PDF-документ. Этот код загрузит документ PDF в`Document` объект, который затем можно использовать для извлечения метаданных XMP.

## Шаг 3: Извлеките метаданные XMP

Чтобы извлечь метаданные XMP из документа PDF, вы можете использовать следующий код:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 В приведенном выше коде`xmp:CreateDate`, `xmp:Nickname` , и`xmp:CustomProperty`являются примерами свойств метаданных XMP, которые можно извлечь из документа PDF. Вы можете заменить эти имена свойств именами любых других свойств метаданных XMP, которые вы хотите извлечь.

## Пример исходного кода для получения метаданных XMP с использованием Aspose.PDF для .NET

 Вот полный исходный код для извлечения метаданных XMP из документа PDF с помощью`GetXmpMetadata` особенность Aspose.PDF для .NET:

```csharp
// Путь к PDF-документу
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Откройте PDF-документ
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Извлечь метаданные XMP
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 В приведенном выше коде замените`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором находится ваш PDF-документ. Этот код извлечет метаданные XMP из документа PDF и выведет их на консоль.