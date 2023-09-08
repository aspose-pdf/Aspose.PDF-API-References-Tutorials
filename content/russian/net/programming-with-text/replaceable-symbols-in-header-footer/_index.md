---
title: Сменные символы в верхнем колонтитуле
linktitle: Сменные символы в верхнем колонтитуле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как использовать заменяемые символы в верхнем и нижнем колонтитуле PDF-документа с помощью Aspose.PDF для .NET.
type: docs
weight: 320
url: /ru/net/programming-with-text/replaceable-symbols-in-header-footer/
---
В этом уроке мы объясним, как использовать заменяемые символы в верхнем и нижнем колонтитуле PDF-документа с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс создания PDF-файла, настройки полей, добавления верхнего и нижнего колонтитула со заменяемыми символами и сохранения PDF-файла с использованием предоставленного исходного кода C#.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором вы хотите сохранить созданный PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir`переменная с путем к желаемому каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте PDF-документ и страницу.

 Далее мы создаем новый PDF-документ и добавляем к нему страницу с помощью`Document` класс и`Page` класс из библиотеки Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Шаг 3: Установите поля

 Мы устанавливаем поля для страницы с помощью`MarginInfo`сорт. Отрегулируйте значения маржи в соответствии с вашими требованиями.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Шаг 4. Добавьте заголовок со заменяемыми символами

 Мы создаем`HeaderFooter` объект для страницы и добавьте`TextFragment` со сменными символами к нему.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// При необходимости установите свойства текста
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Добавьте больше TextFragments или настройте по мере необходимости.
```

## Шаг 5. Добавьте нижний колонтитул со заменяемыми символами

 Аналогичным образом мы создаем`HeaderFooter` объект для нижнего колонтитула страницы и добавьте`TextFragment` объекты со сменными символами к нему.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Добавьте больше TextFragments или настройте по мере необходимости.

hfFoot.Paragraphs.Add(tab2);
```

## Шаг 6. Сохраните PDF-документ

Наконец, мы сохраняем PDF-документ в указанный выходной файл.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Пример исходного кода для заменяемых символов в нижнем колонтитуле с использованием Aspose.PDF для .NET 
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
// Назначьте экземпляр MarginInfo свойству Margin раздела sec1.PageInfo.
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Создайте экземпляр текстового абзаца, в котором будет храниться содержимое для отображения в виде заголовка.
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
// Создайте объект HeaderFooter для раздела.
HeaderFooter hfFoot = new HeaderFooter();
// Установите для объекта HeaderFooter нечетный и четный нижний колонтитул.
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Добавить текстовый абзац, содержащий текущий номер страницы из общего количества страниц.
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Создать экземпляр табличного объекта
Table tab2 = new Table();
// Добавьте таблицу в коллекцию абзацев нужного раздела
hfFoot.Paragraphs.Add(tab2);
// Задается шириной столбца таблицы
tab2.ColumnWidths = "165 172 165";
// Создайте строки в таблице, а затем ячейки в строках.
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Установите вертикальное выравнивание текста по центру.
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java — это компиляция всех компонентов Java, предлагаемых Aspose. Он компилируется #$NL" + "ежедневно, чтобы гарантировать, что он содержит самые актуальные версии каждого компонента. наших компонентов Java. #$NL " + "Используя Aspose.Total для разработчиков Java, разработчики могут создавать широкий спектр приложений. #$NL #$NL #$NP" + "Aspose.Total for Java — это компиляция всех компонентов Java предлагается Aspose. Он компилируется #$NL" + "ежедневно, чтобы гарантировать, что он содержит самые последние версии каждого из наших компонентов Java. #$NL " + "Использование Aspose.Total для разработчиков Java может создать широкий #$NL #$NL #$NP" + "Aspose.Total for Java представляет собой компиляцию всех компонентов Java, предлагаемых Aspose. Он компилируется #$NL" + "ежедневно, чтобы гарантировать, что он содержит наиболее актуальные версии каждого из наших Java-компонентов. #$NL " + "Использование Aspose.Total для разработчиков Java позволяет создавать широкий спектр приложений. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Добавьте таблицу в коллекцию абзацев нужного раздела
page.Paragraphs.Add(table);
// Установите границу ячейки по умолчанию, используя объект BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Установите границу таблицы, используя другой настраиваемый объект BorderInfo.
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Создайте строки в таблице, а затем ячейки в строках.
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

