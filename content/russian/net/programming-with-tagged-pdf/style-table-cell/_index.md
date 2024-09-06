---
title: Стиль ячейки таблицы
linktitle: Стиль ячейки таблицы
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как стилизовать ячейки таблиц с помощью Aspose.PDF для .NET. Пошаговое руководство по созданию и настройке таблиц.
type: docs
weight: 160
url: /ru/net/programming-with-tagged-pdf/style-table-cell/
---
Добро пожаловать в этот подробный урок по форматированию ячеек таблицы с помощью Aspose.PDF для .NET. В этом руководстве мы подробно объясним каждый шаг предоставленного исходного кода C#, чтобы помочь вам понять, как стилизовать ячейки таблицы. Убедитесь, что вы установили Aspose.PDF для .NET и настроили среду разработки, прежде чем начать.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Мы создали новый документ и задали его название и язык.

## Шаг 3: Получение корневого структурного элемента

На этом этапе мы получим корневой элемент структуры для нашего документа.

```csharp
//Получить корневой структурный элемент
StructureElement rootElement = taggedContent.RootElement;
```

Мы получили корневой элемент структуры, который будет служить контейнером для элементов массива.

## Шаг 4: Создание элемента структуры массива

Теперь давайте создадим новый элемент структуры таблицы для нашего документа.

```csharp
// Создать элемент структуры массива
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Мы создали новый элемент структуры массива и добавили его к корневому элементу структуры. Мы также создали элементы заголовка, тела и нижнего колонтитула таблицы.

## Шаг 5: Добавление заголовков таблицы

На этом этапе мы добавим заголовки в нашу таблицу.

```csharp
// Количество строк и столбцов в таблице
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Создайте строку заголовка таблицы
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Мы создали строку заголовка для нашей таблицы и добавили ячейки заголовка со свойствами форматирования, такими как цвет фона, границы, поля и выравнивание.

## Шаг 6: Добавление строк тела таблицы

Теперь давайте добавим строки тела таблицы в нашу таблицу.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Мы добавили строки в тело таблицы, используя циклы для итерации по каждой ячейке таблицы. Мы установили свойства форматирования для каждой ячейки, такие как цвет фона, границы, поля, выравнивание текста и т. д.

## Шаг 7: Добавление нижнего колонтитула

Наконец, мы добавим к нашей таблице нижний колонтитул.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Мы создали нижний колонтитул для нашей таблицы и добавили ячейки нижнего колонтитула с текстом.



## Шаг 8: Сохранение помеченного PDF-документа

Теперь, когда мы создали документ со стилизованной таблицей, мы сохраним его как тегированный PDF-документ.

```csharp
// Сохраните помеченный PDF-документ
document.Save(dataDir + "StyleTableCell.pdf");
```

Мы сохранили помеченный PDF-документ в указанном каталоге.

## Шаг 9: Проверка соответствия PDF/UA

Далее мы проверим соответствие нашего документа формату PDF/UA.

```csharp
// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Мы загрузили помеченный PDF-документ и проверили его соответствие PDF/UA, создав XML-отчет.

### Пример исходного кода для ячейки таблицы стилей с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;

// Создать элемент структуры таблицы
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом уроке мы узнали, как стилизовать ячейки таблицы с помощью Aspose.PDF для .NET. Мы увидели, как создать документ, добавить таблицу с заголовками, строками тела и нижним колонтитулом, а также настроить стили ячеек. Наконец, мы сохранили помеченный PDF-документ и проверили его соответствие PDF/UA. Теперь вы можете использовать Aspose.PDF для .NET для создания и стилизации таблиц в своих приложениях .NET.

### Часто задаваемые вопросы

#### В: Какова цель этого руководства по форматированию ячеек таблицы с помощью Aspose.PDF для .NET?

A: Цель этого руководства — предоставить исчерпывающее руководство по стилю ячеек таблиц в документе PDF с использованием библиотеки Aspose.PDF для .NET. Оно содержит пошаговые инструкции и примеры исходного кода C#, которые помогут вам понять и реализовать форматирование ячеек таблиц.

#### В: Каковы предварительные условия для прохождения этого урока?

A: Прежде чем начать, убедитесь, что вы установили Aspose.PDF для .NET и настроили среду разработки. Это включает в себя настройку вашего проекта для ссылки на библиотеку Aspose.PDF.

#### В: Как создать новый PDF-документ с помощью Aspose.PDF для .NET?

A: Чтобы создать новый PDF-документ, вам необходимо создать экземпляр`Document` объект из библиотеки Aspose.PDF. Предоставленный исходный код C# демонстрирует, как создать документ и задать его заголовок и язык.

#### В: Каково значение корневого элемента структуры в PDF-документе?

A: Элемент корневой структуры служит контейнером для других элементов структуры, помогая организовать и классифицировать содержимое документа PDF. Он играет решающую роль в установлении логической структуры документа.

#### В: Как создать элемент структуры таблицы и настроить его внешний вид с помощью Aspose.PDF для .NET?

 A: Вы можете создать элемент структуры таблицы, используя`CreateTableElement()` метод. Предоставленный исходный код демонстрирует, как настроить внешний вид таблицы, включая ее заголовок, тело и нижний колонтитул, задав такие свойства, как цвет фона, границы, поля и выравнивание.

#### В: Могу ли я добавить несколько строк и столбцов в тело таблицы и настроить их форматирование?

A: Да, в руководстве показано, как добавлять несколько строк и столбцов в тело таблицы с помощью циклов. Также в нем приведены примеры настройки форматирования ячеек, например, цвет фона, границы, выравнивание текста, стиль шрифта и многое другое.

#### В: Какова цель проверки соответствия PDF/UA и как я могу выполнить эту проверку?

 A: Проверка соответствия PDF/UA гарантирует, что документ PDF соответствует стандартам доступности, что делает его более доступным для пользователей с ограниченными возможностями. В руководстве показано, как проверить соответствие PDF/UA с помощью`Validate()` метод и сгенерировать XML-отчет.

#### В: Как я могу применить эти концепции к своим собственным приложениям .NET?

A: Вы можете использовать предоставленные примеры исходного кода C# в качестве руководства по реализации форматирования ячеек таблиц в ваших собственных приложениях .NET. Настройте код по мере необходимости в соответствии с вашими требованиями и интегрируйте его в свои проекты.

#### В: Существуют ли какие-либо рекомендуемые методы стилизации ячеек таблиц в PDF-документах?

A: При оформлении ячеек таблицы учитывайте потребности вашей аудитории, включая требования доступности. Используйте контрастные цвета, соответствующие шрифты и четкое выравнивание ячеек для улучшения читаемости. Кроме того, проверьте соответствие PDF/UA, чтобы убедиться в соблюдении стандартов доступности.

#### В: Какие еще функции Aspose.PDF для .NET я могу использовать для работы с PDF-документами?

A: Aspose.PDF для .NET предлагает широкий спектр функций для обработки PDF-документов, включая извлечение текста, вставку изображений, управление полями форм, цифровые подписи и многое другое. Изучите официальную документацию и ресурсы, чтобы узнать о дополнительных функциях.
