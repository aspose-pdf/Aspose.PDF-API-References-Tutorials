---
title: Определить разрыв таблицы в PDF-файле
linktitle: Определить разрыв таблицы в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как определить разрывы таблиц в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-tables/determine-table-break/
---
В этом уроке мы научимся определять разрывы таблиц в PDF-файле с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого руководства вы узнаете, как определить, выходит ли таблица за пределы полей страницы. Давайте начнем!

## Шаг 1. Настройка среды
Сначала убедитесь, что вы настроили свою среду разработки C# с помощью Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2. Создание PDF-документа
 На этом этапе мы создаем новый`Document` объект, представляющий PDF-документ.

```csharp
pdf-Document = new Document();
```

Этот документ будет использоваться для добавления разделов и таблиц.

## Шаг 3: Добавление раздела и таблицы
Теперь мы добавим раздел в наш PDF-документ и создадим таблицу внутри этого раздела.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Мы также указываем для таблицы верхний предел в 300 пунктов. Вы можете настроить это значение в соответствии с вашими потребностями.

## Шаг 4: Настройка таблицы
На этом этапе мы настраиваем свойства таблицы, такие как ширина столбцов и границы.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Здесь мы определяем ширину столбцов таблицы и границ ячеек. Вы можете настроить эти значения в соответствии со своими предпочтениями.

## Шаг 5. Добавьте в таблицу строки и ячейки.
Теперь мы будем создавать строки и ячейки в таблице с помощью цикла.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Здесь мы создаем в таблице 17 строк и добавляем в каждую строку по три ячейки. Вы можете отрегулировать пряжку в соответствии с вашими потребностями.

## Шаг 6: Определение разрывов таблицы
Теперь мы определим, превышает ли таблица поля страницы, сравнивая высоту страницы с общей высотой объектов в таблице.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Рассчитываем высоту страницы и общую высоту объектов с учетом полей. Если разница составляет 10 или меньше, таблица выходит за пределы полей страницы.

## Шаг 7. Сохранение PDF-документа
Наконец, мы сохраняем PDF-документ с результатами.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Обязательно укажите правильный каталог документов. Полученный PDF-файл будет сохранен с указанными разрывами таблицы.

### Пример исходного кода для определения разрыва таблицы с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создание экземпляра класса объекта PDF
Document pdf = new Document();
// Добавить раздел в коллекцию разделов PDF-документа
Aspose.Pdf.Page page = pdf.Pages.Add();
// Создать экземпляр табличного объекта
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Добавьте таблицу в коллекцию абзацев нужного раздела
page.Paragraphs.Add(table1);
// Задается шириной столбца таблицы
table1.ColumnWidths = "100 100 100";
// Установите границу ячейки по умолчанию, используя объект BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Установите границу таблицы, используя другой настраиваемый объект BorderInfo.
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Создайте объект MarginInfo и установите его левое, нижнее, правое и верхнее поля.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Установите заполнение ячеек по умолчанию для объекта MarginInfo.
table1.DefaultCellPadding = margin;
// Если увеличить счетчик до 17, таблица сломается.
// Потому что это больше не может быть размещено на этой странице.
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Создайте строки в таблице, а затем ячейки в строках.
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Получить информацию о высоте страницы
float PageHeight = (float)pdf.PageInfo.Height;
// Получите информацию об общей высоте верхнего и нижнего полей страницы,
// Поле верха таблицы и высота таблицы.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Отображать высоту страницы, высоту таблицы, верхнее поле таблицы и верх страницы.
// И информация о нижнем поле
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Проверьте, вычитаем ли мы сумму верхнего поля страницы + нижнего поля страницы.
// + Поле верхней части таблицы и высота таблицы от высоты страницы и меньше
// Более 10 (среднее значение строки может быть больше 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Если значение меньше 10, отобразить сообщение.
	//Это показывает, что невозможно разместить еще одну строку, и если мы добавим новую
	// Строка, стол сломается. Это зависит от значения высоты строки.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Сохраните PDF-документ
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Заключение
В этом уроке мы узнали, как определять разрывы таблиц в PDF-документе с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство, чтобы проверить, выходит ли таблица за пределы полей страницы в ваших собственных проектах C#.

### Часто задаваемые вопросы по определению разрыва таблицы в PDF-файле

#### Вопрос: Какова цель определения разрывов таблиц в PDF-документе?

О: Целью определения разрывов таблицы в PDF-документе является проверка того, выходит ли таблица за пределы полей страницы. Это гарантирует, что содержимое таблицы правильно отображается на доступном пространстве страницы. Обнаружив разрывы таблиц, вы можете справиться с переполнением содержимого и соответствующим образом настроить макет таблицы.

#### Вопрос: Как настроить верхнее поле таблицы?

 О: В предоставленном исходном коде C# вы можете настроить верхнее поле таблицы, изменив значение`table1.Margin.Top`свойство. Увеличьте или уменьшите значение по мере необходимости, чтобы установить желаемое верхнее поле таблицы.

#### Вопрос: Могу ли я настроить внешний вид таблицы, например цвета ячеек и размер шрифта?

О: Да, вы можете настроить внешний вид таблицы и ее ячеек, используя различные свойства и методы, предоставляемые Aspose.PDF для .NET. Например, вы можете изменить цвета фона ячеек, размер шрифта, семейство шрифтов, выравнивание текста и многое другое. Обратитесь к официальной документации для получения дополнительной информации о том, как настроить внешний вид таблицы.

#### Вопрос: Что произойдет, если таблица выйдет за пределы полей страницы?

О: Если таблица выходит за пределы полей страницы, это может привести к усечению или перекрытию содержимого, что сделает PDF-документ менее читабельным и организованным. Обнаруживая разрывы таблицы и обрабатывая переполнение, вы можете гарантировать, что содержимое будет правильно отображаться в доступной области страницы.

#### Вопрос: Могу ли я определить разрывы таблиц для нескольких таблиц в одном PDF-документе?

О: Да, вы можете определить разрывы таблиц для нескольких таблиц в одном PDF-документе. Просто повторите шаги для каждой таблицы, которую вы хотите проанализировать, и при необходимости настройте макет таблицы, чтобы предотвратить переполнение содержимого.