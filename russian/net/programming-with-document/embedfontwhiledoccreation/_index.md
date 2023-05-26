---
title: Встроить шрифт при создании документа
linktitle: Встроить шрифт при создании документа
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как внедрить шрифт при создании документа PDF с помощью Aspose.PDF для .NET. Обеспечьте правильное отображение на разных устройствах.
type: docs
weight: 140
url: /ru/net/programming-with-document/embedfontwhiledoccreation/
---

В этом руководстве мы обсудим, как внедрить шрифт при создании документа PDF с помощью Aspose.PDF для .NET. Aspose.PDF для .NET — это мощная библиотека, которая позволяет разработчикам программно создавать, редактировать и управлять PDF-документами. Эта библиотека предоставляет широкий спектр функций для работы с PDF-документами, включая добавление текста, изображений, таблиц и многое другое. Встраивание шрифтов при создании PDF-документа — обычное требование для разработчиков, которые хотят обеспечить правильное отображение PDF-документа на разных устройствах, независимо от того, установлены ли на этих устройствах требуемые шрифты или нет.

## Шаг 1. Создайте новое консольное приложение C#
Для начала создайте новое консольное приложение C# в Visual Studio. Вы можете назвать это как угодно. После создания проекта необходимо добавить ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте пространство имен Aspose.PDF
Добавьте следующую строку кода вверху файла C#, чтобы импортировать пространство имен Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Шаг 3: Создайте объект Pdf
Создайте экземпляр объекта Pdf, вызвав его пустой конструктор:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Шаг 4: Создайте раздел в объекте Pdf
Создайте раздел в объекте Pdf:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Шаг 5: Добавьте текст в раздел
Добавьте текст в раздел:

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## Шаг 6: Установите шрифт и вставьте его
Установите шрифт и вставьте его:

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## Шаг 7: Сохраните PDF-документ
После того, как вы внедрили шрифт при создании документа PDF, вам необходимо сохранить документ:

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Сохранить PDF-документ
doc.Save(dataDir);
```

### Пример исходного кода для встраивания шрифта при создании документа с использованием Aspose.PDF для .NET

```csharp

            
            // Путь к каталогу документов.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Создайте экземпляр объекта Pdf, вызвав его пустой конструктор
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

            // Создайте раздел в объекте Pdf
            Aspose.Pdf.Page page = doc.Pages.Add();

            Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

            Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
            Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
            ts.Font = FontRepository.FindFont("Arial");
            ts.Font.IsEmbedded = true;
            segment.TextState = ts;
            fragment.Segments.Add(segment);
            page.Paragraphs.Add(fragment);

            dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
            // Сохранить PDF-документ
            doc.Save(dataDir);
            
            
        
```

## Заключение
В этом руководстве мы обсудили, как внедрить шрифт при создании документа PDF с помощью Aspose.PDF для .NET. Aspose.PDF для .NET предоставляет простой и удобный API для работы с PDF-документами, включая добавление и встраивание шрифтов. Встраивание шрифтов при создании PDF-документа является важным шагом для обеспечения правильного отображения документа на разных устройствах, независимо от того, установлены ли на этих устройствах необходимые шрифты или нет.