В этом уроке вы узнали, как использовать заменяемые символы в верхнем и нижнем колонтитуле PDF-документа с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы можете создать PDF-файл, установить поля, добавить верхний и нижний колонтитулы со заменяемыми символами и сохранить PDF-файл.

### Часто задаваемые вопросы

#### Вопрос: Какова цель урока «Заменяемые символы в нижнем колонтитуле»?

О: Учебное пособие «Заменяемые символы в нижнем колонтитуле» призвано помочь вам в процессе использования библиотеки Aspose.PDF для .NET для добавления заменяемых символов в верхний и нижний колонтитулы PDF-документа. Сменные символы позволяют динамически заменять определенные заполнители фактическими значениями при создании PDF-файла.

#### Вопрос: Что такое заменяемые символы в контексте верхнего и нижнего колонтитула PDF-файла?

О: Заменяемые символы — это заполнители, которые можно вставлять в верхний и нижний колонтитулы PDF-документа. Эти символы действуют как динамические заполнители для значений, которые можно заполнить во время выполнения, например номеров страниц, дат и пользовательской информации.

#### Вопрос: Зачем мне использовать заменяемые символы в верхнем и нижнем колонтитуле PDF-файла?

О: Сменные символы в верхнем и нижнем колонтитуле полезны, если вы хотите включить в PDF-документы динамическую информацию, такую как номера страниц, даты или другие переменные данные, которые могут измениться при создании документа.

#### Вопрос: Как установить поля для страницы PDF?

 О: Вы можете установить поля для страницы PDF, используя`MarginInfo` класс и присвоение его`Margin` собственность`PageInfo` страницы. При необходимости отрегулируйте значения полей.

#### Вопрос: Как добавить заменяемые символы в верхний и нижний колонтитулы?

 О: Вы можете добавить заменяемые символы, создав`HeaderFooter` объект для верхнего и нижнего колонтитула страницы. Затем вы можете добавить`TextFragment`объекты с нужным текстом, включая заменяемые символы, в`Paragraphs` коллекция`HeaderFooter` объект.

#### Вопрос: Могу ли я настроить внешний вид заменяемых символов?

 О: Да, вы можете настроить внешний вид заменяемых символов, изменив свойства`TextFragment` объекты, содержащие символы. Вы можете установить такие свойства, как шрифт, размер шрифта, цвет, выравнивание и межстрочный интервал.

#### Вопрос: Какие сменные символы я могу использовать?

О: Вы можете использовать различные заменяемые символы, например:

- `$p`: Номер текущей страницы.
- `$P`: Общее количество страниц.
- `$d`: Текущая дата.
- `$t`: Текущее время.
- Пользовательские заполнители, которые вы определяете.

#### Вопрос: Могу ли я включить другой текст и форматирование вокруг заменяемых символов?

 О: Да, вы можете включать другой текст и форматирование вокруг заменяемых символов внутри`TextFragment` объекты. Это позволяет создавать более сложные верхние и нижние колонтитулы, включающие динамический и статический контент.

#### Вопрос: Как сохранить созданный PDF-документ?

 О: Чтобы сохранить созданный PDF-документ, вы можете использовать`Save` метод`Document`сорт. Укажите желаемый путь и имя выходного файла в качестве аргумента.

#### Вопрос: Требуется ли для работы с этим руководством действующая лицензия Aspose?

О: Да, для успешного выполнения кода в этом руководстве требуется действующая лицензия Aspose. Вы можете получить полную лицензию или 30-дневную временную лицензию на веб-сайте Aspose.