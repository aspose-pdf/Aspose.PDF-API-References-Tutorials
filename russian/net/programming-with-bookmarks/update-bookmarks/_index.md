---
title: Обновить закладки
linktitle: Обновить закладки
second_title: Aspose.PDF для справочника API .NET
description: Легко обновляйте закладки в ваших PDF-файлах с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-bookmarks/update-bookmarks/
---

Обновление закладок в документе PDF часто необходимо для отражения изменений или обновлений в структуре или содержании документа. С помощью Aspose.PDF для .NET вы можете легко обновлять закладки, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, который вы хотите обновить. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы откроем PDF-документ, который хотим обновить, используя следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
```

## Шаг 4: Получите объект закладки

На этом шаге мы получим конкретный объект закладки, который хотим обновить. В приведенном ниже примере мы извлекаем закладку с индексом 1 (вторая закладка в коллекции закладок). Вы можете настроить индекс в соответствии с вашими потребностями. Вот соответствующий код:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Шаг 5. Обновите свойства закладки

Теперь давайте обновим свойства закладки, такие как заголовок, курсив и полужирный стиль. Вы можете настроить эти свойства в соответствии с вашими потребностями. Вот соответствующий код:

```csharp
pdfOutline.Title = "Updated Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Шаг 6: Сохраните обновленный файл

Теперь давайте сохраним обновленный PDF-файл, используя`Save` метод`pdfDocument` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "UpdateBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для обновления закладок с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "UpdateBookmarks.pdf");
// Получить объект закладки
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
pdfOutline.Title = "Updated Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
dataDir = dataDir + "UpdateBookmarks_out.pdf";
// Сохранить вывод
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по обновлению закладок с помощью Aspose.PDF для .NET. Вы можете использовать этот код для изменения заголовков и стилей закладок в ваших документах PDF.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.