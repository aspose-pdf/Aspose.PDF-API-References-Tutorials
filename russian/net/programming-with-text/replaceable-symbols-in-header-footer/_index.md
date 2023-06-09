---
title: Заменяемые символы в нижнем колонтитуле верхнего колонтитула
linktitle: Заменяемые символы в нижнем колонтитуле верхнего колонтитула
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать заменяемые символы в верхнем и нижнем колонтитулах PDF-документа с помощью Aspose.PDF для .NET.
type: docs
weight: 320
url: /ru/net/programming-with-text/replaceable-symbols-in-header-footer/
---

В этом руководстве мы объясним, как использовать заменяемые символы в верхнем и нижнем колонтитулах PDF-документа с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим пошаговый процесс создания PDF-файла, настройки полей, добавления верхнего и нижнего колонтитула с заменяемыми символами и сохранения PDF-файла с использованием предоставленного исходного кода C#.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором вы хотите сохранить сгенерированный файл PDF. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к нужному каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте PDF-документ и страницу

Далее мы создаем новый PDF-документ и добавляем в него страницу с помощью`Document` класс и`Page` класс из библиотеки Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Шаг 3: Установите поля

 Мы устанавливаем поля для страницы с помощью`MarginInfo` сорт. Отрегулируйте значения маржи в соответствии с вашими требованиями.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Шаг 4: Добавьте заголовок с заменяемыми символами

 Мы создаем`HeaderFooter` объект для страницы и добавить`TextFragment` со сменными символами к нему.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Установите свойства текста, если хотите
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Добавьте больше TextFragments или настройте по мере необходимости
```

## Шаг 5: Добавьте нижний колонтитул с заменяемыми символами

 Точно так же мы создаем`HeaderFooter` объект для нижнего колонтитула страницы и добавить`TextFragment` объекты с заменяемыми на него символами.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Добавьте больше TextFragments или настройте по мере необходимости

hfFoot.Paragraphs.Add(tab2);
```

## Шаг 6: Сохраните PDF-документ

Наконец, мы сохраняем документ PDF в указанный выходной файл.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Пример исходного кода для заменяемых символов в нижнем колонтитуле верхнего колонтитула с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//Назначьте экземпляр marginInfo свойству Margin объекта sec1.PageInfo.
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Создайте экземпляр текстового абзаца, в котором будет храниться содержимое для отображения в качестве заголовка.
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Создайте объект HeaderFooter для раздела
HeaderFooter hfFoot = new HeaderFooter();
// Установите для объекта HeaderFooter нечетный и четный нижний колонтитул
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Добавить текстовый абзац, содержащий текущий номер страницы из общего количества страниц
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Создать экземпляр табличного объекта
Table tab2 = new Table();
// Добавьте таблицу в коллекцию абзацев нужного раздела
hfFoot.Paragraphs.Add(tab2);
// Задайте ширину столбцов таблицы
tab2.ColumnWidths = "165 172 165";
// Создайте строки в таблице, а затем ячейки в строках
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Установите вертикальное выравнивание текста по центру
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java представляет собой компиляцию каждого компонента Java, предлагаемого Aspose. Он компилируется на #$NL" + "ежедневной основе, чтобы гарантировать, что он содержит самые последние версии каждого наших компонентов Java. #$NL " + "Используя Aspose.Total для Java, разработчики могут создавать широкий спектр приложений. #$NL #$NL #$NP" + "Aspose.Total для Java представляет собой компиляцию всех компонентов Java предлагаемый Aspose. Он составляется #$NL" + "ежедневно, чтобы гарантировать, что он содержит самые последние версии каждого из наших компонентов Java. #$NL " + "Используя Aspose.Total для разработчиков Java, можно создать широкий диапазон приложений. #$NL #$NL #$NP" + "Aspose.Total для Java представляет собой компиляцию всех компонентов Java, предлагаемых Aspose. актуальные версии каждого из наших компонентов Java. #$NL " + "Используя Aspose.Total для Java, разработчики могут создавать широкий спектр приложений. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Добавьте таблицу в коллекцию абзацев нужного раздела
page.Paragraphs.Add(table);
// Установите границу ячейки по умолчанию, используя объект BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Установите границу таблицы, используя другой настраиваемый объект BorderInfo
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Создайте строки в таблице, а затем ячейки в строках
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве вы узнали, как использовать заменяемые символы в верхнем и нижнем колонтитулах PDF-документа с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы сможете создать PDF-файл, установить поля, добавить верхний и нижний колонтитулы с заменяемыми символами и сохранить PDF-файл.