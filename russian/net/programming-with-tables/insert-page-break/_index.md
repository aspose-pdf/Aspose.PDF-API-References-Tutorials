---
title: Вставить разрыв страницы
linktitle: Вставить разрыв страницы
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как вставить разрыв страницы в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-tables/insert-page-break/
---

В этом уроке мы узнаем, как вставить разрыв страницы в документ PDF, используя Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого урока вы узнаете, как добавить разрыв страницы после определенного количества строк в таблице PDF-документа. Давайте начнем!

## Шаг 1. Настройка среды
Убедитесь, что вы настроили среду разработки C# с Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2: Создание документа и таблицы
Мы создаем новый экземпляр Document и добавляем страницу в этот документ. Затем мы создаем экземпляр таблицы для представления нашей таблицы в документе PDF. Мы также определяем стили границ для таблицы.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Шаг 3: Добавьте строки в таблицу
Мы используем цикл, чтобы добавить 200 строк в массив. Для каждой строки мы создаем экземпляр Row и добавляем две ячейки с текстовым содержимым.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Когда добавляется 10 строк, мы вставляем новый разрыв страницы
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Шаг 4: Добавление таблицы в документ
Мы добавляем таблицу в коллекцию абзацев страницы документа.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Шаг 5: Сохраните документ
Мы сохраняем документ PDF со вставленным разрывом страницы.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Пример исходного кода для вставки разрыва страницы с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать экземпляр документа
Document doc = new Document();
// Добавить страницу в коллекцию страниц файла PDF
doc.Pages.Add();
// Создать экземпляр таблицы
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Установить стиль границы для таблицы
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Установить стиль границы по умолчанию для таблицы с красным цветом границы
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Укажите ширину столбцов таблицы
tab.ColumnWidths = "100 100";
// Создайте цикл, чтобы добавить 200 строк для таблицы
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Когда добавлено 10 строк, визуализировать новую строку на новой странице
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Добавить таблицу в коллекцию абзацев файла PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Сохраните PDF-документ
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Заключение
В этом руководстве мы узнали, как вставить разрыв страницы в документ PDF с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство, чтобы добавить разрыв страницы после определенного количества строк в таблице в документе PDF с помощью C#.