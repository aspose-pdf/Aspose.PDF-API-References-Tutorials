---
title: Автоподгонка к окну
linktitle: Автоподгонка к окну
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по использованию Aspose.PDF для .NET и автоматической подгонке к окну при создании PDF.
type: docs
weight: 50
url: /ru/net/programming-with-tables/auto-fit-to-window/
---
Следующая статья представляет собой пошаговое руководство о том, как использовать предоставленный исходный код C# для реализации функции Auto Fit To Window с помощью библиотеки Aspose.PDF для .NET. Функция Auto Fit To Window позволяет создавать PDF-файлы с макетом, адаптированным к окну просмотра. Эта функция особенно полезна, когда вы хотите, чтобы ваш PDF-документ автоматически подстраивался под размер окна программы чтения PDF-файлов, используемого пользователем.

## Шаг 1: Настройка среды

Прежде чем начать, вам необходимо установить на свой компьютер библиотеку Aspose.PDF для .NET. Также не забудьте импортировать необходимые пространства имен в свой проект.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создание PDF-документа

 Для начала необходимо создать`Document` объект, вызвав его конструктор по умолчанию.

```csharp
Document doc = new Document();
```

 Далее создайте раздел в`Pdf` объект.

```csharp
Page sec1 = doc.Pages.Add();
```

## Шаг 3: Добавление таблицы в документ

 На этом этапе мы собираемся добавить таблицу в наш PDF-документ. Сначала создайте`Table` объект.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Затем добавьте таблицу в коллекцию абзацев раздела.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Шаг 4: Настройка внешнего вида таблицы

Вы можете настроить внешний вид таблицы, установив такие свойства, как границы ячеек и поля.

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

Теперь давайте добавим строки и ячейки в нашу таблицу. Начните с создания строки и добавления ячеек в эту строку.

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

### Пример исходного кода для Auto Fit To Window с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создайте объект Pdf, вызвав его пустой конструктор
Document doc = new Document();
// Создайте раздел в объекте Pdf
Page sec1 = doc.Pages.Add();

// Создать экземпляр табличного объекта
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Добавьте таблицу в коллекцию абзацев нужного раздела
sec1.Paragraphs.Add(tab1);

// Задайте ширину столбцов таблицы
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Установите границу ячейки по умолчанию, используя объект BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Установите границу таблицы, используя другой настраиваемый объект BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Создайте объект MarginInfo и установите его левое, нижнее, правое и верхнее поля.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Установите заполнение ячейки по умолчанию для объекта MarginInfo
tab1.DefaultCellPadding = margin;

// Создайте строки в таблице, а затем ячейки в строках
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

В этом руководстве мы узнали, как использовать Aspose.PDF для .NET для создания файла PDF с функцией автоматического подгонки под размер окна. Эта функция чрезвычайно полезна, когда вы хотите, чтобы ваш PDF-документ автоматически подстраивался под размер окна просмотра. Aspose.PDF для .NET предлагает множество других мощных функций для создания файлов PDF и управления ими. Я призываю вас продолжить изучение этой библиотеки, чтобы открыть для себя все ее возможности.

### Часто задаваемые вопросы

#### В: Какова цель функции «Автоподгонка к окну» при создании PDF-файлов?

О. Функция «Автоподгонка к окну» при создании PDF-файлов гарантирует, что макет PDF-документа автоматически подстраивается под размер окна программы чтения PDF-файлов, используемого пользователем. Это обеспечивает лучший просмотр и гарантирует, что контент идеально вписывается в доступную область просмотра.

#### В: Могу ли я настроить внешний вид таблицы, например размер шрифта и цвета?

О: Да, вы можете настроить внешний вид таблицы в документе PDF с помощью Aspose.PDF для .NET. Предоставленный фрагмент кода демонстрирует, как установить такие свойства, как границы ячеек, поля и ширину столбцов. Вы можете дополнительно настроить размер шрифта, цвета и другие аспекты стиля таблицы и ее содержимого.

#### В: Как мне интегрировать Aspose.PDF для .NET в мой проект C#?

О: Чтобы использовать Aspose.PDF для .NET в вашем проекте C#, вам необходимо сначала установить на свой компьютер библиотеку Aspose.PDF для .NET. Затем вы можете добавить ссылку на библиотеку в свой проект C#. Наконец, импортируйте необходимые пространства имен для доступа к классам и методам, предоставляемым Aspose.PDF для .NET.

#### Вопрос. Совместим ли Aspose.PDF для .NET с приложениями .NET Core?

О: Да, Aspose.PDF для .NET совместим с приложениями .NET Core. Он поддерживает различные платформы .NET, включая .NET Framework, .NET Core и .NET 5.0+.

#### В: Могу ли я добавить больше таблиц в документ PDF?

О: Да, вы можете добавить несколько таблиц в документ PDF, выполнив действия, аналогичные показанным во фрагменте кода. Просто создайте новые экземпляры`Aspose.Pdf.Table` class и добавлять их в разные разделы или страницы PDF-документа.