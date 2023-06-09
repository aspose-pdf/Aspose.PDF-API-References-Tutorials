---
title: Интеграция с базой данных
linktitle: Интеграция с базой данных
second_title: Aspose.PDF для справочника API .NET
description: Встраивайте данные из базы данных в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-tables/integrate-with-database/
---

В этом руководстве мы узнаем, как встраивать данные из базы данных в документ PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого руководства вы узнаете, как импортировать табличные данные из базы данных в документ PDF. Давайте начнем!

## Шаг 1. Настройка среды
Убедитесь, что вы настроили среду разработки C# с Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2: Создание таблицы данных
Мы создаем экземпляр DataTable для представления данных, которые мы хотим встроить в документ PDF. В этом примере мы создаем DataTable с тремя столбцами: Employee_ID, Employee_Name и Gender. Мы также добавляем две строки в DataTable с фиктивными данными.

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
Мы создаем экземпляр Document и добавляем страницу в этот документ. Затем мы создаем экземпляр таблицы для представления нашей таблицы в документе PDF. Мы определяем ширину столбцов таблицы и стили границ.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Шаг 4: Импорт данных из DataTable в таблицу
Мы используем метод ImportDataTable для импорта данных из DataTable в таблицу в документе PDF.

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
// Добавить 2 строки в объект DataTable программно
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
// Установите цвет границы таблицы как LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Установите границу для ячеек таблицы
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
В этом руководстве мы узнали, как встраивать данные из базы данных в документ PDF с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство, чтобы импортировать данные из собственной базы данных и отображать их в документах PDF. Изучите документацию Aspose.PDF, чтобы узнать о других функциях и возможностях этой мощной библиотеки.