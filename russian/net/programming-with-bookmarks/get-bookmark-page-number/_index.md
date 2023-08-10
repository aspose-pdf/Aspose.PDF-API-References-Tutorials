---
title: Получить номер страницы закладки в файле PDF
linktitle: Получить номер страницы закладки в файле PDF
second_title: Aspose.PDF для справочника API .NET
description: Легко получить номер страницы закладки в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-bookmarks/get-bookmark-page-number/
---
Получение номеров страниц, связанных с закладками в файле PDF, может быть полезно для навигации. С помощью Aspose.PDF для .NET вы можете легко получить количество страниц закладок, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf.Facades;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, из которого вы хотите извлечь номера страниц закладок. Заменять`"YOUR DOCUMENT DIRECTORY"`в следующем коде с фактическим путем к вашей папке документов:

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

### Часто задаваемые вопросы для получения номера страницы закладки в файле PDF

#### В: Что такое закладки в файле PDF?

О: Закладки в файле PDF — это средства навигации, которые позволяют пользователям быстро переходить к определенным разделам или страницам документа. Они улучшают взаимодействие с пользователем, предоставляя ярлыки для соответствующего контента.

#### В: Зачем мне извлекать номера страниц закладок из PDF-файла?

О: Получение номеров страниц закладок помогает пользователям более эффективно перемещаться по документу, предоставляя четкое указание, куда ведет каждая закладка. Это особенно полезно для длинных документов с несколькими разделами.

#### В: Как мне импортировать необходимые библиотеки для моего проекта C#?

О: Чтобы импортировать необходимую библиотеку для вашего проекта C#, используйте следующую директиву импорта:

```csharp
using Aspose.Pdf.Facades;
```

Эта директива позволяет вам использовать классы и методы, предоставляемые Aspose.PDF для .NET.

#### В: Как указать путь к папке с документами?

 A: В предоставленном исходном коде замените`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к папке, содержащей файл PDF, из которого вы хотите извлечь номера страниц закладок. Это гарантирует, что код сможет найти целевой PDF-файл.

#### Q: Как мне создать редактор закладок?

A: Чтобы создать редактор закладок, используйте следующий код:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### В: Как открыть PDF-файл для работы с закладками?

О: Чтобы открыть файл PDF для извлечения информации о закладках, используйте следующий код:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Заменять`"GetBookmarks.pdf"` с реальным именем файла.

#### В: Как извлечь закладки из файла PDF?

 О: Чтобы извлечь закладки из PDF-файла, используйте`ExtractBookmarks` метод редактора закладок:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### В: Как получить и отобразить номера страниц закладок?

 A: Прокрутите извлеченные закладки, используя`foreach` цикл и получить доступ к`PageNumber` свойство каждой закладки для извлечения и отображения связанного с ней номера страницы:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Вопрос. Можно ли изменить свойства закладок, используя этот подход?

 О: Хотя в этом руководстве основное внимание уделяется получению номеров страниц закладок, вы можете изменить другие свойства закладок, используя тот же`Bookmark`объекта и связанных с ним свойств.

#### В: Как сохранить обновленный PDF-файл после извлечения информации о закладках?

О: Извлечение закладок не изменяет исходный PDF-файл. Если вы хотите сохранить какие-либо изменения, вы можете сделать это с помощью других методов, предоставляемых Aspose.PDF для .NET.