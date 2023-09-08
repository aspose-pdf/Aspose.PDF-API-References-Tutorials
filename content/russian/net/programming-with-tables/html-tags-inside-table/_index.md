---
title: HTML-теги внутри таблицы в PDF-файле
linktitle: HTML-теги внутри таблицы в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как использовать теги HTML внутри таблицы в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-tables/html-tags-inside-table/
---
В этом уроке мы научимся использовать теги HTML внутри таблицы в PDF-документе с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого руководства вы узнаете, как вставить HTML-содержимое в таблицу PDF-документа. Давайте начнем!

## Шаг 1. Настройка среды
Убедитесь, что вы настроили свою среду разработки C# с помощью Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2. Создание данных таблицы
Мы создаем DataTable, содержащий столбец «данные» типа String. Затем мы добавляем строки в этот DataTable, используя HTML-контент.

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

## Шаг 3. Создание документа и таблицы
Создаем новый PDF-документ и добавляем в этот документ страницу. Далее мы инициализируем экземпляр класса Table и устанавливаем свойства таблицы.

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

## Шаг 4. Импорт данных в таблицу
Импортируем данные из DataTable в таблицу с помощью метода ImportDataTable. Мы указываем параметры метода, чтобы указать, какой диапазон строк и столбцов DataTable следует импортировать.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Шаг 5: Добавление таблицы в документ
Добавляем таблицу на страницу документа.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Этап 6: Сохранение документа
Сохраняем PDF-документ с таблицей, содержащей HTML-содержимое.

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
// Инициализирует новый экземпляр таблицы
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Установить ширину столбцов таблицы
tableProvider.ColumnWidths = "400 50 ";
// Установите цвет границы таблицы как LightGray.
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Установить границу ячеек таблицы
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
В этом уроке мы узнали, как использовать теги HTML внутри таблицы в документе PDF с помощью Aspose.PDF для .NET. Это пошаговое руководство можно использовать для вставки HTML-содержимого в ячейки таблицы PDF-документа с помощью C#.

### Часто задаваемые вопросы по HTML-тегам внутри таблицы в PDF-файле

#### Вопрос: Могу ли я использовать другие HTML-теги и атрибуты внутри ячеек таблицы?

 О: Да, внутри ячеек таблицы вы можете использовать различные HTML-теги и атрибуты, например`<b>`, `<i>`, `<a>`и многие другие. Aspose.PDF для .NET поддерживает широкий спектр элементов и стилей HTML, которые вы можете использовать для форматирования содержимого ячеек таблицы.

#### Вопрос: Могу ли я применять стили CSS к содержимому HTML внутри ячеек таблицы?

О: Да, вы можете применять стили CSS к содержимому HTML внутри ячеек таблицы. Aspose.PDF для .NET обеспечивает поддержку основных стилей CSS, которые можно применять к элементам HTML.

#### Вопрос: Можно ли добавлять изображения вместе с HTML-содержимым внутри ячеек таблицы?

 О: Да, вы можете добавлять изображения вместе с HTML-содержимым внутри ячеек таблицы. Вы можете использовать HTML`<img>` теги для включения изображений из различных источников, таких как локальные файлы или URL-адреса.

#### Вопрос: Как указать разную ширину столбцов таблицы?

 О: Вы можете указать разную ширину столбцов таблицы, используя`ColumnWidths` свойство таблицы. Свойство принимает строку, содержащую значения, разделенные пробелами, где каждое значение представляет ширину столбца в пунктах.

#### Вопрос: Могу ли я использовать вложенные таблицы внутри ячейки с содержимым HTML?

О: Да, вы можете использовать вложенные таблицы внутри ячейки с содержимым HTML. Вы можете создавать отдельные экземпляры таблиц и добавлять их как часть содержимого HTML внутри ячейки для достижения эффекта вложенности.