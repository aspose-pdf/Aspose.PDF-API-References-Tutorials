---
title: Вставить разрыв страницы в PDF-файл
linktitle: Вставить разрыв страницы в PDF-файл
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как вставить разрыв страницы в файл PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-tables/insert-page-break/
---
В этом уроке мы научимся вставлять разрыв страницы в PDF-файл с помощью Aspose.PDF для .NET. Мы объясним исходный код на C# шаг за шагом. В конце этого урока вы узнаете, как добавить разрыв страницы после определенного количества строк в таблице PDF-документа. Давайте начнем!

## Шаг 1. Настройка среды
Убедитесь, что вы настроили свою среду разработки C# с помощью Aspose.PDF для .NET. Добавьте ссылку на библиотеку и импортируйте необходимые пространства имен.

## Шаг 2. Создание документа и таблицы
Мы создаем новый экземпляр документа и добавляем страницу в этот документ. Затем мы создаем экземпляр Table для представления нашей таблицы в PDF-документе. Мы также определяем стили границ для таблицы.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Шаг 3. Добавьте строки в таблицу
Мы используем цикл для добавления 200 строк в массив. Для каждой строки мы создаем экземпляр Row и добавляем две ячейки с текстовым содержимым.

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
    
     // При добавлении 10 строк мы вставляем новый разрыв страницы.
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Шаг 4. Добавление таблицы в документ
Мы добавляем таблицу в коллекцию абзацев страницы документа.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Шаг 5: Сохраните документ
Сохраняем PDF-документ со вставленным разрывом страницы.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Пример исходного кода для вставки разрыва страницы с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать экземпляр экземпляра документа
Document doc = new Document();
// Добавить страницу в коллекцию страниц PDF-файла
doc.Pages.Add();
// Создать экземпляр таблицы
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Установить стиль границы для таблицы
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Установите стиль границы по умолчанию для таблицы с красным цветом границы.
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Укажите ширину столбцов таблицы
tab.ColumnWidths = "100 100";
// Создайте цикл для добавления 200 строк в таблицу.
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Когда добавлено 10 строк, отобразите новую строку на новой странице.
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Добавить таблицу в коллекцию абзацев PDF-файла
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Сохраните PDF-документ
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Заключение
В этом уроке мы узнали, как вставить разрыв страницы в PDF-документ с помощью Aspose.PDF для .NET. Вы можете использовать это пошаговое руководство, чтобы добавить разрыв страницы после определенного количества строк в таблице в документе PDF с помощью C#.

### Часто задаваемые вопросы по вставке разрыва страницы в файл PDF

#### Вопрос: Как изменить размер новых страниц, созданных после разрыва страницы?

 О: Чтобы изменить размер новых страниц, созданных после разрыва страницы, вы можете установить`PageSize` собственность`Page` объект. Например, вы можете использовать следующий код, чтобы установить размер страницы A4:

```csharp
// Установите размер страницы А4.
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Вопрос: Могу ли я контролировать поля для новых страниц после разрыва страницы?

 О: Да, вы можете контролировать поля для новых страниц после разрыва страницы. Использовать`Margin` собственность`Page` объект для установки полей страницы. Например, чтобы установить все поля в 10 пунктов, вы можете использовать следующий код:

```csharp
// Установите все поля на 10 пунктов
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Вопрос: Можно ли добавлять верхние и нижние колонтитулы на новые страницы после разрыва страницы?

 О: Да, вы можете добавлять верхние и нижние колонтитулы на новые страницы после разрыва страницы. Использовать`Page.Header` и`Page.Footer` свойства для добавления содержимого в разделы верхнего и нижнего колонтитула страницы. Например:

```csharp
// Добавить заголовок на новые страницы
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Добавляйте нижний колонтитул на новые страницы
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Вопрос: Могу ли я вставлять разрывы страниц в определенных местах, кроме определенного количества строк?

 О: Да, вы можете вставлять разрывы страниц в определенных местах, кроме определенного количества строк. Вы можете установить`IsInNewPage` свойство строки для`true` чтобы заставить таблицу начать новую страницу после этой строки.

#### Вопрос: Как настроить поведение разрыва страницы в зависимости от высоты содержимого?

О: Вы можете использовать`IsBroken` свойство таблицы, позволяющее включить или отключить автоматическое разбиение строк по страницам. Если установлено значение`true`, он позволяет разбивать строки по страницам в зависимости от высоты содержимого.