---
title: Удалить все закладки
linktitle: Удалить все закладки
second_title: Aspose.PDF для справочника API .NET
description: Легко удаляйте все закладки из файлов PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-bookmarks/delete-all-bookmarks/
---

# Удалить все закладки с помощью Aspose.PDF для .NET

В некоторых случаях может потребоваться удаление закладок из PDF-документа. С помощью Aspose.PDF для .NET вы можете легко удалить все закладки, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, из которого вы хотите удалить закладки. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы собираемся открыть документ PDF, из которого мы хотим удалить закладки, используя следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Шаг 4. Удалите все закладки

 На этом шаге мы удаляем все закладки из документа с помощью`Delete` метод`Outlines` свойство. Вот соответствующий код:

```csharp
pdfDocument.Outlines.Delete();
```

## Шаг 5: Сохраните обновленный файл

 Наконец, мы сохраняем обновленный PDF-файл, используя`Save` метод`pdfDocument` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для удаления всех закладок с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Удалить все закладки
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Сохранить обновленный файл
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по удалению всех закладок с помощью Aspose.PDF для .NET. Вы можете использовать этот код для очистки ваших PDF-документов, удалив все существующие закладки.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.