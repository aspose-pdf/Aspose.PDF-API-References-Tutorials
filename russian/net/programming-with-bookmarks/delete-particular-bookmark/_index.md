---
title: Удалить конкретную закладку
linktitle: Удалить конкретную закладку
second_title: Aspose.PDF для справочника API .NET
description: Легко удаляйте определенные закладки из файлов PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 40
url: /ru/net/programming-with-bookmarks/delete-particular-bookmark/
---

Может потребоваться удалить определенную закладку из документа PDF. С помощью Aspose.PDF для .NET вы можете легко удалить определенную закладку, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, из которого вы хотите удалить ту или иную закладку. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы собираемся открыть документ PDF, из которого мы хотим удалить закладку, используя следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
```

## Шаг 4. Удалите определенную закладку

 На этом шаге мы удаляем конкретную закладку, используя`Delete` метод`Outlines` свойство. Указываем название удаляемой закладки. Вот соответствующий код:

```csharp
pdfDocument.Outlines.Delete("Child Outline");
```

## Шаг 5: Сохраните обновленный файл

 Наконец, мы сохраняем обновленный PDF-файл, используя`Save` метод`pdfDocument` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для удаления определенной закладки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
// Удалить конкретный план по заголовку
pdfDocument.Outlines.Delete("Child Outline");
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
// Сохранить обновленный файл
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по удалению определенной закладки с помощью Aspose.PDF для .NET. Вы можете использовать этот код для нацеливания и удаления определенных закладок из ваших PDF-документов.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.