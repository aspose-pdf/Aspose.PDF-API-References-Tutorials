---
title: Текст в нижнем колонтитуле
linktitle: Текст в нижнем колонтитуле
second_title: Aspose.PDF для справочника API .NET
description: Научитесь добавлять текст в нижний колонтитул документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 180
url: /ru/net/programming-with-stamps-and-watermarks/text-in-footer/
---
В этом уроке мы узнаем, как добавить текст в нижний колонтитул PDF-документа, используя Aspose.PDF для .NET. Выполните следующие действия:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 4: Создайте текст нижнего колонтитула

Создайте новый текстовый штамп с текстом, который вы хотите добавить в нижний колонтитул:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Вы можете настроить текст, изменив его свойства, такие как нижнее поле, выравнивание по горизонтали и выравнивание по вертикали.

## Шаг 5: Добавьте текст нижнего колонтитула на все страницы

Просмотрите все страницы PDF-документа и добавьте текстовый штамп в нижний колонтитул:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Шаг 6: Сохранение PDF-документа

После добавления текста нижнего колонтитула на все страницы сохраните обновленный PDF-документ:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором вы хотите сохранить PDF-документ.

### Пример исходного кода для нижнего колонтитула Textin с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Создать нижний колонтитул
TextStamp textStamp = new TextStamp("Footer Text");

// Установить свойства штампа
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Добавить нижний колонтитул на все страницы
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Сохранить обновленный файл PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Заключение

Поздравляем! Вы узнали, как добавить текст в нижний колонтитул PDF-документа с помощью Aspose.PDF для .NET. Теперь вы можете настраивать нижние колонтитулы, добавляя дополнительный текст в документы PDF.
