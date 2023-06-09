---
title: Получить закладки
linktitle: Получить закладки
second_title: Aspose.PDF для справочника API .NET
description: С легкостью добавляйте в закладки свои PDF-файлы с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-bookmarks/get-bookmarks/
---

Извлечение закладок из документа PDF может быть полезно для анализа структуры документа и навигационной информации. С помощью Aspose.PDF для .NET вы можете легко получить закладки, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, из которого вы хотите извлечь закладки. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы собираемся открыть документ PDF, из которого мы хотим извлечь закладки, используя следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
```

## Шаг 4. Просмотр закладок

На этом шаге мы пройдемся по всем закладкам в документе, используя`foreach` петля. Для каждой закладки мы будем отображать такую информацию, как заголовок, курсив, полужирный стиль и цвет. Вот соответствующий код:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
}
```

### Пример исходного кода для получения закладок с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetBookmarks.pdf");
// Перебрать все закладки
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
}
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по получению закладок с помощью Aspose.PDF для .NET. Вы можете использовать этот код для анализа закладок и извлечения информации, связанной с каждой закладкой в ваших документах PDF.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.