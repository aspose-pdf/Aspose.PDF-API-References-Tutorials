---
title: Заменить таблицу
linktitle: Заменить таблицу
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как заменить таблицу в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 180
url: /ru/net/programming-with-tables/replace-table/
---

В этом руководстве мы шаг за шагом проведем вас по замене таблицы в документе PDF с помощью Aspose.PDF для .NET. Мы объясним предоставленный исходный код C# и покажем, как его реализовать.

## Шаг 1: Загрузка существующего документа PDF
Во-первых, вам нужно загрузить существующий PDF-документ, используя следующий код:

```csharp
// Путь к каталогу документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите существующий PDF-документ
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Шаг 2: Создание объекта TableAbsorber для поиска таблиц
Далее мы создадим объект TableAbsorber для поиска таблиц в документе PDF:

```csharp
// Создайте объект TableAbsorber, чтобы найти таблицы
TableAbsorber absorber = new TableAbsorber();
```

## Шаг 3: Посетите первую страницу с поглотителем
Теперь мы посетим первую страницу PDF-документа с помощью поглотителя:

```csharp
// Посетите первую страницу с поглотителем
absorb.Visit(pdfDocument.Pages[1]);
```

## Шаг 4: Получение первой таблицы на странице
Чтобы иметь возможность заменить таблицу, мы получим первую таблицу страницы:

```csharp
// Получить первую таблицу на странице
AbsorbedTable table = absorb.TableList[0];
```

## Шаг 5: Создание новой таблицы
Теперь создадим новую таблицу с нужными столбцами и ячейками:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Шаг 6: Замена существующей таблицы новой таблицей
Теперь мы заменим существующую таблицу новой таблицей на первой странице документа:

```csharp
// Заменить таблицу новой таблицей
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Шаг 7: Сохранение документа
Наконец, мы сохраняем измененный PDF-документ:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Пример исходного кода для замены таблицы с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузить существующий PDF-документ
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Создайте объект TableAbsorber для поиска таблиц
TableAbsorber absorber = new TableAbsorber();

// Посетите первую страницу с поглотителем
absorber.Visit(pdfDocument.Pages[1]);

// Получить первую таблицу на странице
AbsorbedTable table = absorber.TableList[0];

// Создать новую таблицу
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Замените таблицу на новую
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Сохранить документ
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Заключение
Поздравляем! Теперь вы узнали, как заменить таблицу в документе PDF с помощью Aspose.PDF для .NET. В этом пошаговом руководстве показано, как загрузить документ, найти существующую таблицу, создать новую таблицу и заменить ее. Теперь вы можете применить эти знания в своих проектах.