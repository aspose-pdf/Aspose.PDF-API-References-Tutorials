---
title: Текст в заголовке
linktitle: Текст в заголовке
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить текст в заголовок документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 190
url: /ru/net/programming-with-stamps-and-watermarks/text-in-header/
---
В этом уроке мы узнаем, как добавить текст в заголовок PDF-документа, используя Aspose.PDF для .NET. Выполните следующие действия:

## Шаг 1: Подготовка проекта

Убедитесь, что вы установили Aspose.PDF для .NET и создали проект C#.

## Шаг 2. Импорт пространств имен

Добавьте в исходный файл C# следующие пространства имен:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Шаг 3: Открытие документа

Откройте существующий документ PDF, используя указанный путь:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 4: Создание текста заголовка

Создайте новый текстовый штамп с текстом, который вы хотите добавить в заголовок:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Вы можете настроить текст, изменив его свойства, такие как верхнее поле, выравнивание по горизонтали и выравнивание по вертикали.

## Шаг 5: Добавьте текст заголовка на все страницы

Пройдитесь по всем страницам PDF-документа и добавьте текстовый штамп в шапку:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Шаг 6: Сохранение PDF-документа

Как только текст заголовка будет добавлен на все страницы, сохраните обновленный PDF-документ:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором вы хотите сохранить PDF-документ.

### Пример исходного кода для заголовка Textin с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Создать заголовок
TextStamp textStamp = new TextStamp("Header Text");

// Установить свойства штампа
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Добавить заголовок на всех страницах
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Сохранить обновленный документ
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Заключение

Поздравляем! Вы узнали, как добавить текст в заголовок PDF-документа с помощью Aspose.PDF для .NET. Теперь вы можете настраивать заголовки, добавляя дополнительный текст в документы PDF.
