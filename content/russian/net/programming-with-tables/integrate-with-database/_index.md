---
title: Интеграция с базой данных в PDF-файле
linktitle: Интеграция с базой данных в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Встраивайте данные из базы данных в файл PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-tables/integrate-with-database/
---
В этом уроке мы научимся встраивать данные из базы данных в файл PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого руководства вы узнаете, как импортировать данные таблицы из базы данных в документ PDF. Давайте начнем!

## Шаг 1. Настройка среды
Убедитесь, что вы настроили свою среду разработки C# с помощью Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2. Создание таблицы данных
Мы создаем экземпляр DataTable для представления данных, которые мы хотим встроить в документ PDF. В этом примере мы создаем DataTable с тремя столбцами: «Идентификатор_сотрудника», «Имя_сотрудника» и «Пол». Мы также добавляем две строки в DataTable с фиктивными данными.

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

## Шаг 3. Создание PDF-документа и таблицы
Мы создаем экземпляр Document и добавляем страницу в этот документ. Затем мы создаем экземпляр Table для представления нашей таблицы в PDF-документе. Мы определяем ширину столбцов таблицы и стили границ.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Шаг 4. Импорт данных из DataTable в таблицу.
Мы используем метод ImportDataTable для импорта данных из DataTable в таблицу PDF-документа.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Шаг 5: Добавление таблицы в документ
Мы добавляем таблицу в коллекцию абзацев страницы документа.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Шаг 6: Сохраните документ
Сохраняем PDF-документ с данными из встроенной базы данных.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Поздравляем! Теперь вы знаете, как встроить данные базы данных в документ PDF с помощью Aspose.PDF для .NET.

### Пример исходного кода для интеграции с базой данных с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Добавьте 2 строки в объект DataTable программно
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
// Инициализирует новый экземпляр таблицы
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Установить ширину столбцов таблицы
table.ColumnWidths = "40 100 100 100";
// Установите цвет границы таблицы как LightGray.
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Установить границу ячеек таблицы
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Добавить объект таблицы на первую страницу входного документа
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Сохранить обновленный документ, содержащий объект таблицы.
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Заключение
В этом уроке мы узнали, как встраивать данные из базы данных в PDF-документ с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство для импорта данных из вашей собственной базы данных и отображения их в документах PDF. Изучите документацию Aspose.PDF, чтобы узнать о других функциях и возможностях, предлагаемых этой мощной библиотекой.

### Часто задаваемые вопросы по интеграции с базой данных в PDF-файле

#### Вопрос: Могу ли я использовать Aspose.PDF для .NET с различными типами баз данных, такими как MySQL, SQL Server или Oracle?

О: Да, вы можете использовать Aspose.PDF для .NET с различными типами баз данных, такими как MySQL, SQL Server, Oracle и другими. Aspose.PDF для .NET предоставляет функциональные возможности для чтения данных из различных источников данных, включая базы данных, файлы XML и многое другое. Вы можете получить данные из базы данных желаемого типа и заполнить их в DataTable или любую другую структуру данных, совместимую с Aspose.PDF для .NET.

#### Вопрос: Как настроить внешний вид таблицы в PDF-документе?

О: Вы можете настроить внешний вид таблицы в PDF-документе, используя различные свойства, предоставляемые библиотекой Aspose.PDF for .NET. Например, вы можете установить различные стили границ, цвета фона, стили шрифта и выравнивание для таблицы и ее ячеек. Обратитесь к документации Aspose.PDF для .NET для получения более подробной информации о настройке внешнего вида таблицы.

#### Вопрос: Можно ли добавлять гиперссылки или интерактивные элементы к данным, импортированным из базы данных?

О: Да, вы можете добавлять гиперссылки или другие интерактивные элементы к данным, импортированным из базы данных. Aspose.PDF для .NET поддерживает добавление гиперссылок, закладок и других интерактивных элементов в документ PDF. Вы можете манипулировать содержимым DataTable перед его импортом в таблицу и включать гиперссылки или другие интерактивные функции.

#### Вопрос: Могу ли я разбить таблицу на страницы, если она превышает определенное количество строк?

 О: Да, вы можете разбить таблицу на страницы, если она превышает определенное количество строк. Чтобы добиться этого, вы можете использовать`IsInNewPage`свойство объекта Row, указывающее, что новая страница должна начинаться после определенной строки. Вы можете рассчитать количество строк, отображаемых на странице, и установить`IsInNewPage` имущество соответственно.

#### Вопрос: Как экспортировать PDF-документ со встроенными данными базы данных в другие форматы файлов, например DOCX или XLSX?

О: Aspose.PDF для .NET позволяет конвертировать PDF-документы в различные другие форматы файлов, включая DOCX (Microsoft Word) и XLSX (Microsoft Excel). Для достижения этой цели вы можете использовать библиотеку Aspose.PDF for .NET в сочетании с другими библиотеками Aspose, такими как Aspose.Words и Aspose.Cells. Сначала сохраните документ PDF со встроенными данными базы данных, а затем используйте соответствующую библиотеку Aspose, чтобы преобразовать его в желаемый формат файла.