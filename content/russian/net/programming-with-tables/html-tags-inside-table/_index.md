---
title: HTML-теги внутри таблицы в PDF-файле
linktitle: HTML-теги внутри таблицы в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как использовать HTML-теги внутри таблицы в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-tables/html-tags-inside-table/
---
В этом уроке мы научимся использовать HTML-теги внутри таблицы в PDF-документе с помощью Aspose.PDF для .NET. Мы шаг за шагом объясним исходный код на C#. В конце этого урока вы будете знать, как вставить HTML-контент в таблицу в PDF-документе. Давайте начнем!

## Шаг 1: Настройка среды
Убедитесь, что вы настроили среду разработки C# с Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2: Создание табличных данных
Мы создаем DataTable, содержащий столбец "data" типа String. Затем мы добавляем строки в этот DataTable, используя HTML-контент.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Шаг 3: Создание документа и таблицы
Мы создаем новый PDF-документ и добавляем страницу в этот документ. Далее мы инициализируем экземпляр класса Table и задаем свойства таблицы.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Шаг 4: Импорт данных в таблицу
Импортируем данные из DataTable в таблицу с помощью метода «ImportDataTable». Указываем параметры метода, чтобы указать, какой диапазон строк и столбцов DataTable следует импортировать.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Шаг 5: Добавление таблицы в документ
Добавляем таблицу на страницу документа.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Этап 6: Сохранение документа
Сохраняем PDF-документ с таблицей, содержащей HTML-контент.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Пример исходного кода для HTML-тегов внутри таблицы с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Инициализирует новый экземпляр таблицы.
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Установить ширину столбцов таблицы
tableProvider.ColumnWidths = "400 50 ";
// Установить цвет границы таблицы как LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Установить границу для ячеек таблицы
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Заключение
В этом уроке мы узнали, как использовать HTML-теги внутри таблицы в документе PDF с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство для вставки HTML-контента в ячейки таблицы в документе PDF с помощью C#.

### Часто задаваемые вопросы по тегам HTML внутри таблицы в файле PDF

#### В: Могу ли я использовать другие HTML-теги и атрибуты внутри ячеек таблицы?

 A: Да, вы можете использовать различные HTML-теги и атрибуты внутри ячеек таблицы, например`<b>`, `<i>`, `<a>`и многое другое. Aspose.PDF для .NET поддерживает широкий спектр элементов и стилей HTML, которые можно использовать для форматирования содержимого ячеек таблицы.

#### В: Могу ли я применять стили CSS к HTML-содержимому внутри ячеек таблицы?

A: Да, вы можете применять стили CSS к HTML-содержимому внутри ячеек таблицы. Aspose.PDF для .NET обеспечивает поддержку базовых стилей CSS, которые можно применять к HTML-элементам.

#### В: Можно ли добавлять изображения вместе с HTML-контентом внутри ячеек таблицы?

 A: Да, вы можете добавлять изображения вместе с содержимым HTML внутри ячеек таблицы. Вы можете использовать HTML`<img>` теги для включения изображений из различных источников, таких как локальные файлы или URL-адреса.

#### В: Как указать разную ширину столбцов в таблице?

 A: Вы можете указать различную ширину столбцов для таблицы, используя`ColumnWidths` свойство таблицы. Свойство принимает строку, содержащую разделенные пробелами значения, где каждое значение представляет ширину столбца в точках.

#### В: Можно ли использовать вложенные таблицы внутри ячейки с HTML-содержимым?

A: Да, вы можете использовать вложенные таблицы внутри ячейки с содержимым HTML. Вы можете создать отдельные экземпляры таблиц и добавить их как часть содержимого HTML внутри ячейки, чтобы достичь эффекта вложенности.