---
title: Создать PDF с текстом с тегами
linktitle: Создать PDF с текстом с тегами
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по созданию PDF-файла с размеченным текстом с помощью Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
В этом руководстве мы предоставим вам пошаговое руководство по созданию PDF-документа с размеченным текстом с помощью Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно создавать, обрабатывать и конвертировать PDF-документы. Используя функции структуры содержимого с тегами в Aspose.PDF, вы можете добавлять текст с тегами в документ PDF.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio установлена с .NET framework.
2. Библиотека Aspose.PDF для .NET.

## Шаг 1: Настройка проекта

Для начала создайте новый проект в Visual Studio и добавьте ссылку на библиотеку Aspose.PDF для .NET. Вы можете загрузить библиотеку с официального сайта Aspose и установить ее на свой компьютер.

## Шаг 2. Импортируйте необходимые пространства имен

В файле кода C# импортируйте пространства имен, необходимые для доступа к классам и методам, предоставляемым Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Шаг 3: Создание PDF-документа с размеченным текстом

Используйте следующий код для создания PDF-документа с размеченным текстом:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// Добавьте сюда больше абзацев

// Сохраните PDF-документ
document.Save(dataDir + "PDFwithTagText.pdf");
```

Этот код создает пустой документ PDF и добавляет текст с тегами, используя методы, предоставляемые Aspose.PDF. Вы можете добавить другие текстовые элементы с тегами, такие как заголовки и абзацы, используя соответствующие методы.

### Пример исходного кода для создания PDF с текстом с тегами с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать PDF-документ
Document document = new Document();
// Получить контент для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Установить заголовок и язык для Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Создание элементов структуры текстового блока
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// Сохранить PDF-документ
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## Заключение

В этом руководстве вы узнали, как создать PDF-документ с размеченным текстом, используя Aspose.PDF для .NET. Функции помеченной структуры содержимого Aspose.PDF позволяют вам структурировать и организовывать текст для лучшей доступности и семантики.
