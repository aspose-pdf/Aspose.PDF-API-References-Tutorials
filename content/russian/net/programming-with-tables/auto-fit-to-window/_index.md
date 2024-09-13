---
title: Автоматически подогнать под размер окна
linktitle: Автоматически подогнать под размер окна
second_title: Справочник по API Aspose.PDF для .NET
description: Пошаговое руководство по использованию Aspose.PDF для .NET и достижению автоматического подгона под размер окна при создании PDF-файла.
type: docs
weight: 50
url: /ru/net/programming-with-tables/auto-fit-to-window/
---
Следующая статья представляет собой пошаговое руководство по использованию предоставленного исходного кода C# для достижения функциональности Auto Fit To Window с помощью библиотеки Aspose.PDF для .NET. Функция Auto Fit To Window позволяет создавать файлы PDF с макетом, адаптированным к окну просмотра. Эта функция особенно полезна, когда вы хотите, чтобы ваш документ PDF автоматически подстраивался под размер окна программы чтения PDF, используемой пользователем.

## Шаг 1: Настройка среды

Прежде чем начать, вам необходимо установить библиотеку Aspose.PDF для .NET на вашем компьютере. Также не забудьте импортировать необходимые пространства имен в ваш проект.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создание PDF-документа

 Для начала вам нужно создать`Document` объект, вызвав его конструктор по умолчанию.

```csharp
Document doc = new Document();
```

 Далее создайте раздел в`Pdf` объект.

```csharp
Page sec1 = doc.Pages.Add();
```

## Шаг 3: Добавление таблицы в документ

 На этом шаге мы добавим таблицу в наш PDF-документ. Сначала создадим`Table` объект.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Затем добавьте таблицу в коллекцию абзацев раздела.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Шаг 4: Настройка внешнего вида таблицы

Вы можете настроить внешний вид таблицы, задав такие свойства, как границы ячеек и поля.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Шаг 4: Добавление строк и ячеек в таблицу

Теперь давайте добавим строки и ячейки в нашу таблицу. Начнем с создания строки и добавления ячеек в эту строку.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Шаг 5: Сохранение документа

Наконец, укажите путь к выходному файлу и сохраните документ.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для функции «Автоматическое подгонка под размер окна» с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создайте объект Pdf, вызвав его пустой конструктор.
Document doc = new Document();
// Создать раздел в объекте PDF
Page sec1 = doc.Pages.Add();

// Создать экземпляр объекта таблицы
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Добавить таблицу в подборку абзацев нужного раздела
sec1.Paragraphs.Add(tab1);

// Установите ширину столбцов таблицы
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Установить границу ячейки по умолчанию с помощью объекта BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Установить границу таблицы, используя другой настроенный объект BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Создайте объект MarginInfo и задайте его левое, нижнее, правое и верхнее поля.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Установите отступ ячейки по умолчанию для объекта MarginInfo
tab1.DefaultCellPadding = margin;

//Создайте строки в таблице, а затем ячейки в строках.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Сохранить обновленный документ, содержащий табличный объект
doc.Save(dataDir);
```

## Заключение

В этом уроке мы узнали, как использовать Aspose.PDF для .NET для создания PDF-файла с функцией Auto Fit To Window. Эта функция чрезвычайно полезна, когда вы хотите, чтобы ваш PDF-документ автоматически подстраивался под размер окна просмотра. Aspose.PDF для .NET предлагает множество других мощных функций для создания и обработки PDF-файлов. Я рекомендую вам изучить эту библиотеку подробнее, чтобы открыть для себя все ее возможности.

### Часто задаваемые вопросы

#### В: Каково назначение функции «Автоматическое подгонка под размер окна» при создании PDF-файлов?

A: Функция Auto Fit To Window при создании PDF гарантирует, что макет документа PDF автоматически подстраивается под размер окна PDF-ридера, используемого пользователем. Это обеспечивает лучший просмотр и гарантирует, что содержимое идеально вписывается в доступную область просмотра.

#### В: Могу ли я настроить внешний вид таблицы, например размер шрифта и цвета?

A: Да, вы можете настроить внешний вид таблицы в документе PDF с помощью Aspose.PDF для .NET. Приведенный фрагмент кода демонстрирует, как задать такие свойства, как границы ячеек, поля и ширина столбцов. Вы можете дополнительно настроить размер шрифта, цвета и другие аспекты стиля таблицы и ее содержимого.

#### В: Как интегрировать Aspose.PDF для .NET в мой проект C#?

A: Чтобы использовать Aspose.PDF для .NET в вашем проекте C#, вам необходимо сначала установить библиотеку Aspose.PDF для .NET на вашем компьютере. Затем вы можете добавить ссылку на библиотеку в ваш проект C#. Наконец, импортируйте необходимые пространства имен для доступа к классам и методам, предоставляемым Aspose.PDF для .NET.

#### В: Совместим ли Aspose.PDF для .NET с приложениями .NET Core?

A: Да, Aspose.PDF для .NET совместим с приложениями .NET Core. Он поддерживает различные платформы .NET, включая .NET Framework, .NET Core и .NET 5.0+.

#### В: Могу ли я добавить больше таблиц в PDF-документ?

A: Да, вы можете добавить несколько таблиц в PDF-документ, выполнив аналогичные шаги, как показано в фрагменте кода. Просто создайте новые экземпляры`Aspose.Pdf.Table` класс и добавляйте их в разные разделы или страницы PDF-документа.