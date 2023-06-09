---
title: Добавить закладку
linktitle: Добавить закладку
second_title: Aspose.PDF для справочника API .NET
description: Легко добавляйте закладки в файлы PDF для улучшения навигации с помощью Aspose.PDF для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/add-bookmark/
---

Добавление закладок в PDF-документ обеспечивает простую и быструю навигацию. С помощью Aspose.PDF для .NET вы можете легко добавить закладку, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, в который вы хотите добавить закладку. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы откроем документ PDF, к которому мы хотим добавить закладку, используя следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Шаг 4: Создайте объект закладки

 На этом шаге мы создадим объект закладки, используя`OutlineItemCollection` class и установите его свойства, такие как заголовок, атрибут курсива, атрибут полужирного шрифта и действие, которое будет выполняться при нажатии. Вот соответствующий код:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Шаг 5: Добавьте закладку в документ

 Наконец, мы добавляем созданную закладку в коллекцию закладок документа, используя метод`Add` метод`Outlines` свойство. Вот соответствующий код:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Пример исходного кода для добавления закладки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Создать объект закладки
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Установите номер целевой страницы
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Добавьте закладку в коллекцию структуры документа.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Сохранить вывод
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по добавлению закладки с помощью Aspose.PDF для .NET. Вы можете использовать этот код для улучшения навигации в документах PDF, добавляя пользовательские закладки.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.