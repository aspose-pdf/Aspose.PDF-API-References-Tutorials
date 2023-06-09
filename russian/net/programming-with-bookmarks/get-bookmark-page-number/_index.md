---
title: Получить номер страницы закладки
linktitle: Получить номер страницы закладки
second_title: Aspose.PDF для справочника API .NET
description: Легко получайте номера страниц закладок из ваших файлов PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-bookmarks/get-bookmark-page-number/
---

Получение номеров страниц, связанных с закладками в документе PDF, может быть полезно для навигации. С помощью Aspose.PDF для .NET вы можете легко получить количество страниц закладок, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf.Facades;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, из которого вы хотите извлечь номера страниц закладок. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Создайте редактор закладок

 Теперь мы создадим`PdfBookmarkEditor` объект для управления закладками документа. Используйте следующий код:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Шаг 4: Откройте файл PDF

 На этом шаге мы открываем файл PDF с помощью`BindPdf` метод редактора закладок. Вот соответствующий код:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Шаг 5. Извлеките закладки

 Теперь мы извлечем закладки из документа с помощью`ExtractBookmarks` метод редактора закладок. Вот соответствующий код:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Шаг 6. Просмотрите закладки и получите номера страниц

 Наконец, мы перебираем извлеченные закладки и получаем номера страниц, связанные с каждой закладкой, используя`foreach` петля. Вот соответствующий код:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Пример исходного кода для получения номера страницы закладки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Открыть PDF-файл
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Извлечь закладки
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по получению номеров страниц закладок с помощью Aspose.PDF для .NET. Вы можете использовать этот код для получения навигационной информации, связанной с каждой закладкой в ваших документах PDF.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.