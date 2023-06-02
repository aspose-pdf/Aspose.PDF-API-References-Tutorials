---
title: Уменьшить документы
linktitle: Уменьшить документы
second_title: Aspose.PDF для справочника API .NET
description: Из этого пошагового руководства вы узнаете, как использовать Aspose.PDF для .NET для сжатия PDF-документов.
type: docs
weight: 350
url: /ru/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам создавать, обрабатывать и оптимизировать PDF-документы с помощью C#. В этом руководстве мы рассмотрим пример использования Aspose.PDF для сжатия документа PDF.

## Шаг 1: Загрузка PDF-документа

 Чтобы сжать PDF-документ, нам сначала нужно загрузить его в наше приложение C#, используя Aspose.PDF. В приведенном ниже коде мы указываем путь к нашему PDF-документу и создаем новый экземпляр файла`Document` сорт.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## Шаг 2: сжатие PDF-документа

 После того, как мы загрузили документ PDF, мы можем использовать`OptimizeResources` метод`Document` class для оптимизации документа и потенциального уменьшения его размера. Обратите внимание, что этот метод не может гарантировать сжатие документа, поскольку некоторые PDF-документы уже могут быть сильно оптимизированы.

```csharp
// Оптимизация PDF-документа. Однако обратите внимание, что этот метод не может гарантировать сжатие документа.
pdfDocument.OptimizeResources();
```

## Шаг 3: Сохранение обновленного PDF-документа

После того, как мы оптимизировали документ PDF, мы можем сохранить обновленную версию в новый файл, используя`Save` метод`Document` сорт. В приведенном ниже коде мы указываем путь и имя выходного файла.

```csharp
// Укажите путь к выходному файлу
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(outputFilePath);
```

### Пример исходного кода для сжатия документов с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
// Оптимизация PDF-документа. Однако обратите внимание, что этот метод не может гарантировать сжатие документа.
pdfDocument.OptimizeResources();
dataDir = dataDir + "ShrinkDocument_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
```
