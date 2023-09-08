---
title: Создать многоколоночный PDF-файл
linktitle: Создать многоколоночный PDF-файл
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как создать многоколоночный PDF-файл с помощью Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-text/create-multi-column-pdf/
---
Это руководство проведет вас через процесс создания многоколоночного PDF-файла с использованием Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Visual Studio или любой другой компилятор C#, установленный на вашем компьютере.
- Aspose.PDF для библиотеки .NET. Вы можете скачать его с официального сайта Aspose или использовать для установки менеджер пакетов, например NuGet.

## Шаг 1. Настройте проект
1. Создайте новый проект C# в предпочитаемой вами среде разработки.
2. Добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен.
В файле кода, в котором вы хотите создать многоколоночный PDF-файл, добавьте следующие директивы в верхней части файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Шаг 3. Установите каталог документов.
 В коде найдите строку с надписью`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с путем к каталогу, в котором хранятся ваши документы.

## Шаг 4. Создайте новый экземпляр документа.
 Создать экземпляр нового`Document` объект, добавив следующую строку кода:

```csharp
Document doc = new Document();
```

## Шаг 5. Установите поля страницы.
 Укажите информацию о левом и правом полях PDF-файла с помощью`PageInfo.Margin` собственность`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Шаг 6. Добавьте страницу в документ
 Добавьте новую страницу в документ с помощью`Add` метод`Pages`коллекция. В предоставленном коде новая страница присваивается переменной`page`.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 7. Создайте объект Graph и добавьте линию.
 Создать новый`Graph` объект с определенными размерами и добавьте к нему линию. Затем добавьте`Graph` возражать против`Paragraphs` коллекция страницы.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Шаг 8. Добавьте текст заголовка в формате HTML.
 Создать`HtmlFragment` объект и установите его содержимое в желаемый текст HTML. Затем добавьте фрагмент в`Paragraphs` коллекция страницы.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Шаг 9. Создайте FloatingBox с несколькими столбцами.
 Создать`FloatingBox` объект и установите количество столбцов и интервал между столбцами. Затем добавьте фрагменты текста и строку в`Paragraphs` коллекция`FloatingBox`.

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

## Шаг 10. Сохраните PDF-документ.
 Сохраните PDF-документ, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir);
```

### Пример исходного кода для создания многоколоночного PDF-файла с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Укажите информацию о левом поле для файла PDF.
doc.PageInfo.Margin.Left = 40;
//Укажите информацию о правом поле для файла PDF.
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Добавьте строку в коллекцию парафразов объекта раздела.
page.Paragraphs.Add(graph1);
// Укажите координаты линии
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Создание строковых переменных с текстом, содержащим теги HTML.
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Создание текстовых абзацев, содержащих текст HTML.
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Добавьте четыре столбца в раздел
box.ColumnInfo.ColumnCount = 2;
// Установите расстояние между столбцами
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Создайте объект графика для рисования линии.
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Укажите координаты линии
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Добавьте строку в коллекцию абзацев объекта раздела.
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
Вы успешно создали PDF-файл с несколькими столбцами, используя Aspose.PDF для .NET. Полученный PDF-файл теперь можно найти по указанному пути к выходному файлу.

### Часто задаваемые вопросы

#### Вопрос: Чему посвящено это руководство?

Это руководство посвящено процессу создания многоколоночного PDF-файла с использованием библиотеки Aspose.PDF для .NET. Приведенный исходный код C# демонстрирует необходимые шаги для достижения этой цели.

#### Вопрос: Какие пространства имен мне следует импортировать для этого руководства?

О: В файле кода, в котором вы хотите создать многоколоночный PDF-файл, импортируйте следующие пространства имен в начале файла:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Вопрос: Как указать каталог документа?

 О: В коде найдите строку`string dataDir = "YOUR DOCUMENT DIRECTORY";` и заменить`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

#### Вопрос: Как создать новый экземпляр документа?

 О: На шаге 4 вы создадите новый экземпляр`Document` объект, используя предоставленный код.

#### Вопрос: Как настроить поля страницы?

 О: На шаге 5 вы будете использовать`PageInfo.Margin` собственность`Document` чтобы указать информацию о левом и правом полях PDF-файла.

#### Вопрос: Как добавить страницу в документ?

 О: На шаге 6 вы добавите в документ новую страницу, используя`Add` метод`Pages` коллекция.

#### Вопрос: Как создать объект «График» и добавить линию?

 О: На шаге 7 вы создадите новый`Graph` объект, добавьте к нему строку, а затем добавьте`Graph` возражать против`Paragraphs` коллекция страницы.

#### Вопрос: Как добавить текст заголовка в формате HTML?

 О: На шаге 8 вы создадите`HtmlFragment` объект и установите его содержимое в желаемый текст HTML, затем добавьте фрагмент в`Paragraphs` коллекция страницы.

#### Вопрос: Как создать FloatingBox с несколькими столбцами?

 О: На шаге 9 вы создадите`FloatingBox` объект с несколькими столбцами и интервалом между столбцами, затем добавьте фрагменты текста и строку в`Paragraphs` коллекция`FloatingBox`.

#### Вопрос: Как сохранить PDF-документ?

 О: На шаге 10 вы сохраните PDF-документ, используя`Save` метод`Document` объект.

#### Вопрос: Каков основной вывод из этого урока?

О: Следуя этому руководству, вы узнали, как создать PDF-документ с несколькими столбцами, используя Aspose.PDF для .NET. Это может быть полезно для отображения контента в структурированном и организованном макете.