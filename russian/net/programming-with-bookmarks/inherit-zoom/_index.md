---
title: Наследовать Zoom
linktitle: Наследовать Zoom
second_title: Aspose.PDF для справочника API .NET
description: Легко наследуйте масштабирование закладок в ваших PDF-файлах с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-bookmarks/inherit-zoom/
---

Наследование масштаба в документе PDF позволяет указать уровень масштабирования по умолчанию для закладок. С Aspose.PDF для .NET вы можете легко наследовать масштабирование, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Шаг 2. Укажите путь к папке с документами.

На этом шаге вам нужно указать путь к папке, содержащей PDF-файл, от которого вы хотите унаследовать масштаб. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы собираемся открыть документ PDF, для которого мы хотим унаследовать масштаб, используя следующий код:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 4: Получите коллекцию закладок

 На этом шаге мы получим коллекцию закладок или ориентиров документа с помощью`Outlines` собственность`doc` объект. Вот соответствующий код:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Шаг 5: Установите уровень масштабирования

 Теперь мы установим уровень масштабирования, создав`XYZExplicitDestination` объект с указанными координатами x, y и z. Здесь мы используем координаты (100, 100, 0) с масштабом 2. Вот соответствующий код:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Шаг 6: Добавьте уровень масштабирования в закладки

 На этом этапе мы добавляем`XYZExplicitDestination` объект как действие к закладкам`item` коллекция. Вот соответствующий код:

```csharp
item. Action = new GoToAction(dest);
```

## Шаг 7: Добавьте обновленные закладки в документ

 Наконец, мы добавляем обновленные закладки в коллекцию закладок документа, используя метод`Add` метод`doc.Outlines` объект. Вот соответствующий код:

```csharp
doc. Outlines. Add(item);
```

## Шаг 8: Сохраните обновленный файл

Теперь давайте сохраним обновленный PDF-файл, используя`Save` метод`doc` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для Inherit Zoom с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document doc = new Document(dataDir + "input.pdf");
// Получить коллекцию контуров/закладок PDF-файла
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Установите уровень масштабирования как 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Добавить XYZExplicitDestination в качестве действия для составления коллекции PDF-файлов
item.Action = new GoToAction(dest);
// Добавить элемент в коллекцию контуров PDF-файла
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Сохранить вывод
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по наследованию Zoom с помощью Aspose.PDF для .NET. Вы можете использовать этот код, чтобы указать уровень масштабирования по умолчанию для закладок в ваших PDF-документах.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.