---
title: Размещение текста вокруг изображения в PDF-файле
linktitle: Размещение текста вокруг изображения в PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как разместить текст вокруг изображения в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 260
url: /ru/net/programming-with-text/placing-text-around-image/
---
В этом уроке мы объясним, как разместить текст вокруг изображения в PDF-файле с помощью библиотеки Aspose.PDF для .NET. Мы пройдем пошаговый процесс создания таблицы, добавления изображения и размещения текста вокруг изображения, используя предоставленный исходный код C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена библиотека Aspose.PDF для .NET.
- Базовое понимание программирования на C#.

## Шаг 1. Настройте каталог документов

 Сначала вам нужно указать путь к каталогу, в котором вы хотите сохранить созданный PDF-файл. Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir`переменная с путем к желаемому каталогу.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте документ и страницу.

 Далее мы создаем`Document` объект и добавьте к нему страницу с помощью`Pages.Add()` метод.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Шаг 3: Создайте таблицу

 Создаем таблицу с помощью`Table` class и добавьте его в коллекцию абзацев страницы.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Шаг 4. Установите ширину и поля столбцов таблицы

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

## Шаг 5. Добавьте изображение в таблицу

 Мы создаем`Image` объект, укажите путь к файлу изображения и установите фиксированную высоту и ширину изображения. Затем мы добавляем изображение в коллекцию абзацев ячейки таблицы.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Шаг 6. Добавьте текст вокруг изображения

 Мы создаем строковые переменные, содержащие текст в формате HTML, и создаем`HtmlFragment`объект. Затем мы добавляем текст HTML в ячейку таблицы, содержащую изображение.

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

## Шаг 8. Сохраните PDF-документ.

Наконец, мы сохраняем PDF-документ в указанный выходной файл.

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
// Добавьте таблицу в коллекцию абзацев нужного раздела
page.Paragraphs.Add(table1);
// Задается шириной столбца таблицы
table1.ColumnWidths = "120 270";
// Создайте объект MarginInfo и установите его левое, нижнее, правое и верхнее поля.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Установите заполнение ячеек по умолчанию для объекта MarginInfo.
table1.DefaultCellPadding = margin;
// Создайте строки в таблице, а затем ячейки в строках.
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Создайте объект изображения
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Укажите путь к файлу изображения
logo.File = dataDir + "aspose-logo.jpg";
// Укажите изображение с фиксированной высотой
logo.FixHeight = 120;
// Укажите фиксированную ширину изображения
logo.FixWidth = 110;
row1.Cells.Add();
// Добавьте изображение в коллекцию абзацев ячейки таблицы.
row1.Cells[0].Paragraphs.Add(logo);
// Создание строковых переменных с текстом, содержащим теги HTML.
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Создайте текстовый объект, который будет добавлен справа от изображения.
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Добавьте текстовые абзацы, содержащие текст HTML, в ячейку таблицы.
row1.Cells[1].Paragraphs.Add(TitleText);
// Установите вертикальное выравнивание содержимого строки как «Сверху».
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Создайте строки в таблице, а затем ячейки в строках.
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Установите значение диапазона строк для второй строки как 2.
SecondRow.Cells[0].ColSpan = 2;
// Установите вертикальное выравнивание второй строки как Верхнее.
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Добавьте текстовые абзацы, содержащие текст HTML, в ячейку таблицы.
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Сохраните PDF-файл
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Заключение

В этом уроке вы узнали, как разместить текст вокруг изображения в PDF-документе с помощью библиотеки Aspose.PDF для .NET. Следуя пошаговому руководству и выполнив предоставленный код C#, вы можете создать таблицу, добавить изображение и расположить текст вокруг изображения в документе PDF.

### Часто задаваемые вопросы

#### Вопрос: Какова цель урока «Размещение текста вокруг изображения в PDF-файле»?

О: Учебное пособие «Размещение текста вокруг изображения в PDF-файле» демонстрирует, как использовать библиотеку Aspose.PDF для .NET для размещения текста вокруг изображения в PDF-документе. Учебное пособие содержит пошаговое руководство и исходный код C#, которые помогут вам создать таблицу, добавить изображение и расположить текст вокруг изображения.

#### Вопрос: Зачем мне размещать текст вокруг изображения в PDF-документе?

О: Размещение текста вокруг изображения улучшает визуальное представление PDF-документов, делая их более привлекательными и информативными. Этот прием часто используется в документах, брошюрах, отчетах и других материалах, где требуется эстетично объединить изображения и текст.

#### Вопрос: Как настроить каталог документов?

О: Чтобы настроить каталог документов:

1.  Заменять`"YOUR DOCUMENT DIRECTORY"` в`dataDir` переменная с путем к каталогу, в котором вы хотите сохранить созданный PDF-файл.

#### Вопрос: Как создать таблицу и добавить в нее изображение?

 О: Данное руководство проведет вас через процесс создания таблицы с помощью`Table` класс и добавление изображения в таблицу с помощью`Image` сорт. Прежде чем добавлять его в ячейку таблицы, вы укажете путь, высоту и ширину файла изображения.

#### Вопрос: Как расположить текст вокруг изображения?

 О: Чтобы разместить текст вокруг изображения, вы создадите текст в формате HTML, используя`HtmlFragment` сорт. Этот текст будет содержать как заголовок, так и основной текст. Затем вы добавите этот HTML-текст в ячейку таблицы, расположенную рядом с ячейкой изображения.

#### Вопрос: Могу ли я настроить внешний вид текста и изображения?

О: Да, вы можете настроить внешний вид текста и изображения с помощью тегов и свойств HTML. Например, вы можете установить размеры шрифта, цвета, стили и выравнивание текста. Дополнительно вы можете настроить размер и размеры изображения.

#### Вопрос: Как сохранить PDF-документ?

 О: После добавления изображения и текста в таблицу вы можете сохранить PDF-документ с помощью`Save` метод`Document` сорт. Укажите желаемый путь к выходному файлу в качестве аргумента`Save` метод.

#### Вопрос: Каков ожидаемый результат этого руководства?

О: Следуя инструкциям и выполнив предоставленный код C#, вы создадите PDF-документ, демонстрирующий, как разместить текст вокруг изображения. Выходной документ будет содержать таблицу с изображением и текстом, расположенными вокруг нее.

#### Вопрос: Могу ли я использовать другие форматы изображений, кроме JPG?

 О: Да, вы можете использовать различные форматы изображений, поддерживаемые библиотекой Aspose.PDF, такие как PNG, BMP, GIF и другие. При создании`Image` объект, укажите путь к файлу нужного формата изображения.

#### Вопрос: Требуется ли для работы с этим руководством действующая лицензия Aspose?

О: Да, для корректной работы этого руководства требуется действующая лицензия Aspose. Вы можете приобрести полную лицензию или получить 30-дневную временную лицензию на веб-сайте Aspose.