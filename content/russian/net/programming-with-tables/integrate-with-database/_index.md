---
title: Интеграция с базой данных в PDF-файле
linktitle: Интеграция с базой данных в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Внедрите данные из базы данных в PDF-файл с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-tables/integrate-with-database/
---
В этом уроке мы научимся встраивать данные из базы данных в PDF-файл с помощью Aspose.PDF для .NET. Мы шаг за шагом объясним исходный код на C#. В конце этого урока вы будете знать, как импортировать табличные данные из базы данных в PDF-документ. Начнем!

## Шаг 1: Настройка среды
Убедитесь, что вы настроили среду разработки C# с Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2: Создание DataTable
Мы создаем экземпляр DataTable для представления данных, которые мы хотим внедрить в документ PDF. В этом примере мы создаем DataTable с тремя столбцами: Employee_ID, Employee_Name и Gender. Мы также добавляем две строки в DataTable с фиктивными данными.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Шаг 3: Создание PDF-документа и таблицы
Мы создаем экземпляр Document и добавляем страницу в этот документ. Далее мы создаем экземпляр Table для представления нашей таблицы в документе PDF. Мы определяем ширину столбцов таблицы и стили границ.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Шаг 4: Импорт данных из DataTable в таблицу
Мы используем метод ImportDataTable для импорта данных из DataTable в таблицу PDF-документа.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Шаг 5: Добавление таблицы в документ
Добавляем таблицу в коллекцию абзацев страницы документа.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Шаг 6: Сохраните документ.
Сохраняем PDF-документ с данными из встроенной базы данных.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Поздравляем! Теперь вы знаете, как встроить данные базы данных в PDF-документ с помощью Aspose.PDF для .NET.

### Пример исходного кода для интеграции с базой данных с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Добавить 2 строки в объект DataTable программным способом
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Создать экземпляр документа
Document doc = new Document();
doc.Pages.Add();
// Инициализирует новый экземпляр таблицы.
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Установить ширину столбцов таблицы
table.ColumnWidths = "40 100 100 100";
// Установить цвет границы таблицы как LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Установить границу для ячеек таблицы
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Добавить табличный объект на первую страницу входного документа
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Сохранить обновленный документ, содержащий табличный объект
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Заключение
В этом уроке мы узнали, как встроить данные из базы данных в документ PDF с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство для импорта данных из вашей собственной базы данных и отображения их в документах PDF. Изучите документацию Aspose.PDF подробнее, чтобы узнать о других функциях и возможностях, предлагаемых этой мощной библиотекой.

### Часто задаваемые вопросы по интеграции с базой данных в PDF-файле

#### В: Могу ли я использовать Aspose.PDF для .NET с различными типами баз данных, такими как MySQL, SQL Server или Oracle?

A: Да, вы можете использовать Aspose.PDF для .NET с различными типами баз данных, такими как MySQL, SQL Server, Oracle и другими. Aspose.PDF для .NET предоставляет функциональные возможности для чтения данных из различных источников данных, включая базы данных, XML-файлы и многое другое. Вы можете извлекать данные из нужного вам типа базы данных и заполнять ими DataTable или любую другую структуру данных, совместимую с Aspose.PDF для .NET.

#### В: Как настроить внешний вид таблицы в PDF-документе?

A: Вы можете настроить внешний вид таблицы в документе PDF, используя различные свойства, предоставляемые библиотекой Aspose.PDF for .NET. Например, вы можете задать различные стили границ, цвета фона, стили шрифтов и выравнивание для таблицы и ее ячеек. Более подробную информацию о настройке внешнего вида таблицы см. в документации Aspose.PDF for .NET.

#### В: Можно ли добавлять гиперссылки или интерактивные элементы к данным, импортированным из базы данных?

A: Да, вы можете добавлять гиперссылки или другие интерактивные элементы к данным, импортированным из базы данных. Aspose.PDF для .NET поддерживает добавление гиперссылок, закладок и других интерактивных элементов в документ PDF. Вы можете манипулировать содержимым в DataTable перед его импортом в таблицу и включать гиперссылки или другие интерактивные функции.

#### В: Могу ли я разбить таблицу на страницы, если она превышает определенное количество строк?

 A: Да, вы можете разбить таблицу на страницы, если она превышает определенное количество строк. Для этого вы можете использовать`IsInNewPage`свойство объекта Row, чтобы указать, что новая страница должна начинаться после определенной строки. Вы можете рассчитать количество строк для отображения на странице и задать`IsInNewPage` имущество соответственно.

#### В: Как экспортировать PDF-документ со встроенными данными базы данных в другие форматы файлов, такие как DOCX или XLSX?

A: Aspose.PDF for .NET позволяет вам преобразовывать PDF-документы в различные другие форматы файлов, включая DOCX (Microsoft Word) и XLSX (Microsoft Excel). Вы можете использовать библиотеку Aspose.PDF for .NET в сочетании с другими библиотеками Aspose, такими как Aspose.Words и Aspose.Cells, чтобы добиться этого. Сначала сохраните PDF-документ со встроенными данными базы данных, а затем используйте соответствующую библиотеку Aspose, чтобы преобразовать его в нужный вам формат файла.