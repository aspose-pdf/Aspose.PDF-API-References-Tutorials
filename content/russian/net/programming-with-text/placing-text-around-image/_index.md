---
title: Размещение текста вокруг изображения в PDF-файле
linktitle: Размещение текста вокруг изображения в PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как разместить текст вокруг изображения в PDF-файле с помощью Aspose.PDF для .NET.
type: docs
weight: 260
url: /ru/net/programming-with-text/placing-text-around-image/
---
В этом уроке мы объясним, как разместить текст вокруг изображения в PDF-файле с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс создания таблицы, добавления изображения и размещения текста вокруг изображения с помощью предоставленного исходного кода C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовые знания программирования на C#.

## Шаг 1: Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором вы хотите сохранить созданный PDF-файл. Заменить`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменную с путем к нужному вам каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте документ и страницу

 Далее мы создаем`Document` объект и добавьте к нему страницу с помощью`Pages.Add()` метод.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Шаг 3: Создайте таблицу

 Мы создаем таблицу с помощью`Table` класс и добавьте его в коллекцию абзацев страницы.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Шаг 4: Установка ширины и полей столбцов таблицы

 Мы задаем ширину столбцов таблицы и создаем`MarginInfo` объект для установки полей.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Шаг 5: Добавьте изображение в таблицу

 Мы создаем`Image` объект, указать путь к файлу изображения и задать фиксированную высоту и ширину изображения. Затем мы добавляем изображение в коллекцию абзацев ячейки таблицы.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Шаг 6: Добавьте текст вокруг изображения

 Мы создаем строковые переменные, содержащие текст в формате HTML, и создаем`HtmlFragment`объект. Затем мы добавляем HTML-текст в ячейку таблицы, содержащую изображение.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Шаг 7: Добавьте дополнительный текст

 Мы создаем еще один`HtmlFragment` объект, содержащий дополнительный текст в формате HTML, и добавьте его в отдельную ячейку таблицы.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Шаг 8: Сохраните PDF-документ.

Наконец, мы сохраняем PDF-документ в указанный выходной файл.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Пример исходного кода для размещения текста вокруг изображения с помощью Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр объекта документа
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Создать страницу в PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Создать экземпляр объекта таблицы
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Добавить таблицу в подборку абзацев нужного раздела
page.Paragraphs.Add(table1);
// Установите ширину столбцов таблицы
table1.ColumnWidths = "120 270";
// Создайте объект MarginInfo и задайте его левое, нижнее, правое и верхнее поля.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Установите отступ ячейки по умолчанию для объекта MarginInfo
table1.DefaultCellPadding = margin;
// Создайте строки в таблице, а затем ячейки в строках.
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Создать объект изображения
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Укажите путь к файлу изображения
logo.File = dataDir + "aspose-logo.jpg";
// Укажите фиксированную высоту изображения
logo.FixHeight = 120;
// Укажите фиксированную ширину изображения
logo.FixWidth = 110;
row1.Cells.Add();
// Добавить изображение в коллекцию абзацев ячейки таблицы
row1.Cells[0].Paragraphs.Add(logo);
// Создание строковых переменных с текстом, содержащим HTML-теги
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Создайте текстовый объект, который будет добавлен справа от изображения.
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Добавьте текстовые абзацы, содержащие HTML-текст, в ячейку таблицы.
row1.Cells[1].Paragraphs.Add(TitleText);
// Установить вертикальное выравнивание содержимого строки по верхнему краю
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Создайте строки в таблице, а затем ячейки в строках.
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Установите значение диапазона строк для второй строки как 2
SecondRow.Cells[0].ColSpan = 2;
// Установить вертикальное выравнивание второй строки как «Сверху»
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Добавьте текстовые абзацы, содержащие HTML-текст, в ячейку таблицы.
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Сохраните PDF-файл
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Заключение

В этом уроке вы узнали, как разместить текст вокруг изображения в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполняя предоставленный код C#, вы можете создать таблицу, добавить изображение и разместить текст вокруг изображения в документе PDF.

### Часто задаваемые вопросы

#### В: Какова цель урока «Размещение текста вокруг изображения в PDF-файле»?

A: Учебник "Размещение текста вокруг изображения в PDF-файле" демонстрирует, как использовать библиотеку Aspose.PDF для .NET для размещения текста вокруг изображения в PDF-документе. Учебник содержит пошаговое руководство и исходный код C#, которые помогут вам создать таблицу, добавить изображение и расположить текст вокруг изображения.

#### В: Зачем мне размещать текст вокруг изображения в PDF-документе?

A: Размещение текста вокруг изображения улучшает визуальное представление ваших PDF-документов, делая их более интересными и информативными. Этот прием часто используется в документах, брошюрах, отчетах и других материалах, где вы хотите объединить изображения и текст эстетически приятным образом.

#### В: Как настроить каталог документов?

A: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, в котором вы хотите сохранить сгенерированный PDF-файл.

#### В: Как создать таблицу и добавить в нее изображение?

 A: Учебник проведет вас через процесс создания таблицы с помощью`Table` класс и добавление изображения в таблицу с помощью`Image` класс. Вы укажете путь к файлу изображения, высоту и ширину перед его добавлением в ячейку таблицы.

#### В: Как расположить текст вокруг изображения?

 A: Чтобы разместить текст вокруг изображения, вам нужно создать текст в формате HTML с помощью`HtmlFragment` класс. Этот текст будет содержать как заголовок, так и основной текст. Затем вы добавите этот HTML-текст в ячейку таблицы, которая находится рядом с ячейкой изображения.

#### В: Могу ли я настроить внешний вид текста и изображения?

A: Да, вы можете настроить внешний вид текста и изображения с помощью HTML-тегов и свойств. Например, вы можете задать размеры шрифта, цвета, стили и выравнивание для текста. Кроме того, вы можете настроить размер и габариты изображения.

#### В: Как сохранить PDF-документ?

 A: После добавления изображения и текста в таблицу вы можете сохранить PDF-документ с помощью`Save` Метод`Document` class. Укажите желаемый путь к выходному файлу в качестве аргумента для`Save` метод.

#### В: Каков ожидаемый результат этого урока?

A: Следуя руководству и выполняя предоставленный код C#, вы сгенерируете PDF-документ, демонстрирующий, как разместить текст вокруг изображения. Выходной документ будет содержать таблицу с изображением и текстом, расположенным вокруг него.

#### В: Могу ли я использовать другие форматы изображений, помимо JPG?

 A: Да, вы можете использовать различные форматы изображений, поддерживаемые библиотекой Aspose.PDF, такие как PNG, BMP, GIF и т. д. При создании`Image` объект, укажите путь к файлу нужного формата изображения.

#### В: Требуется ли для этого руководства действующая лицензия Aspose?

A: Да, для корректной работы этого руководства требуется действующая лицензия Aspose. Вы можете приобрести полную лицензию или получить 30-дневную временную лицензию на веб-сайте Aspose.