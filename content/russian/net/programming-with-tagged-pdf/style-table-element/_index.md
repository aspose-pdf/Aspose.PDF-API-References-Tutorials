---
title: Элемент таблицы стилей
linktitle: Элемент таблицы стилей
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как форматировать элемент таблицы с помощью Aspose.PDF для .NET. Пошаговое руководство по настройке стилей и свойств.
type: docs
weight: 170
url: /ru/net/programming-with-tagged-pdf/style-table-element/
---
В этом подробном руководстве мы шаг за шагом проведем вас через предоставленный исходный код C#, чтобы отформатировать элемент массива с помощью Aspose.PDF для .NET. Следуйте инструкциям ниже, чтобы понять, как настраивать стили и свойства элемента массива.

## Шаг 1: Настройка среды

Прежде чем начать, убедитесь, что вы настроили среду разработки для использования Aspose.PDF для .NET. Это включает установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2: Создание документа

На этом этапе мы создадим новый объект документа Aspose.PDF.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Мы создали новый документ и задали его название и язык.

## Шаг 3: Получение корневого структурного элемента

На этом этапе мы получим корневой элемент структуры для нашего документа.

```csharp
// Получить корневой структурный элемент
StructureElement rootElement = taggedContent.RootElement;
```

Мы получили корневой элемент структуры, который будет служить контейнером для элемента массива.

## Шаг 4: Создание элемента структуры массива

Теперь давайте создадим новый элемент структуры таблицы для нашего документа.

```csharp
// Создать элемент структуры массива
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Мы создали новый элемент структуры массива и добавили его к корневому элементу структуры.

## Шаг 5: Настройка стилей и свойств элементов массива

На этом этапе мы настроим стили и свойства элемента массива.

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

// Настройте стиль повторяющихся строк
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Мы использовали различные свойства для настройки элемента таблицы, такие как цвет фона, границы, выравнивание, стиль ячеек по умолчанию, поля, ширина столбца и т. д.

## Шаг 6: Добавьте заголовки, текст и нижний колонтитул таблицы.

Теперь добавим заголовки, тело и нижний колонтитул таблицы к элементу таблицы.
```csharp
// Добавить заголовки таблиц
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

//Добавьте строки тела таблицы.
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

// Добавьте линию основания стола.
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Мы добавили в таблицу заголовки, основные строки и строку нижнего колонтитула, используя соответствующие элементы.

## Шаг 7: Сохранение помеченного PDF-документа

Теперь, когда мы создали наш документ со стилизованным элементом таблицы, мы сохраним его как тегированный PDF-документ.

```csharp
// Сохраните помеченный PDF-документ
document.Save(dataDir + "StyleTableElement.pdf");
```

Мы сохранили помеченный PDF-документ в указанном каталоге.

## Шаг 8: Проверка соответствия PDF/UA

Далее мы проверим соответствие нашего документа формату PDF/UA.

```csharp
// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Мы загрузили помеченный PDF-документ и проверили его соответствие PDF/UA, создав XML-отчет.

### Пример исходного кода для элемента таблицы стилей с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Получить корневой элемент структуры
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

// Сохранить помеченный PDF-документ
document.Save(dataDir + "StyleTableElement.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом уроке мы узнали, как форматировать элемент массива с помощью Aspose.PDF для .NET. Мы настроили стили и свойства элемента таблицы, добавили заголовки, строки тела и нижний колонтитул, сохранили помеченный PDF-документ и проверили его соответствие PDF/UA.

### Часто задаваемые вопросы

#### В: Какова цель этого руководства по форматированию элемента массива с помощью Aspose.PDF для .NET?

A: Цель этого руководства — провести вас через процесс форматирования элемента массива в документе PDF с помощью Aspose.PDF для .NET. Оно предоставляет пошаговые инструкции и примеры исходного кода C#, которые помогут вам настроить стили и свойства элемента массива.

#### В: Каковы предварительные условия для прохождения этого урока?

A: Перед началом убедитесь, что вы настроили среду разработки для использования Aspose.PDF для .NET. Это включает установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

#### В: Как создать новый PDF-документ и задать его заголовок и язык с помощью Aspose.PDF для .NET?

 A: Чтобы создать новый PDF-документ, вам необходимо создать`Document` объект из библиотеки Aspose.PDF. Исходный код C#, предоставленный в учебнике, демонстрирует, как создать документ и задать его заголовок и языковые свойства.

#### В: Каково значение корневого элемента структуры в PDF-документе?

A: Элемент корневой структуры действует как контейнер для других элементов структуры, помогая организовать и категоризировать содержимое документа PDF. Он играет решающую роль в установлении логической структуры документа.

#### В: Как создать и настроить элемент структуры массива с помощью Aspose.PDF для .NET?

 A: Вы можете создать элемент структуры массива, используя`CreateTableElement()` метод. Исходный код учебника содержит примеры настройки различных свойств элемента таблицы, таких как цвет фона, границы, выравнивание, ширина столбца и многое другое.

#### В: Могу ли я настраивать стили и свойства ячеек таблицы внутри элемента массива?

A: Да, в руководстве рассматривается, как настраивать стили и свойства всего элемента таблицы, включая заголовки, строки тела и нижний колонтитул. Однако в нем не рассматривается настройка отдельных ячеек таблицы.

#### В: Как добавить заголовки, строки тела и нижний колонтитул к элементу таблицы?

A: В руководстве объясняется, как создавать и добавлять заголовки, строки тела и нижний колонтитул к элементу таблицы, используя соответствующие методы, предоставляемые Aspose.PDF для .NET.

#### В: Что такое соответствие стандарту PDF/UA и как я могу проверить его для моего помеченного PDF-документа?

 A: Соответствие PDF/UA гарантирует, что документ PDF соответствует стандартам доступности, что делает его более доступным для пользователей с ограниченными возможностями. В руководстве показано, как проверить соответствие PDF/UA с помощью`Validate()` метод и сформировать отчет о соответствии XML.

#### В: Как я могу включить эти концепции в свои собственные приложения .NET?

A: Вы можете использовать предоставленные примеры исходного кода C# в качестве руководства по реализации форматирования элементов массива в ваших собственных приложениях .NET. Измените и адаптируйте код в соответствии с вашими требованиями и интегрируйте его в свои проекты.

#### В: Существуют ли какие-либо рекомендуемые методы форматирования элементов массива в PDF-документах?

A: При форматировании элементов массива (таблиц) учитывайте читаемость и доступность контента. Используйте четкие и разборчивые шрифты, соответствующие цвета и поддерживайте единообразную компоновку. Проверьте соответствие PDF/UA, чтобы гарантировать соблюдение стандартов доступности.

#### В: Какие еще функции Aspose.PDF для .NET я могу изучить для настройки PDF-документов?

A: Aspose.PDF для .NET предлагает ряд функций для настройки PDF-документов, включая обработку текста, вставку изображений, управление полями форм, цифровые подписи, аннотации и многое другое. Ознакомьтесь с официальной документацией и ресурсами, чтобы изучить дополнительные функции.