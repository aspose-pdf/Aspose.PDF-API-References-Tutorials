---
title: Элемент таблицы стилей
linktitle: Элемент таблицы стилей
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как создать и оформить элемент таблицы в Aspose.PDF для .NET с помощью пошаговых инструкций, настраиваемого стиля и соответствия PDF/UA.
type: docs
weight: 170
url: /ru/net/programming-with-tagged-pdf/style-table-element/
---
## Введение

В этой статье мы рассмотрим, как создать и оформить элемент таблицы с помощью Aspose.PDF для .NET. Вы узнаете, как структурировать таблицу, применять пользовательские стили и проверять соответствие вашего документа стандартам PDF/UA. К концу этого руководства вы сможете с легкостью создавать профессионально выглядящие таблицы в ваших PDF-файлах!

## Предпосылки

Прежде чем приступить к обучению, вам необходимо убедиться, что у вас есть следующее:

1. Visual Studio или аналогичная IDE, установленная на вашем компьютере.
2. .NET Framework или .NET Core SDK для запуска приложения.
3.  Aspose.PDF для библиотеки .NET, загруженной и указанной в вашем проекте. Вы можете получить последнюю версию с[здесь](https://releases.aspose.com/pdf/net/).
4.  Действующая лицензия Aspose или[временная лицензия](https://purchase.aspose.com/temporary-license/) чтобы разблокировать полную функциональность библиотеки.

## Импортные пакеты

Для начала импортируйте необходимые пространства имен в свой проект:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Эти пространства имен охватывают основные операции PDF, тегированный контент, таблицы и форматирование текста.

Теперь давайте разберем процесс создания и стилизации таблицы в Aspose.PDF. Мы подробно рассмотрим каждый раздел, чтобы вы могли следить за процессом.

## Шаг 1: Создайте новый PDF-документ и настройте тегированный контент

На первом этапе мы создадим пустой PDF-документ и настроим его тегированное содержимое.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать новый PDF-документ
Document document = new Document();

// Настройка тегированного контента
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Начнем с создания нового`Document` объект, представляющий наш PDF.`TaggedContent`объект используется для управления структурой документа, обеспечивая соответствие стандартам доступности. Мы задаем заголовок и язык документа для правильной маркировки.

## Шаг 2: Определите корневой элемент

Далее мы создадим корневой элемент структуры, который будет выступать в качестве контейнера для всего содержимого нашего PDF-файла.

```csharp
// Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;
```

 The`RootElement` служит базовым контейнером для всех структурированных элементов, включая нашу таблицу. Он помогает поддерживать структурную иерархию документа, что важно как для организации, так и для доступности.

## Шаг 3: Создание и оформление элемента таблицы

 Теперь, когда корневой элемент настроен, мы создадим`TableElement` и применяйте стили, такие как цвет фона, границы и выравнивание.

```csharp
// Создать элемент структуры таблицы
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Оформите стол
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Мы создаем`TableElement` , который определяет структуру нашей таблицы.`BackgroundColor`, `Border` , и`Alignment` Свойства позволяют нам настраивать внешний вид таблицы.`Broken` свойство гарантирует, что если таблица разбивается на страницы, она разбивается вертикально.

## Шаг 4: Задайте размеры таблицы и стили ячеек

На этом этапе мы определим количество столбцов, отступы ячеек и другие важные свойства таблицы.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Мы указываем ширину столбцов, чтобы гарантировать равномерное расположение каждого столбца в таблице.`DefaultCellBorder`, `DefaultCellPadding` , и`DefaultCellTextState` определить стили ячеек по умолчанию, включая границы, отступы, цвет текста и размер шрифта.

## Шаг 5: Добавьте повторяющиеся строки и пользовательские стили

Мы также можем определить стили для повторяющихся строк и других определенных элементов таблицы, таких как верхние и нижние колонтитулы.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 The`RepeatingRowsCount` гарантирует, что первые три строки повторяются, если таблица занимает несколько страниц. Мы устанавливаем`RepeatingRowsStyle` чтобы применить индивидуальный цвет фона к этим строкам.

## Шаг 6: Добавьте элементы «голова», «тело» и «ножки» стола.

Теперь давайте создадим разделы заголовка, основного текста и нижнего колонтитула таблицы и заполним их содержимым.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Создать строку заголовка
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Заполнить тело таблицы
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Таблица разделена на три части: head, body и foot. Сначала мы создаем строку заголовка, используя`TableTHElement`и добавляем заголовки столбцов. Затем заполняем тело таблицы`TableTDElement`, заполняя каждую ячейку меткой, включающей ее положение.

## Шаг 7: Сохраните документ.

Наконец, мы сохраняем PDF-документ в указанном каталоге.

```csharp
// Сохраните помеченный PDF-документ
document.Save(dataDir + "StyleTableElement.pdf");
```

Этот шаг завершает процесс создания документа, сохраняя PDF-файл со стилизованной таблицей.

## Шаг 8: Проверка соответствия PDF/UA

После сохранения документа важно убедиться, что он соответствует стандартам PDF/UA (универсальная доступность).

```csharp
// Проверьте соответствие PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Здесь мы перезагружаем документ и проверяем его на соответствие стандартам PDF/UA. Соответствие гарантирует, что ваш PDF-файл соответствует требованиям доступности, что делает его пригодным для широкого круга пользователей.

## Заключение

С Aspose.PDF для .NET создание и стилизация таблиц в ваших PDF-документах становятся простыми и интуитивно понятными. Следуя шагам, описанным в этом руководстве, вы можете создавать таблицы с настраиваемыми стилями и обеспечивать соответствие ваших PDF-файлов стандартам доступности. Независимо от того, создаете ли вы отчеты или структурированные документы, таблицы являются мощным инструментом для наглядного представления данных.

## Часто задаваемые вопросы

### Можно ли добавлять изображения в ячейки таблицы?
 Да, вы можете вставлять изображения в ячейки таблицы с помощью`Image` элемент.

### Как динамически регулировать ширину столбцов?
 Вы можете установить`ColumnAdjustment` собственность`AutoFitToWindow` для автоматической регулировки ширины столбцов в зависимости от содержимого.

### Обязательно ли соответствие формату PDF/UA для всех документов?
Хотя это и не обязательно, но рекомендуется для документов, требующих высоких стандартов доступности.

### Могу ли я применять разные стили к определенным строкам?
 Да, вы можете настроить отдельные строки или ячейки, изменив их`TextState` или`BackgroundColor`.

### В чем преимущество использования тегированного контента?
Тегированный контент улучшает доступность документов и помогает обеспечить соответствие таким стандартам, как PDF/UA.