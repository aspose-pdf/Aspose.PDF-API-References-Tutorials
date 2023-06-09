---
title: Экспорт данных рабочего листа Excel в таблицу
linktitle: Экспорт данных рабочего листа Excel в таблицу
second_title: Aspose.PDF для справочника API .NET
description: Экспорт данных из листа Excel в таблицу PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-tables/export-excel-worksheet-data-to-table/
---

В этом руководстве мы узнаем, как экспортировать данные из листа Excel и создать таблицу в документе PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим исходный код шаг за шагом и подробно объясним каждый раздел. К концу этого руководства вы сможете создавать PDF-файлы с таблицами, содержащими данные из рабочих листов Excel. Давайте начнем!

## Требования
Прежде чем мы начнем, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования С#
- Visual Studio установлена на вашем компьютере
- В ваш проект добавлена библиотека Aspose.PDF для .NET

## Шаг 1: Настройка среды
Для начала создайте новый проект C# в Visual Studio. Добавьте ссылку на библиотеку Aspose.PDF для .NET, щелкнув правой кнопкой мыши свой проект в обозревателе решений, выбрав «Управление пакетами NuGet» и выполнив поиск «Aspose.PDF». Установите пакет, и вы готовы к работе.

## Шаг 2: Загрузка рабочего листа Excel
На первом этапе нашего кода мы определяем путь к каталогу, содержащему документ Excel. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором находится ваш файл Excel.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Здесь мы используем библиотеку Aspose.Cells для загрузки книги Excel. Обязательно замените «newBook1.xlsx» именем вашего файла Excel.

## Шаг 3: Доступ к рабочему листу
 Далее нам нужно получить доступ к первому рабочему листу в файле Excel. Делаем это с помощью`Worksheets` коллекция`Workbook` объект.

```csharp
// Доступ к первому рабочему листу в файле Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Если ваш файл Excel содержит несколько рабочих листов, вы можете изменить значение индекса`[0]` для доступа к другому рабочему листу.

## Шаг 4: Экспорт данных в DataTable
 Теперь мы экспортируем содержимое рабочего листа Excel в`DataTable` объект. Мы указываем диапазон ячеек для экспорта с помощью`ExportDataTable` метод.

```csharp
// Экспорт содержимого 7 строк и 2 столбцов, начиная с 1-й ячейки, в DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

В этом примере мы экспортируем все строки и столбцы, начиная с первой ячейки (0, 0) до последней ячейки на листе. Установите соответствующий диапазон в зависимости от ваших требований.

## Шаг 5: Создание PDF-документа
Теперь мы создадим новый PDF-документ, используя библиотеку Aspose.PDF.

```csharp
// Создание экземпляра документа
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Это создает пустой PDF-документ, в который мы можем добавить контент.

## Шаг 6: Добавление страницы и таблицы
Чтобы отобразить данные в формате таблицы, нам нужно добавить страницу и таблицу в документ PDF.

```csharp
// Создать страницу в экземпляре документа
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Создать объект таблицы
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Добавьте объект «Таблица» в коллекцию абзацев раздела.
sec1.Paragraphs.Add(tab1);
```

Здесь мы создаем новую страницу и объект таблицы. Затем мы добавляем таблицу в коллекцию абзацев страницы.

## Шаг 7: Настройка свойств таблицы
Перед импортом данных нам нужно установить некоторые свойства таблицы, такие как ширина столбцов и границы ячеек по умолчанию.

```csharp
// Установить ширину столбцов таблицы
tab1.ColumnWidths = "40 100 100";

// Установите границу ячейки таблицы по умолчанию с помощью объекта BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

В этом примере мы устанавливаем ширину столбцов на 40, 100 и 100 единиц. Настройте значения на основе ваших данных. Мы также устанавливаем границу ячейки по умолчанию для отображения границ со всех сторон каждой ячейки.

## Шаг 8: Импорт данных в таблицу
 Теперь мы будем импортировать данные из`DataTable` объект в таблицу с помощью`ImportDataTable` метод.

```csharp
// Импортируйте данные в объект Table из таблицы DataTable, созданной выше.
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Здесь мы указываем диапазон строк и столбцов для импорта. В этом примере мы импортируем все строки и столбцы из`dataTable` объект.

## Шаг 9: Форматирование таблицы
Чтобы улучшить внешний вид таблицы, мы можем применить форматирование к определенным ячейкам или строкам. На этом шаге мы отформатируем первую строку и чередующиеся строки таблицы.

```csharp
// Получить 1-ю строку из таблицы
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Отформатируйте первую строку
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Установите цвет фона ячеек в первой строке
     curCell.BackgroundColor = Color.Blue;// Установите лицо для ячеек в первой строке
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Установите цвет шрифта ячеек в первой строке
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Установите выравнивание текста для ячеек в первой строке
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Альтернативный формат строки
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Установите цвет фона ячеек в чередующихся строках
         curCell.BackgroundColor = Color.Gray;
        
         // Установите цвет текста ячеек в чередующихся строках
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Здесь мы перебираем ячейки в первой строке и устанавливаем их цвет фона, шрифт, цвет шрифта и выравнивание текста. Затем мы перебираем все ячейки в чередующихся строках и устанавливаем их фон и цвет текста.

## Шаг 10: Сохранение PDF-документа
Наконец, мы сохраняем документ PDF в указанное место.

```csharp
// Сохранить PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на желаемый путь к каталогу и имя файла для выходного PDF-файла.

### Пример исходного кода для экспорта данных листа Excel в таблицу с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Доступ к первому рабочему листу в файле Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Экспорт содержимого 7 строк и 2 столбцов, начиная с 1-й ячейки, в DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Создание экземпляра документа
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Создать страницу в экземпляре документа
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Создать объект таблицы
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Добавьте объект «Таблица» в коллекцию абзацев раздела.
sec1.Paragraphs.Add(tab1);

// Установить ширину столбцов таблицы. Нам нужно указать ColumnCount вручную.
// Поскольку текущий рабочий лист Excel имеет три столбца, поэтому мы указываем одно и то же количество
tab1.ColumnWidths = "40 100 100";

// Установите границу ячейки таблицы по умолчанию с помощью объекта BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Импортируйте данные в объект Table из таблицы DataTable, созданной выше.
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Получить 1-ю строку из таблицы
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Переберите все ячейки в 1-й строке и установите для них синий цвет фона.
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Установите фон всех ячеек в 1-й строке таблицы.
	curCell.BackgroundColor = Color.Blue;
	// Установите начертание шрифта для ячеек 1-й строки таблицы.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Установите цвет шрифта для всех ячеек в 1-й строке таблицы.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Установите выравнивание текста для ячеек 1-й строки как Центр.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Переберите все ячейки в 1-й строке и установите для них синий цвет фона.
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Установите цвет фона всех ячеек, кроме 1-й строки.
		curCell.BackgroundColor = Color.Gray;
		// Установите цвет текста для всех ячеек, кроме 1-й строки.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Сохраните PDF-файл
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Заключение
В этом руководстве мы узнали, как экспортировать данные из листа Excel в таблицу PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрели пошаговый процесс загрузки рабочего листа Excel, создания документа PDF, добавления таблицы, импорта данных и форматирования таблицы. Теперь вы можете программно создавать файлы PDF с таблицами, содержащими данные Excel.