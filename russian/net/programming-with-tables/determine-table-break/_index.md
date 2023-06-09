---
title: Определить перерыв в таблице
linktitle: Определить перерыв в таблице
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как определить разрывы таблиц в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-tables/determine-table-break/
---

В этом руководстве мы узнаем, как определить разрывы таблиц в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого руководства вы узнаете, как определить, выходит ли таблица за пределы полей страницы. Давайте начнем!

## Шаг 1. Настройка среды
Во-первых, убедитесь, что вы настроили среду разработки C# с Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2: Создание PDF-документа
 На этом этапе мы создаем новый`Document` объект для представления PDF-документа.

```csharp
pdf-Document = new Document();
```

Этот документ будет использоваться для добавления разделов и таблиц.

## Шаг 3: Добавление раздела и таблицы
Теперь мы добавим раздел в наш документ PDF и создадим таблицу внутри этого раздела.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Мы также указываем верхнее поле в 300 пунктов для таблицы. Вы можете настроить это значение в соответствии с вашими потребностями.

## Шаг 4: Настройка стола
На этом этапе мы настраиваем свойства таблицы, такие как ширина столбцов и границы.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Здесь мы определяем ширину столбцов таблицы и границы ячеек. Вы можете настроить эти значения в соответствии со своими предпочтениями.

## Шаг 5: Добавьте строки и ячейки в таблицу
Теперь мы создадим строки и ячейки в таблице с помощью цикла.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Здесь мы создаем 17 строк в таблице и добавляем по три ячейки в каждую строку. Вы можете отрегулировать пряжку в соответствии с вашими потребностями.

## Шаг 6: Определение разрывов таблицы
Теперь мы определим, выходит ли таблица за пределы полей страницы, сравнив высоту страницы с общей высотой объектов в таблице.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Рассчитываем высоту страницы и общую высоту объектов с учетом полей. Если разница составляет 10 или меньше, таблица выходит за пределы полей страницы.

## Шаг 7: Сохранение PDF-документа
Наконец, мы сохраняем PDF-документ с результатами.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Обязательно укажите правильный каталог документов. Полученный файл PDF будет сохранен с определенными разрывами таблицы.

### Пример исходного кода для определения разрыва таблицы с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создание объекта класса PDF
Document pdf = new Document();
// Добавить раздел в коллекцию разделов документа PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Создать экземпляр табличного объекта
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Добавьте таблицу в коллекцию абзацев нужного раздела
page.Paragraphs.Add(table1);
// Задайте ширину столбцов таблицы
table1.ColumnWidths = "100 100 100";
// Установите границу ячейки по умолчанию, используя объект BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Установите границу таблицы, используя другой настраиваемый объект BorderInfo
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Создайте объект MarginInfo и установите его левое, нижнее, правое и верхнее поля.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Установите заполнение ячейки по умолчанию для объекта MarginInfo
table1.DefaultCellPadding = margin;
// Если увеличить счетчик до 17, стол сломается.
// Потому что это больше не может быть размещено на этой странице
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Создайте строки в таблице, а затем ячейки в строках
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Получить информацию о высоте страницы
float PageHeight = (float)pdf.PageInfo.Height;
// Получите информацию об общей высоте верхнего и нижнего поля страницы,
// Верхнее поле таблицы и высота таблицы.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Отображение высоты страницы, высоты таблицы, поля верхней части таблицы и верхней части страницы
// Информация о нижнем поле
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Проверьте, вычитаем ли мы сумму верхнего поля страницы + нижнего поля страницы
// + Поле таблицы и высота таблицы от высоты страницы и меньше
// Больше 10 (средний ряд может быть больше 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	//Если значение меньше 10, отобразите сообщение.
	// Что показывает, что другую строку нельзя разместить, и если мы добавим новую
	// Ряд, стол сломается. Это зависит от значения высоты строки.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Сохраните pdf-документ
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Заключение
В этом руководстве мы узнали, как определить разрывы таблиц в документе PDF с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство, чтобы проверить, выходит ли таблица за пределы полей страницы в ваших собственных проектах C#.