---
title: Получить дочерние закладки
linktitle: Получить дочерние закладки
second_title: Aspose.PDF для справочника API .NET
description: Легко получайте дочерние закладки ваших PDF-файлов с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-bookmarks/get-child-bookmarks/
---

Извлечение дочерних закладок из документа PDF может быть полезно для изучения иерархической структуры закладок. С помощью Aspose.PDF для .NET вы можете легко получить дочерние закладки, следуя следующему исходному коду:

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
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## Шаг 4. Просмотр закладок и дочерних закладок

На этом шаге мы пройдемся по всем закладкам в документе, используя`foreach`петля. Для каждой закладки мы будем отображать такую информацию, как заголовок, курсив, полужирный стиль и цвет. Если у закладки есть дочерние закладки, мы также отобразим их. Вот соответствующий код:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // Просмотр дочерних закладок, а также
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### Пример исходного кода для получения дочерних закладок с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// Перебрать все закладки
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// Есть дочерние закладки, а затем прокручивайте их.
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по получению дочерних закладок с помощью Aspose.PDF для .NET. Вы можете использовать этот код для изучения иерархической структуры закладок и получения подробной информации о каждой закладке и ее дочерних закладках в ваших документах PDF.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.