---
title: Удалить открытое действие
linktitle: Удалить открытое действие
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как удалить действие открытия из PDF-файла с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-links-and-actions/remove-open-action/
---

Из этого пошагового руководства вы узнаете, как удалить действие открытия из файла PDF с помощью Aspose.PDF для .NET.

## Шаг 1. Настройка среды

Убедитесь, что вы настроили среду разработки с проектом C# и соответствующими ссылками на Aspose.PDF.

## Шаг 2: Загрузка файла PDF

Установите путь к каталогу ваших документов и загрузите файл PDF, используя следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Откройте документ
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Шаг 3: Удаление открытого действия

 Удалите действие открытия из документа, установив`OpenAction` свойство в ноль:

```csharp
document. OpenAction = null;
```

## Шаг 4: Сохраните обновленный документ

 Сохраните обновленный документ с помощью`Save` метод:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Шаг 5: Отображение результата

Вывести сообщение о том, что действие открытия было успешно удалено, и указать расположение сохраненного файла:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Пример исходного кода для удаления открытого действия с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Удалить действие открытия документа
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Сохранить обновленный документ
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Заключение

Поздравляем! Теперь вы знаете, как удалить действие открытия из PDF-файла с помощью Aspose.PDF для .NET. Используйте эти знания для настройки свойств и поведения PDF-файлов в ваших проектах.

Теперь, когда вы завершили это руководство, вы можете применить эти концепции к своим собственным проектам и дополнительно изучить функции, предлагаемые Aspose.PDF для .NET.