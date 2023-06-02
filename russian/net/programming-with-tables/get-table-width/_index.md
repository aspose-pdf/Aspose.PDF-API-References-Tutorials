---
title: Получить ширину таблицы
linktitle: Получить ширину таблицы
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как получить ширину таблицы в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-tables/get-table-width/
---

В этом уроке мы узнаем, как получить ширину таблицы в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого урока вы узнаете, как получить ширину таблицы в документе PDF. Давайте начнем!

## Шаг 1. Настройка среды
Во-первых, убедитесь, что вы настроили среду разработки C# с Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2: Создание нового документа и страницы
Мы создаем новый документ PDF и добавляем страницу в этот документ.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Шаг 3: Инициализация новой таблицы
Мы инициализируем новую таблицу и устанавливаем для столбца значение «AutoFitToContent».

```csharp
Table table = new Table
{
ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
```

## Шаг 4: Добавьте строку и ячейки в таблицу
Мы добавляем строку в таблицу и добавляем ячейки в эту строку.

```csharp
Row row = table.Rows.Add();
Cell cell = row.Cells.Add("Text of cell 1");
cell = row.Cells.Add("Text from cell 2");
```

## Шаг 5: Получите ширину таблицы
Мы используем метод «GetWidth()», чтобы получить ширину таблицы.

```csharp
Console.WriteLine(table.GetWidth());
```

### Пример исходного кода для получения ширины таблицы с использованием Aspose.Words для .NET

```csharp
// Создать новый документ
Document doc = new Document();
// Добавить страницу в документ
Page page = doc.Pages.Add();
// Инициализировать новую таблицу
Table table = new Table
{
	ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
// Добавить строку в таблицу
Row row = table.Rows.Add();
// Добавить ячейку в таблицу
Cell cell = row.Cells.Add("Cell 1 text");
cell = row.Cells.Add("Cell 2 text");
// Получить ширину таблицы
Console.WriteLine(table.GetWidth());

System.Console.WriteLine("Extracted table width succesfully!");
```

## Заключение
В этом руководстве мы узнали, как получить ширину таблицы в документе PDF с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство, чтобы получить ширину таблицы в своих собственных проектах C#.