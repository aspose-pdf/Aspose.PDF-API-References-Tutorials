---
title: Создать многоколоночный PDF
linktitle: Создать многоколоночный PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как создать многоколоночный PDF-файл с помощью Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-text/create-multi-column-pdf/
---

Этот учебник проведет вас через процесс создания многоколоночного PDF-файла с использованием Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов, например NuGet, для его установки.

## Шаг 1: Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В файле кода, в котором вы хотите создать PDF-файл с несколькими столбцами, добавьте следующие директивы using в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Шаг 3: Установите каталог документов
 В коде найдите строку, которая говорит`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4: Создайте новый экземпляр документа
 Создать новый`Document` объекта, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5. Установите поля страницы
 Укажите информацию о левом и правом полях для файла PDF, используя`PageInfo.Margin` собственность`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Шаг 6: Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью`Add` метод`Pages` коллекция. В предоставленном коде новая страница назначается переменной`page`.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 7: Создайте объект Graph и добавьте линию
 Создать новый`Graph` объект с определенными размерами и добавьте к нему линию. Затем добавьте`Graph` возражать против`Paragraphs` коллекция страницы.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Шаг 8: Добавьте текст заголовка с форматированием HTML
 Создать`HtmlFragment` объект и установите его содержимое в желаемый текст HTML. Затем добавьте фрагмент в`Paragraphs` коллекция страницы.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Шаг 9: Создайте FloatingBox с несколькими столбцами
 Создать`FloatingBox` объект и установить количество столбцов и интервал между столбцами. Затем добавьте текстовые фрагменты и строку в`Paragraphs` коллекция`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Шаг 10: Сохраните PDF-документ
 Сохраните документ PDF с помощью`Save` метод`Document` объект.

```csharp
doc.Save(dataDir);
```

### Пример исходного кода для создания многоколоночного Pdf с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Укажите информацию о левом поле для файла PDF
doc.PageInfo.Margin.Left = 40;
//Укажите информацию о правом поле для файла PDF.
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Добавьте строку в коллекцию paraphraphs объекта section
page.Paragraphs.Add(graph1);
// Укажите координаты линии
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Создайте строковые переменные с текстом, содержащим html-теги
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Создание текстовых абзацев, содержащих текст HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Добавьте четыре столбца в раздел
box.ColumnInfo.ColumnCount = 2;
// Установить расстояние между столбцами
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Создайте объект графиков, чтобы нарисовать линию
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Укажите координаты линии
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Добавьте строку в коллекцию абзацев объекта раздела
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Сохранить PDF-файл
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Заключение
Вы успешно создали PDF-файл с несколькими столбцами, используя Aspose.PDF для .NET. Полученный файл PDF теперь можно найти по указанному пути к выходному файлу.