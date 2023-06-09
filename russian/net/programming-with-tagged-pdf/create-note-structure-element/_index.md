---
title: Создать элемент структуры заметки
linktitle: Создать элемент структуры заметки
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по созданию структурированных заметок в документе PDF с использованием Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-tagged-pdf/create-note-structure-element/
---
В этом руководстве мы предоставим вам пошаговое руководство по созданию элемента структуры заметки в документе PDF с использованием Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно создавать, обрабатывать и конвертировать PDF-документы. Используя отмеченные функции структуры содержимого Aspose.PDF, вы можете добавлять структурированные заметки в свой PDF-документ.

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

## Шаг 3: Создание документа PDF и структурированных элементов заметок

Используйте следующий код для создания документа PDF и добавления структурированных элементов заметок:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Этот код создает пустой документ PDF и добавляет в абзац структурированные элементы примечания. Каждая заметка создается с использованием методов, предоставляемых Aspose.PDF.

## Шаг 4: Сохранение PDF-документа

Используйте следующий код для сохранения PDF-документа:

```csharp
document. Save(outFile);
```

Этот код сохраняет PDF-документ со структурными элементами примечания в указанный файл.

### Пример исходного кода для создания элемента структуры заметки с использованием Aspose.PDF для .NET 

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Создать PDF-документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Добавить элемент абзаца
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Добавить элемент примечания
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Добавить элемент примечания
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Добавить элемент примечания
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//Необходимо генерировать исключение - Aspose.Pdf.Tagged.TaggedException: элемент структуры с идентификатором = 'note_002' уже существует
//note3.SetId("note_002");
// Результирующий документ не соответствует PDF/UA, если ClearId() используется для элемента структуры примечания
//примечание3.ClearId();
// Сохранить документ в формате PDF с тегами
document.Save(outFile);
// Проверка соответствия PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом руководстве вы узнали, как создавать элементы структуры заметок в документе PDF с помощью Aspose.PDF для .NET. Элементы структурированных заметок позволяют добавлять в документ PDF дополнительную структурированную информацию.
