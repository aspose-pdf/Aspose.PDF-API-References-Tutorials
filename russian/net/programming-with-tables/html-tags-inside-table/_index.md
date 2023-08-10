---
title: Теги HTML внутри таблицы в файле PDF
linktitle: Теги HTML внутри таблицы в файле PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать теги HTML внутри таблицы в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-tables/html-tags-inside-table/
---
В этом уроке мы узнаем, как использовать теги HTML внутри таблицы в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого руководства вы узнаете, как вставить содержимое HTML в таблицу в документе PDF. Давайте начнем!

## Шаг 1. Настройка среды
Убедитесь, что вы настроили среду разработки C# с Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2: Создание табличных данных
Мы создаем DataTable, содержащую столбец «данные» типа String. Затем мы добавляем строки в эту таблицу данных, используя содержимое HTML.

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
Мы создаем новый документ PDF и добавляем страницу в этот документ. Далее мы инициализируем экземпляр класса Table и устанавливаем свойства таблицы.

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
Мы импортируем данные из DataTable в таблицу с помощью метода «ImportDataTable». Мы указываем параметры метода, чтобы указать, какой диапазон строк и столбцов DataTable следует импортировать.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Шаг 5: Добавление таблицы в документ
Добавляем таблицу на страницу документа.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Этап 6: Сохранение документа
Мы сохраняем PDF-документ с таблицей, содержащей HTML-контент.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Пример исходного кода HTML-тегов внутри таблицы с использованием Aspose.PDF для .NET

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
// Инициализирует новый экземпляр таблицы
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Установить ширину столбцов таблицы
tableProvider.ColumnWidths = "400 50 ";
// Установите цвет границы таблицы как LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Установите границу для ячеек таблицы
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
В этом руководстве мы узнали, как использовать теги HTML внутри таблицы в документе PDF с помощью Aspose.PDF для .NET. Это пошаговое руководство можно использовать для вставки содержимого HTML в ячейки таблицы в документе PDF с помощью C#.

### Часто задаваемые вопросы по тегам HTML внутри таблицы в файле PDF

#### В: Могу ли я использовать другие HTML-теги и атрибуты внутри ячеек таблицы?

 О: Да, вы можете использовать различные HTML-теги и атрибуты внутри ячеек таблицы, например`<b>`, `<i>`, `<a>`и многое другое. Aspose.PDF для .NET поддерживает широкий спектр HTML-элементов и стилей, которые можно использовать для форматирования содержимого в ячейках таблицы.

#### Вопрос. Можно ли применить стили CSS к содержимому HTML внутри ячеек таблицы?

О: Да, вы можете применять стили CSS к содержимому HTML внутри ячеек таблицы. Aspose.PDF для .NET обеспечивает поддержку основных стилей CSS, которые можно применять к элементам HTML.

#### В: Можно ли добавлять изображения вместе с содержимым HTML внутри ячеек таблицы?

 О: Да, вы можете добавлять изображения вместе с содержимым HTML в ячейки таблицы. Вы можете использовать HTML`<img>` теги для включения изображений из различных источников, таких как локальные файлы или URL-адреса.

#### Q: Как указать разную ширину столбцов для таблицы?

 A: Вы можете указать различную ширину столбцов для таблицы, используя`ColumnWidths` свойство таблицы. Свойство принимает строку, содержащую значения, разделенные пробелами, где каждое значение представляет ширину столбца в пунктах.

#### Вопрос. Можно ли использовать вложенные таблицы внутри ячейки с содержимым HTML?

О: Да, вы можете использовать вложенные таблицы внутри ячейки с содержимым HTML. Вы можете создавать отдельные экземпляры таблиц и добавлять их как часть HTML-содержимого внутри ячейки для достижения эффекта вложенности.