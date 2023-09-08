---
title: Добавить повторяющийся столбец в PDF-документ
linktitle: Добавить повторяющийся столбец в PDF-документ
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как добавить повторяющийся столбец в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/programming-with-tables/add-repeating-column/
---
В этом уроке мы узнаем, как добавить повторяющийся столбец в PDF-документ, используя Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого урока вы узнаете, как создать таблицу с повторяющимся столбцом в PDF-документе. Давайте начнем!

## Шаг 1. Настройка среды
Сначала убедитесь, что вы настроили свою среду разработки C# с помощью Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2. Создание PDF-документа
На этом этапе мы создаем новый PDF-документ.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Мы создали пустой PDF-документ, в который можно добавлять контент.

## Шаг 3. Создание таблиц
На этом этапе мы создаем основную таблицу (`outerTable`) и вложенную таблицу (`mytable`), который будет повторяться в столбце.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Мы указали свойства таблицы, такие как ширина столбца и режим разрыва вложенной таблицы.

## Шаг 4. Добавление таблиц в документ
Теперь добавляем созданные таблицы в PDF-документ.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Сначала добавляем основную таблицу (`outerTable`) в документ PDF. Далее мы добавляем вложенную таблицу (`mytable` ) как абзац в ячейке основной таблицы. Мы также указываем количество повторяющихся столбцов для`mytable` (в данном примере 5 столбцов).

## Шаг 5. Добавление заголовков и строк
Теперь добавим в таблицу заголовки и строки.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Добавьте сюда другие заголовки

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Добавьте сюда остальные столбцы
}
```

Сначала добавляем заголовки в первую строку таблицы (`headerRow`). Затем мы добавляем строки данных из цикла. В этом примере мы добавляем 6 строк данных.

## Шаг 6. Сохранение PDF-документа
Наконец, мы сохраняем PDF-документ в указанный файл.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Обязательно укажите правильный каталог и имя файла для сохранения выходного PDF-файла.

### Пример исходного кода для добавления повторяющегося столбца с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Создать новый документ
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Создайте экземпляр внешней таблицы, занимающей всю страницу.
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Создайте экземпляр объекта таблицы, который будет вложен внутри внешнего стола, который разобьется внутри той же страницы.
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Добавьте externalTable в абзацы страницы.
// Добавить mytable в externalTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Добавить строку заголовка
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Создайте строки в таблице, а затем ячейки в строках.
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Заключение
В этом уроке мы узнали, как добавить повторяющийся столбец в документ PDF с помощью Aspose.PDF для .NET. Это пошаговое руководство можно использовать для создания таблиц с повторяющимися столбцами в собственных проектах C#.

### Часто задаваемые вопросы по добавлению повторяющегося столбца в PDF-документ

#### Вопрос: Можно ли настроить количество повторяющихся столбцов во вложенной таблице?

 О: Да, вы можете настроить количество повторяющихся столбцов во вложенной таблице. В приведенном примере мы установили`mytable.RepeatingColumnsCount = 5;`, что означает, что будет 5 повторяющихся столбцов. Вы можете изменить это значение на любое желаемое число.

#### Вопрос: Можно ли динамически добавлять дополнительные строки во вложенную таблицу?

О: Да, вы можете динамически добавлять дополнительные строки во вложенную таблицу так же, как показано в руководстве. Вы можете использовать циклы или любую другую логику для добавления строк на основе ваших данных.

#### Вопрос: Могу ли я применять стили и форматирование к таблице и ее ячейкам?

О: Да, вы можете применять стили и форматирование к таблице и ее ячейкам с помощью Aspose.PDF для .NET. Библиотека предоставляет различные свойства и методы для настройки внешнего вида таблицы и ее содержимого.

#### Вопрос: Совместим ли Aspose.PDF для .NET с .NET Core?

О: Да, Aspose.PDF для .NET совместим с .NET Core. Вы можете использовать его как в приложениях .NET Framework, так и в приложениях .NET Core.

#### Вопрос: Могу ли я использовать этот подход для добавления повторяющихся столбцов в существующий PDF-документ?

О: Да, вы можете использовать этот подход для добавления повторяющихся столбцов в существующий PDF-документ. Просто загрузите существующий документ с помощью Aspose.PDF для .NET и выполните те же действия, чтобы создать и добавить повторяющийся столбец.