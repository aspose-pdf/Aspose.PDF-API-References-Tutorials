---
title: Отобразить таблицу в PDF-документе
linktitle: Отобразить таблицу в PDF-документе
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как отобразить таблицу в PDF-документе с помощью Aspose.PDF для .NET.
type: docs
weight: 170
url: /ru/net/programming-with-tables/render-table/
---
В этом уроке мы шаг за шагом покажем вам, как отобразить таблицу в документе PDF с помощью Aspose.PDF для .NET. Мы объясним предоставленный исходный код C# и покажем, как его реализовать.

## Шаг 1: Создание документа
Сначала создадим новый PDF-документ:

```csharp
// Путь к каталогу документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создать новый документ
Document doc = new Document();
```

## Шаг 2: Настройка полей и ориентации страницы
Далее настроим поля страницы и установим альбомную ориентацию:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Шаг 3: Создание таблицы и столбцов
Теперь давайте создадим таблицу и зададим ширину столбцов:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Шаг 4: Добавьте строки и ячейки в таблицу.
Далее мы добавим строки и ячейки в таблицу с помощью цикла:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Шаг 5: Добавление таблицы на страницу
Теперь добавим таблицу на страницу документа:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Шаг 6: Отображение таблицы на новой странице
Далее мы создадим новую таблицу и установим свойство «IsInNewPage» в значение «true», чтобы отобразить таблицу на новой странице:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Шаг 7: Сохраните PDF-файл
Наконец, сохраняем PDF-документ:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Пример исходного кода для Render Table с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Добавлена страница.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Я хочу, чтобы таблица 1 была перенесена на следующую страницу, пожалуйста...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Заключение
Поздравляем! Теперь вы узнали, как отобразить таблицу в документе PDF с помощью Aspose.PDF для .NET. Это пошаговое руководство показало вам, как создать документ, настроить поля и ориентацию страницы, добавить таблицу и отобразить таблицу на новой странице. Теперь вы можете применить эти знания в своих собственных проектах.

### Часто задаваемые вопросы по отображению таблицы в PDF-документе

#### В: Как изменить внешний вид таблицы, например, изменить цвета ячеек или добавить границы?

A: Чтобы изменить внешний вид таблицы, вы можете задать различные ее свойства.`Aspose.Pdf.Table` и его ячейки. Например, вы можете установить`BackgroundColor` свойство ячеек менять цвет фона. Вы также можете задать`Border` свойство таблицы или отдельных ячеек для добавления границ. Кроме того, вы можете настроить шрифт, цвет текста и выравнивание содержимого таблицы, изменив`TextState` принадлежащий`TextFragment` объекты, добавленные в ячейки.

#### В: Могу ли я добавлять верхние и нижние колонтитулы в таблицу?

A: Да, вы можете добавлять заголовки или нижние колонтитулы в таблицу, создавая дополнительные строки в начале или конце таблицы и устанавливая соответствующее содержимое в ячейках. Вы можете настраивать заголовки или нижние колонтитулы независимо от остального содержимого таблицы, добавляя различные стили или содержимое к этим конкретным строкам.

#### В: Как я могу контролировать положение таблицы на странице?

 A: Чтобы контролировать положение таблицы на странице, вы можете настроить`MarginInfo` принадлежащий`PageInfo` объект.`MarginInfo`позволяет вам задать левое, правое, верхнее и нижнее поля страницы, что влияет на доступное место для таблицы. Вы также можете использовать`PositioningType` собственность`Aspose.Pdf.Table` для управления его горизонтальным и вертикальным выравниванием в области содержимого страницы.

#### В: Могу ли я экспортировать таблицу в другие форматы файлов, например Excel или CSV?

A: Aspose.PDF для .NET в первую очередь предназначен для работы с PDF-документами. Хотя он может экспортировать PDF-документ как изображение или XPS, он не поддерживает экспорт таблиц в такие форматы, как Excel или CSV. Для экспорта табличных данных в другие форматы файлов вам может потребоваться использовать дополнительные библиотеки или методы для преобразования содержимого PDF в нужный формат.

#### В: Как добавить гиперссылки в ячейки таблицы?

 A: Чтобы добавить гиперссылки в ячейки таблицы, вы можете использовать`Aspose.Pdf.WebHyperlink` класс для создания гиперссылки и последующего добавления ее в качестве якоря к`TextFragment`внутри ячейки. Это позволяет связать URL-адрес или ссылку с определенным текстом или содержимым внутри ячейки, создавая кликабельные гиперссылки.