---
title: Добавить дочернюю закладку
linktitle: Добавить дочернюю закладку
second_title: Aspose.PDF для справочника API .NET
description: Легко добавляйте дочерние закладки в файлы PDF для более организованного просмотра с помощью Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/programming-with-bookmarks/add-child-bookmark/
---

Добавление дочерних закладок в документ PDF обеспечивает более структурированную организацию и навигацию. С помощью Aspose.PDF для .NET вы можете легко добавить вложенную закладку, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, в который вы хотите добавить вложенную закладку. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы откроем документ PDF, к которому мы хотим добавить вложенную закладку, используя следующий код:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Шаг 4: Создайте родительский объект закладки

 На этом шаге мы создадим родительский объект закладки, используя`OutlineItemCollection` class и задайте его свойства, такие как заголовок, атрибут курсива и атрибут полужирного шрифта. Вот соответствующий код:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Шаг 5: Создайте дочерний объект закладки

На этом шаге мы снова создадим объект вложенной закладки, используя`OutlineItemCollection` класс и установить его свойства. Вот соответствующий код:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Шаг 6: Добавьте вложенную закладку к родительской закладке

 Наконец, мы добавляем созданную вложенную закладку в коллекцию вложенных закладок родительской закладки, используя метод`Add` метод родительского объекта. Вот соответствующий код:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Шаг 7. Добавьте родительскую закладку в коллекцию закладок документа

 Наконец, мы добавляем родительскую закладку в коллекцию закладок документа, используя метод`Add` метод`Outlines` свойство. Вот соответствующий код:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Пример исходного кода для добавления дочерней закладки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Создать родительский объект закладки
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Создать дочерний объект закладки
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Добавить дочернюю закладку в коллекцию родительских закладок
pdfOutline.Add(pdfChildOutline);
// Добавьте родительскую закладку в коллекцию структуры документа.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Сохранить вывод
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по добавлению вложенной закладки с помощью Aspose.PDF для .NET. Вы можете использовать этот код для организации и структурирования закладок в документах PDF.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях управления закладками.