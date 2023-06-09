---
title: Создать PDF с изображением с тегами
linktitle: Создать PDF с изображением с тегами
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по созданию PDF-файла с изображением с тегами с помощью Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
В этом руководстве мы предоставим вам пошаговое руководство по созданию документа PDF с изображением с тегами с помощью Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно создавать, обрабатывать и конвертировать PDF-документы. Используя функции структуры содержимого с тегами в Aspose.PDF, вы можете добавлять изображения с тегами в документ PDF.

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

## Шаг 3: Создание документа PDF с изображением с тегами

Используйте следующий код для создания PDF-документа с изображением с тегами:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Этот код создает пустой документ PDF и добавляет изображение с тегами, используя методы, предоставляемые Aspose.PDF. Изображение указывается с замещающим текстом, заголовком и тегом.

## Шаг 4: Сохранение PDF-документа

Используйте следующий код для сохранения PDF-документа:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Этот код сохраняет документ PDF с изображением с тегами в указанный файл.

### Пример исходного кода для создания PDF-файла с изображением с тегами с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Добавить изображение с разрешением 300 DPI (по умолчанию)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Сохранить PDF-документ
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Заключение

В этом руководстве вы узнали, как создать PDF-документ с изображением с тегами, используя Aspose.PDF для .NET. Изображения с тегами добавляют в документ PDF дополнительную структурированную информацию.
