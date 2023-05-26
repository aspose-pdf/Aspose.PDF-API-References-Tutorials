---
title: Подтвердить стандарт PDFUA
linktitle: Подтвердить стандарт PDFUA
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать Aspose.PDF для .NET для проверки стандарта PDF/UA с использованием кода C#. Пошаговое руководство.
type: docs
weight: 400
url: /ru/net/programming-with-document/validatepdfuastandard/
---
Aspose.PDF для .NET — это мощная библиотека, предоставляющая различные функции для работы с PDF-документами. Одной из его функций является возможность проверки PDF-документов на соответствие стандарту PDF/UA. В этой статье мы предоставим пошаговое руководство по использованию Aspose.PDF для .NET для получения и проверки соответствия стандарту PDF/UA с помощью кода C#.

## Шаг 1. Определение пути к каталогу документов

Далее нам нужно определить путь к каталогу, в котором находится наш PDF-документ. Вы можете сделать это, добавив следующий фрагмент кода:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших PDF-документов.

## Шаг 2: Открытие PDF-документа

После определения пути к каталогу документа мы можем открыть наш PDF-документ, используя следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");
```

 Этот код создает новый`Document` объект из нашего файла PDF, расположенного в указанном каталоге.

## Шаг 3. Проверка PDF для PDF/UA

Теперь, когда мы открыли PDF-документ, мы можем использовать Aspose.PDF для .NET для проверки документа на соответствие PDF/UA. Следующий фрагмент кода выполнит эту работу:

```csharp
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
```

Этот код проверяет документ PDF на соответствие стандарту PDF/UA и создает отчет о проверке в указанном файле XML. Результат проверки сохраняется в`isValidPdfUa` переменная, имеющая логический тип данных.

### Пример исходного кода для Get Validate PDFUAstandard с использованием Aspose.PDF для .NET

```csharp
           
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Открыть документ
	Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");

	// Подтвердить PDF для PDF/UA
	bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
		   
```
