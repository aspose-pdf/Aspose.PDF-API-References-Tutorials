---
title: Получить номер страницы закладки в PDF-файле
linktitle: Получить номер страницы закладки в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Легко получите номер страницы закладки в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-bookmarks/get-bookmark-page-number/
---
Получение номеров страниц, связанных с закладками в PDF-файле, может быть полезно для навигации. С помощью Aspose.PDF для .NET вы можете легко получить номер страницы закладок, выполнив следующий исходный код:

## Шаг 1. Импортируйте необходимые библиотеки.

Прежде чем начать, вам необходимо импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf.Facades;
```

## Шаг 2. Установите путь к папке с документами.

 На этом этапе вам необходимо указать путь к папке, содержащей PDF-файл, из которого вы хотите извлечь номера страниц закладок. Заменять`"YOUR DOCUMENT DIRECTORY"`в следующем коде с фактическим путем к папке ваших документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3. Создайте редактор закладок.

 Теперь мы создадим`PdfBookmarkEditor` объект для управления закладками документа. Используйте следующий код:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Шаг 4: Откройте PDF-файл

 На этом этапе мы открываем PDF-файл с помощью`BindPdf` метод редактора закладок. Вот соответствующий код:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Шаг 5. Извлеките закладки

 Теперь мы извлечем закладки из документа с помощью`ExtractBookmarks` метод редактора закладок. Вот соответствующий код:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Шаг 6. Просмотрите закладки и получите номера страниц.

 Наконец, мы просматриваем извлеченные закладки и получаем номера страниц, связанных с каждой закладкой, используя`foreach` петля. Вот соответствующий код:

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
// Создать PDFBookmarkEditor
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

Поздравляем! Теперь у вас есть пошаговое руководство по получению номеров страниц закладок с помощью Aspose.PDF для .NET. Вы можете использовать этот код для получения навигационной информации, связанной с каждой закладкой в ваших PDF-документах.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.

### Часто задаваемые вопросы по получению номера страницы закладки в PDF-файле

#### Вопрос: Что такое закладки в PDF-файле?

О: Закладки в PDF-файле — это средства навигации, которые позволяют пользователям быстро переходить к определенным разделам или страницам документа. Они улучшают взаимодействие с пользователем, предоставляя ярлыки к соответствующему контенту.

#### Вопрос: Зачем мне получать номера страниц закладок из PDF-файла?

Ответ: Получение номеров страниц закладок помогает пользователям более эффективно перемещаться по документу, обеспечивая четкое представление о том, куда ведет каждая закладка. Это особенно полезно для более длинных документов с несколькими разделами.

#### Вопрос: Как мне импортировать необходимые библиотеки для моего проекта C#?

О: Чтобы импортировать необходимую библиотеку для вашего проекта C#, используйте следующую директиву импорта:

```csharp
using Aspose.Pdf.Facades;
```

Эта директива позволяет вам использовать классы и методы, предоставляемые Aspose.PDF для .NET.

#### Вопрос: Как указать путь к папке с документами?

 О: В предоставленном исходном коде замените`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к папке, содержащей PDF-файл, из которого вы хотите извлечь номера страниц закладок. Это гарантирует, что код сможет найти целевой PDF-файл.

#### Вопрос: Как создать редактор закладок?

О: Чтобы создать редактор закладок, используйте следующий код:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Вопрос: Как открыть PDF-файл для манипуляций с закладками?

О: Чтобы открыть PDF-файл для извлечения информации о закладках, используйте следующий код:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Заменять`"GetBookmarks.pdf"` с фактическим именем файла.

#### Вопрос: Как извлечь закладки из PDF-файла?

 О: Чтобы извлечь закладки из PDF-файла, используйте команду`ExtractBookmarks` метод редактора закладок:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Вопрос: Как получить и отобразить номера страниц закладок?

 A: Прокрутите извлеченные закладки с помощью`foreach` цикл и доступ к`PageNumber` свойство каждой закладки для получения и отображения связанного с ней номера страницы:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Вопрос: Могу ли я изменить свойства закладок, используя этот подход?

 О: Хотя в этом руководстве основное внимание уделяется получению номеров страниц закладок, вы можете изменить другие свойства закладок, используя тот же`Bookmark`объект и связанные с ним свойства.

#### Вопрос: Как сохранить обновленный PDF-файл после извлечения информации о закладках?

О: Извлечение закладки не изменяет исходный PDF-файл. Если вы хотите сохранить какие-либо изменения, вы можете сделать это, используя другие методы, предоставляемые Aspose.PDF для .NET.