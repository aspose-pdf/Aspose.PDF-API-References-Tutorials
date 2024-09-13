---
title: Заменяемые символы в верхнем и нижнем колонтитулах
linktitle: Заменяемые символы в верхнем и нижнем колонтитулах
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как использовать заменяемые символы в верхнем и нижнем колонтитуле PDF-документа с помощью Aspose.PDF для .NET.
type: docs
weight: 320
url: /ru/net/programming-with-text/replaceable-symbols-in-header-footer/
---
В этом уроке мы объясним, как использовать заменяемые символы в верхнем и нижнем колонтитуле документа PDF с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс создания PDF, установки полей, добавления верхнего и нижнего колонтитула со заменяемыми символами и сохранения PDF с помощью предоставленного исходного кода C#.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовые знания программирования на C#.

## Шаг 1: Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором вы хотите сохранить созданный PDF-файл. Заменить`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменную с путем к нужному вам каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте PDF-документ и страницу

 Далее мы создаем новый PDF-документ и добавляем в него страницу с помощью`Document` класс и`Page` класс из библиотеки Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Шаг 3: Установите поля

 Мы устанавливаем поля для страницы с помощью`MarginInfo` класс. Отрегулируйте значения полей в соответствии с вашими требованиями.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Шаг 4: Добавьте заголовок со сменными символами

 Мы создаем`HeaderFooter` объект для страницы и добавьте`TextFragment` со сменными символами.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// При желании задайте свойства текста.
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Добавьте больше текстовых фрагментов или настройте их по мере необходимости.
```

## Шаг 5: Добавьте нижний колонтитул со сменными символами

 Аналогично мы создаем`HeaderFooter` объект для нижнего колонтитула страницы и добавьте`TextFragment` объекты со сменными символами.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Добавьте больше текстовых фрагментов или настройте их по мере необходимости.

hfFoot.Paragraphs.Add(tab2);
```

## Шаг 6: Сохраните PDF-документ.

Наконец, мы сохраняем PDF-документ в указанный выходной файл.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Пример исходного кода для заменяемых символов в верхнем и нижнем колонтитулах с использованием Aspose.PDF для .NET 
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
// Создайте текстовый абзац, в котором будет храниться содержимое, отображаемое в качестве заголовка.
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
// Установите объект HeaderFooter для четных и нечетных нижних колонтитулов
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Добавить текстовый абзац, содержащий текущий номер страницы из общего количества страниц.
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Создать экземпляр объекта таблицы
Table tab2 = new Table();
// Добавить таблицу в подборку абзацев нужного раздела
hfFoot.Paragraphs.Add(tab2);
// Установите ширину столбцов таблицы
tab2.ColumnWidths = "165 172 165";
//Создайте строки в таблице, а затем ячейки в строках.
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Установить вертикальное выравнивание текста по центру.
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java — это компиляция каждого компонента Java, предлагаемого Aspose. Он компилируется ежедневно, чтобы гарантировать, что он содержит самые последние версии каждого из наших компонентов Java. #$NL " + "Используя Aspose.Total for Java, разработчики могут создавать широкий спектр приложений. #$NL #$NL #$NP" + "Aspose.Total for Java — это компиляция каждого компонента Java, предлагаемого Aspose. Он компилируется ежедневно, чтобы гарантировать, что он содержит самые последние версии каждого из наших компонентов Java. #$NL " + "Используя Aspose.Total for Java, разработчики могут создавать широкий спектр приложений. #$NL #$NL #$NP" + "Aspose.Total for Java — это компиляция каждого компонента Java, предлагаемого Aspose. Он компилируется ежедневно, чтобы гарантировать, что он содержит самые последние версии каждого из наших компонентов Java. #$NL " + "Используя Aspose.Total для разработчиков Java, можно создавать широкий спектр приложений. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Добавить таблицу в подборку абзацев нужного раздела
page.Paragraphs.Add(table);
// Установить границу ячейки по умолчанию с помощью объекта BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Установить границу таблицы, используя другой настроенный объект BorderInfo
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//Создайте строки в таблице, а затем ячейки в строках.
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

В этом уроке вы узнали, как использовать заменяемые символы в верхнем и нижнем колонтитуле документа PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете создать PDF, задать поля, добавить верхний и нижний колонтитулы со заменяемыми символами и сохранить PDF.

### Часто задаваемые вопросы

#### В: Какова цель урока «Заменяемые символы в верхнем и нижнем колонтитуле»?

A: Учебник "Заменяемые символы в верхнем и нижнем колонтитуле" призван провести вас через процесс использования библиотеки Aspose.PDF для .NET для добавления заменяемых символов в верхний и нижний колонтитулы документа PDF. Заменяемые символы позволяют вам динамически заменять определенные заполнители фактическими значениями при создании PDF.

#### В: Что такое заменяемые символы в контексте верхнего и нижнего колонтитула PDF-файла?

A: Заменяемые символы — это заполнители, которые можно вставить в верхний и нижний колонтитулы документа PDF. Эти символы действуют как динамические заполнители для значений, которые можно заполнить во время выполнения, например, номера страниц, даты и пользовательская информация.

#### В: Зачем мне использовать заменяемые символы в верхнем и нижнем колонтитуле PDF-файла?

A: Заменяемые символы в верхнем и нижнем колонтитулах полезны, когда вы хотите включить в свои PDF-документы динамическую информацию, такую как номера страниц, даты или другие переменные данные, которые могут измениться при создании документа.

#### В: Как установить поля для страницы PDF-файла?

 A: Вы можете установить поля для страницы PDF с помощью`MarginInfo` класс и назначение его`Margin` собственность`PageInfo` страницы. Отрегулируйте значения полей по мере необходимости.

#### В: Как добавить заменяемые символы в верхний и нижний колонтитулы?

 A: Вы можете добавить заменяемые символы, создав`HeaderFooter` объект для верхнего и нижнего колонтитула страницы. Затем вы можете добавить`TextFragment`объекты с нужным текстом, включая заменяемые символы, в`Paragraphs` коллекция`HeaderFooter` объект.

#### В: Могу ли я настроить внешний вид заменяемых символов?

 A: Да, вы можете настроить внешний вид заменяемых символов, изменив свойства`TextFragment` объекты, содержащие символы. Вы можете задать такие свойства, как шрифт, размер шрифта, цвет, выравнивание и межстрочный интервал.

#### В: Какие сменные символы я могу использовать?

A: Вы можете использовать различные сменные символы, такие как:

- `$p`: Текущий номер страницы.
- `$P`: Общее количество страниц.
- `$d`: Текущая дата.
- `$t`: Текущее время.
- Пользовательские заполнители, которые вы определяете.

#### В: Могу ли я включить другой текст и форматирование вокруг заменяемых символов?

 A: Да, вы можете включить другой текст и форматирование вокруг заменяемых символов в`TextFragment` объекты. Это позволяет создавать более сложные верхние и нижние колонтитулы, включающие динамический и статический контент.

#### В: Как сохранить созданный PDF-документ?

 A: Чтобы сохранить созданный PDF-документ, вы можете использовать`Save` Метод`Document`класс. Укажите желаемый путь к выходному файлу и имя в качестве аргумента.

#### В: Требуется ли для этого руководства действующая лицензия Aspose?

A: Да, для успешного выполнения кода в этом руководстве требуется действующая лицензия Aspose. Вы можете получить полную лицензию или 30-дневную временную лицензию на веб-сайте Aspose.