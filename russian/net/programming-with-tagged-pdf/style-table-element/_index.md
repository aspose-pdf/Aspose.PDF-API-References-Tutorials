---
title: Элемент таблицы стилей
linktitle: Элемент таблицы стилей
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как отформатировать элемент таблицы с помощью Aspose.PDF для .NET. Пошаговое руководство по настройке стилей и свойств.
type: docs
weight: 170
url: /ru/net/programming-with-tagged-pdf/style-table-element/
---
В этом подробном руководстве мы шаг за шагом проведем вас через предоставленный исходный код C#, чтобы отформатировать элемент массива с помощью Aspose.PDF для .NET. Следуйте приведенным ниже инструкциям, чтобы понять, как настроить стили и свойства элемента массива.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2: Создание документа

На этом шаге мы создадим новый объект документа Aspose.PDF.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Мы создали новый документ и установили название документа и язык.

## Шаг 3: Получение элемента корневой структуры

На этом шаге мы получим элемент корневой структуры для нашего документа.

```csharp
//Получить элемент корневой структуры
StructureElement rootElement = taggedContent.RootElement;
```

Мы получили элемент корневой структуры, который будет служить контейнером для элемента массива.

## Шаг 4: Создание элемента структуры массива

Теперь давайте создадим новый элемент структуры таблицы для нашего документа.

```csharp
// Создайте элемент структуры массива
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Мы создали новый элемент структуры массива и добавили его в корневой элемент структуры.

## Шаг 5: Настройка стилей и свойств элементов массива

На этом шаге мы настроим стили и свойства элемента массива.

```csharp
// Настройте стили и свойства элемента массива
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Настройка стиля повторяющихся линий
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Мы использовали различные свойства для настройки элемента таблицы, такие как цвет фона, границы, выравнивание, стиль ячейки по умолчанию, поля, ширина столбца и т. д.

## Шаг 6: Добавьте заголовки, тело и нижний колонтитул таблицы

Теперь давайте добавим заголовки, тело и нижний колонтитул таблицы к элементу таблицы.
```csharp
// Добавить заголовки таблицы
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Количество строк и столбцов в таблице
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Создайте строку заголовка таблицы
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Добавьте строки тела таблицы
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Добавьте нижнюю линию таблицы
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Мы добавили в таблицу заголовки, строки тела и строку нижнего колонтитула, используя соответствующие элементы.

## Шаг 7: Сохранение документа PDF с тегами

Теперь, когда мы создали наш документ со стилизованным элементом таблицы, мы сохраним его как PDF-документ с тегами.

```csharp
// Сохраните документ PDF с тегами
document.Save(dataDir + "StyleTableElement.pdf");
```

Мы сохранили помеченный PDF-документ в указанном каталоге.

## Шаг 8. Проверка соответствия PDF/UA

Далее мы проверим соответствие PDF/UA нашего документа.

```csharp
// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Мы загрузили документ PDF с тегами и проверили его соответствие формату PDF/UA, создав отчет XML.

### Пример исходного кода для элемента таблицы стилей с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Получить элемент корневой структуры
StructureElement rootElement = taggedContent.RootElement;

// Создать элемент структуры таблицы
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "StyleTableElement.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом руководстве мы узнали, как отформатировать элемент массива с помощью Aspose.PDF для .NET. Мы настроили стили и свойства элемента таблицы, добавили заголовки, основные строки и нижний колонтитул, сохранили документ PDF с тегами и проверили его соответствие формату PDF/UA.

### Часто задаваемые вопросы

#### В: Какова цель этого руководства по форматированию элемента массива с помощью Aspose.PDF для .NET?

О: Цель этого руководства — провести вас через процесс форматирования элемента массива в документе PDF с помощью Aspose.PDF для .NET. Он содержит пошаговые инструкции и примеры исходного кода C#, которые помогут вам настроить стили и свойства элемента массива.

#### В: Каковы предварительные условия для прохождения этого руководства?

О: Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

#### В: Как я могу создать новый PDF-документ и установить его название и язык, используя Aspose.PDF для .NET?

 О: Чтобы создать новый документ PDF, вам необходимо создать`Document` объект из библиотеки Aspose.PDF. Предоставленный в руководстве исходный код C# демонстрирует, как создать документ и установить его заголовок и языковые свойства.

#### В: Каково значение элемента корневой структуры в документе PDF?

О: Элемент корневой структуры выступает в качестве контейнера для других элементов структуры, помогая организовать и классифицировать содержимое документа PDF. Он играет решающую роль в установлении логической структуры документа.

#### В: Как создать и настроить элемент структуры массива с помощью Aspose.PDF для .NET?

 A: Вы можете создать элемент структуры массива с помощью`CreateTableElement()` метод. Исходный код руководства содержит примеры настройки различных свойств элемента таблицы, таких как цвет фона, границы, выравнивание, ширина столбца и т. д.

#### Вопрос. Можно ли настроить стили и свойства ячеек таблицы в элементе массива?

О: Да, в этом руководстве рассказывается, как настроить стили и свойства всего элемента таблицы, включая заголовки, основные строки и нижний колонтитул. Однако в нем конкретно не рассматривается настройка отдельных ячеек таблицы.

#### Вопрос. Как добавить заголовки, основные строки и нижний колонтитул к элементу таблицы?

О: В этом руководстве объясняется, как создавать и добавлять заголовки, основные строки и нижний колонтитул к элементу таблицы с помощью соответствующих методов, предоставляемых Aspose.PDF для .NET.

#### Вопрос. Что такое соответствие требованиям PDF/UA и как я могу проверить его для своего PDF-документа с тегами?

 О: Соответствие PDF/UA гарантирует, что PDF-документ соответствует стандартам специальных возможностей, что делает его более доступным для пользователей с ограниченными возможностями. В этом руководстве показано, как проверить соответствие PDF/UA с помощью`Validate()` метод и создать отчет о соответствии XML.

#### Вопрос: Как я могу включить эти концепции в свои собственные приложения .NET?

О: Вы можете использовать предоставленные примеры исходного кода C# в качестве руководства по реализации форматирования элементов массива в ваших собственных приложениях .NET. Измените и адаптируйте код в соответствии с вашими требованиями и интегрируйте его в свои проекты.

#### Вопрос: Существуют ли какие-либо рекомендации по форматированию элементов массива в документах PDF?

О: При форматировании элементов массива (таблиц) учитывайте удобочитаемость и доступность содержимого. Используйте четкие и разборчивые шрифты, подходящие цвета и поддерживайте единообразный макет. Подтвердите соответствие PDF/UA, чтобы обеспечить соблюдение стандартов доступности.

#### В: Какие еще функции Aspose.PDF для .NET можно использовать для настройки PDF-документа?

О: Aspose.PDF для .NET предлагает ряд функций для настройки PDF-документа, включая работу с текстом, вставку изображений, управление полями формы, цифровые подписи, аннотации и многое другое. Обратитесь к официальной документации и ресурсам, чтобы изучить дополнительные функции.