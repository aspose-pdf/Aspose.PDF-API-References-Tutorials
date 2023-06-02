---
title: Установить границу
linktitle: Установить границу
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как установить границу в таблице PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 200
url: /ru/net/programming-with-tables/set-border/
---

В этом уроке мы шаг за шагом поможем вам установить границу в таблице PDF-документа с помощью Aspose.PDF для .NET. Мы объясним предоставленный исходный код C# и покажем, как его реализовать.

## Шаг 1: Создание экземпляра объекта Document
Во-первых, мы создадим экземпляр объекта Document:

```csharp
Document doc = new Document();
```

## Шаг 2. Добавление страницы в документ PDF
Далее мы добавим страницу в документ PDF:

```csharp
Page page = doc.Pages.Add();
```

## Шаг 3: Создание объекта BorderInfo
Теперь мы создадим объект BorderInfo для определения границы таблицы:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Шаг 4: Указание верхней и нижней границ
Мы укажем, что верхняя и нижняя границы будут двойными:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Шаг 5: Создание экземпляра объекта Table
Теперь давайте создадим экземпляр объекта Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Шаг 6: Указание ширины столбцов
Укажем ширину столбцов таблицы:

```csharp
table. ColumnWidths = "100";
```

## Шаг 7: Создание объекта строки
Мы создадим объект Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Шаг 8: Добавление ячейки в строку
Далее мы добавим ячейку в строку:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Шаг 9: Установка границы ячейки
Мы собираемся определить границу ячейки (двойная граница):

```csharp
cell. Border = border;
```

## Шаг 10: Добавление таблицы на страницу
Теперь добавим таблицу на страницу документа:

```csharp
page.Paragraphs.Add(table);
```

## Шаг 11: Сохраните PDF-документ
Наконец, мы сохраним документ PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Пример исходного кода для установки границы с использованием Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать объект документа
Document doc = new Document();
// Добавить страницу в документ PDF
Page page = doc.Pages.Add();
// Создать объект BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// Укажите, что верхняя граница будет двойной
border.Top.IsDoubled = true;
// Укажите, что нижняя граница будет двойной
border.Bottom.IsDoubled = true;
// Создание экземпляра объекта таблицы
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Укажите информацию о ширине столбцов
table.ColumnWidths = "100";
// Создать объект строки
Aspose.Pdf.Row row = table.Rows.Add();
// Добавить ячейку таблицы в коллекцию ячеек строки
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Установите границу для объекта ячейки (двойная граница)
cell.Border = border;
//Добавить таблицу в коллекцию абзацев страницы
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Сохраните PDF-документ
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Заключение
Поздравляем! Теперь вы узнали, как установить границу в таблице PDF-документа с помощью Aspose.PDF для .NET. В этом пошаговом руководстве показано, как создать документ, добавить страницу, настроить границу таблицы и сохранить документ PDF. Теперь вы можете применить эти знания в своих проектах.