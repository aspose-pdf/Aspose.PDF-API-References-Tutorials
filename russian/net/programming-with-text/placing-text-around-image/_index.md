---
title: Размещение текста вокруг изображения
linktitle: Размещение текста вокруг изображения
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как разместить текст вокруг изображения в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 260
url: /ru/net/programming-with-text/placing-text-around-image/
---

В этом руководстве мы объясним, как разместить текст вокруг изображения в документе PDF с помощью библиотеки Aspose.PDF для .NET. Мы рассмотрим пошаговый процесс создания таблицы, добавления изображения и размещения текста вокруг изображения, используя предоставленный исходный код C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Во-первых, вам нужно указать путь к каталогу, в котором вы хотите сохранить сгенерированный файл PDF. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к нужному каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте документ и страницу

 Далее мы создаем`Document` объект и добавить к нему страницу с помощью`Pages.Add()` метод.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Шаг 3: Создайте таблицу

 Мы создаем таблицу с помощью`Table` class и добавьте его в коллекцию абзацев страницы.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Шаг 4: Установите ширину столбца таблицы и поля

 Мы устанавливаем ширину столбцов таблицы и создаем`MarginInfo` объект для установки полей.

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

 Мы создаем`Image` объекта, укажите путь к файлу изображения и задайте фиксированную высоту и ширину изображения. Затем мы добавляем изображение в коллекцию абзацев ячейки таблицы.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Шаг 6: Добавьте текст вокруг изображения

 Мы создаем строковые переменные, содержащие текст в формате HTML, и создаем`HtmlFragment` объект. Затем мы добавляем текст HTML в ячейку таблицы, содержащую изображение.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Шаг 7: Добавьте дополнительный текст

 Мы создаем еще один`HtmlFragment` объект, содержащий дополнительный текст в формате HTML, и добавить его в отдельную ячейку таблицы.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Шаг 8: Сохраните PDF-документ

Наконец, мы сохраняем документ PDF в указанный выходной файл.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Пример исходного кода для размещения текста вокруг изображения с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр объекта документа
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Создать страницу в PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Создать экземпляр табличного объекта
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
//Добавьте таблицу в коллекцию абзацев нужного раздела
page.Paragraphs.Add(table1);
// Задайте ширину столбцов таблицы
table1.ColumnWidths = "120 270";
// Создайте объект MarginInfo и установите его левое, нижнее, правое и верхнее поля.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Установите заполнение ячейки по умолчанию для объекта MarginInfo
table1.DefaultCellPadding = margin;
// Создайте строки в таблице, а затем ячейки в строках
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Создайте объект изображения
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Укажите путь к файлу изображения
logo.File = dataDir + "aspose-logo.jpg";
// Укажите фиксированную высоту изображения
logo.FixHeight = 120;
// Укажите фиксированную ширину изображения
logo.FixWidth = 110;
row1.Cells.Add();
// Добавьте изображение в коллекцию абзацев ячейки таблицы
row1.Cells[0].Paragraphs.Add(logo);
// Создайте строковые переменные с текстом, содержащим html-теги
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
// Создайте текстовый объект, который будет добавлен справа от изображения
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Добавьте текстовые абзацы, содержащие текст HTML, в ячейку таблицы.
row1.Cells[1].Paragraphs.Add(TitleText);
// Установите вертикальное выравнивание содержимого строки как Top
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Создайте строки в таблице, а затем ячейки в строках
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Установите значение диапазона строк для второй строки как 2
SecondRow.Cells[0].ColSpan = 2;
// Установите вертикальное выравнивание второй строки как Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Добавьте текстовые абзацы, содержащие текст HTML, в ячейку таблицы.
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Сохраните PDF-файл
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Заключение

В этом руководстве вы узнали, как размещать текст вокруг изображения в документе PDF с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы сможете создать таблицу, добавить изображение и расположить текст вокруг изображения в документе PDF.