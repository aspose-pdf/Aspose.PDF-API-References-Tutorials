---
title: Стиль ячейки таблицы
linktitle: Стиль ячейки таблицы
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как стилизовать ячейки таблицы в PDF с помощью Aspose.PDF для .NET с помощью этого подробного руководства. Следуйте инструкциям, чтобы создать и отформатировать красивые таблицы PDF.
type: docs
weight: 160
url: /ru/net/programming-with-tagged-pdf/style-table-cell/
---
## Введение

Создание профессионально выглядящих таблиц PDF может быть сложным, но с Aspose.PDF для .NET это на удивление просто! Независимо от того, оформляете ли вы заголовки, нижние колонтитулы или определенные ячейки таблицы, эта мощная библиотека предоставляет вам все необходимые инструменты для создания прекрасно отформатированных документов PDF. В этом уроке мы рассмотрим, как оформить ячейки таблиц в документе PDF с помощью Aspose.PDF для .NET. Не волнуйтесь — мы разобьем все на простые шаги.

## Предпосылки

Прежде чем приступить к изучению кода, убедитесь, что у вас выполнены следующие предварительные условия:

1. Aspose.PDF для .NET: Загрузите и установите последнюю версию Aspose.PDF с сайта[здесь](https://releases.aspose.com/pdf/net/).
2. IDE (например, Visual Studio): настройка среды разработки .NET.
3. Базовые знания программирования на C#: Требуется небольшое знакомство с C#.
4.  Aspose.PDF License: Получите временную или полную лицензию, чтобы разблокировать все функции библиотеки. Вы можете получить бесплатную пробную версию[здесь](https://purchase.aspose.com/temporary-license/).

## Импортные пакеты

Перед началом убедитесь, что вы импортировали необходимые пространства имен. В вашем проекте вам понадобится следующее:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Теперь, когда все настроено, давайте перейдем к пошаговому руководству!

Мы собираемся создать таблицу в документе PDF и стилизовать ее ячейки. Каждый шаг будет подробно объяснять процесс.

## Шаг 1: Создайте новый PDF-документ

 Первый шаг — создать новый PDF-документ. В Aspose.PDF вы можете инициализировать новый`Document` объект, представляющий ваш PDF-файл.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать новый PDF-документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Здесь мы инициализируем PDF-документ и задаем его заголовок и язык. Это придает вашему документу правильную структуру, которая необходима для соответствия PDF/UA.

## Шаг 2: Настройте структуру таблицы

Таблицы в PDF-файлах определяются в элементах структуры. Давайте создадим таблицу и определим строки и столбцы таблицы.

```csharp
// Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;

// Создать элемент структуры таблицы
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Теперь мы определили заголовок таблицы (`TableTHeadElement`), тело (`TableTBodyElement`), и стопа (`TableTFootElement`) разделов. Вы можете думать о них как о скелете вашей таблицы.

## Шаг 3: Оформление ячеек заголовков

Стилизация ячеек заголовка делает их выделяющимися. Здесь мы применяем фоновые цвета, границы и выравнивание текста.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

На этом этапе мы проходим по каждой ячейке заголовка, задавая ей зелено-желтый фон, серую границу и выровненный по правому краю текст. Вы можете настроить эти свойства в соответствии с желаемым дизайном.

## Шаг 4: Заполнение и оформление тела таблицы

Тело таблицы содержит фактические данные. Вот как можно оформить каждую ячейку с помощью определенных полей, границ и настроек текста.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 На этом этапе мы заполняем тело таблицы четырьмя строками и стилизуем каждую ячейку желтым фоном и центрированным, жирным синим текстом. Мы также используем`MarginInfo`класс для определения отступов вокруг текста.

## Шаг 5: Оформление нижнего колонтитула

Чтобы придать таблице завершенную структуру, мы добавляем и оформляем ячейки нижнего колонтитула так же, как мы это делали с верхним колонтитулом.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

Раздел нижнего колонтитула оформлен аналогично заголовку, что позволяет читателям легко следить за структурой таблицы.

## Шаг 6: Сохраните и проверьте PDF-документ.

Наконец, мы сохраняем PDF-документ и проверяем его на соответствие стандарту PDF/UA.

```csharp
// Сохраните помеченный PDF-документ
document.Save(dataDir + "StyleTableCell.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Сохраняем PDF и используем`Validate` метод, гарантирующий соответствие стандартам доступности (соответствие PDF/UA).

## Заключение

Стилизация таблиц в PDF с помощью Aspose.PDF для .NET — это одновременно мощный и гибкий инструмент. С помощью нескольких строк кода вы можете создавать собственные дизайны таблиц, которые выделят ваши PDF-документы. Aspose.PDF упрощает создание отполированных PDF-файлов, начиная от настройки границ ячеек и фона и заканчивая обеспечением доступности.

## Часто задаваемые вопросы

### Можно ли применять разные стили к отдельным ячейкам таблицы?  
Да, вы можете стилизовать отдельные ячейки, настроив`TableTDElement` характеристики.

### Как объединить ячейки таблицы?  
 Вы можете использовать`ColSpan` и`RowSpan` свойства для объединения ячеек в таблице.

### Возможно ли создать таблицу, совместимую с PDF/UA?  
 Да, как показано в этом руководстве, вы можете обеспечить соответствие PDF/UA, проверив свой документ с помощью`Validate` метод.

### Можно ли использовать разные шрифты в ячейках таблицы?  
 Конечно! Вы можете указать разные шрифты, используя`TextState` объект для каждой ячейки.

### Как загрузить Aspose.PDF для .NET?  
 Вы можете скачать его с сайта[страница релизов](https://releases.aspose.com/pdf/net/).