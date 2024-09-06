---
title: Создать элемент таблицы
linktitle: Создать элемент таблицы
second_title: Справочник по API Aspose.PDF для .NET
description: Пошаговое руководство по созданию элемента массива с помощью Aspose.PDF для .NET. Легко создавайте динамические PDF-файлы с таблицами.
type: docs
weight: 80
url: /ru/net/programming-with-tagged-pdf/create-table-element/
---
В этом пошаговом руководстве мы проведем вас через процесс создания элемента массива с помощью Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет вам программно манипулировать документами PDF. Создание элемента массива — это распространенное требование при создании динамических PDF-файлов, и Aspose.PDF предлагает простой и эффективный способ сделать это.

Давайте углубимся в код и узнаем, как создать элемент массива с помощью Aspose.PDF для .NET.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Установлена библиотека Aspose.PDF для .NET.
2. Базовые знания языка программирования C#.

## Шаг 1: Настройка среды

Чтобы начать, откройте среду разработки C# и создайте новый проект. Убедитесь, что вы добавили ссылку на библиотеку Aspose.PDF для .NET в свой проект.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа

 Первый шаг — создать новый PDF-документ с помощью`Document` сорт.

```csharp
// Создать документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Здесь мы также задаем заголовок и язык для помеченного контента.

## Шаг 3: Создание элемента массива

Далее нам нужно создать элемент массива и добавить его в документ. Мы начинаем с получения корневого элемента структуры, затем создаем новый элемент таблицы с помощью`CreateTableElement` метод.

```csharp
// Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Сохраните помеченный PDF-документ
document.Save(dataDir + "CreateTableElement.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Пример исходного кода для создания элемента таблицы с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Сохранить помеченный PDF-документ
document.Save(dataDir + "CreateTableElement.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

Вы узнали, как создать элемент массива с помощью Aspose.PDF для .NET. Теперь вы можете создавать PDF-документы с динамическими таблицами, используя этот метод. Не стесняйтесь изучать больше возможностей Aspose.PDF, чтобы раскрыть его полный потенциал.

### Часто задаваемые вопросы

#### В: Что такое элемент массива в документе PDF и зачем мне его создавать с помощью Aspose.PDF для .NET?

A: Элемент массива в документе PDF представляет собой структурированную коллекцию данных, часто используемую для создания таблиц или сеток. Вам может потребоваться создать элемент массива с помощью Aspose.PDF для .NET при создании динамических PDF-файлов, требующих структурированного представления данных, например табличной информации или сеток.

#### В: Как Aspose.PDF для .NET упрощает процесс создания элемента массива?

A: Aspose.PDF для .NET предоставляет полный набор классов и методов, которые позволяют вам создавать, настраивать и управлять элементами массива (таблицами) в документе PDF программным способом. Это устраняет необходимость в ручном манипулировании PDF и упрощает создание структурированных представлений данных.

#### В: Каковы основные этапы создания элемента массива с использованием Aspose.PDF для .NET?

A: Основные шаги включают настройку среды, создание документа, получение корневого элемента структуры, создание элемента таблицы, определение строк и ячеек в таблице и указание форматирования и свойств для элементов. Приведенный пример кода демонстрирует эти шаги.

####  В: Какую роль играет`taggedContent` object play in creating an array element?

 А:`taggedContent` объект, полученный из документа`TaggedContent`свойство, позволяет вам определить структуру тегированного содержимого в документе PDF. Это включает в себя создание и организацию элементов массива и их дочерних элементов в иерархическом порядке.

#### В: Каким образом код обеспечивает доступность и семантику созданного элемента массива?

 A: Код устанавливает такие атрибуты, как`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , и`ColSpan` для улучшения доступности и семантики элемента массива. Эти атрибуты способствуют хорошо структурированному, информативному и визуально привлекательному представлению данных.

#### В: Каково значение соответствия PDF/UA в контексте создания элементов массива?

 A: Соответствие PDF/UA (Universal Accessibility) гарантирует, что сгенерированные PDF-документы доступны для пользователей с ограниченными возможностями и соответствуют определенным стандартам доступности. Пример кода проверяет соответствие PDF/UA с помощью`Validate` метод, помогающий вам создавать инклюзивные и доступные документы.

#### В: Могу ли я дополнительно настроить форматирование и внешний вид элементов массива?

A: Да, вы можете настроить форматирование и внешний вид элементов массива, настроив такие атрибуты, как цвет фона, стиль границы, размер шрифта и выравнивание. Aspose.PDF для .NET предоставляет широкий спектр свойств для адаптации визуального представления к вашим требованиям.

#### В: Как я могу расширить эти знания, чтобы создавать более сложные структуры таблиц или включать элементы массива в более крупные PDF-документы?

A: Вы можете расширить эти знания, изучив дополнительные возможности Aspose.PDF для .NET, такие как слияние нескольких элементов массива, создание вложенных таблиц, добавление верхних и нижних колонтитулов и интеграция элементов массива в более крупные макеты PDF. Документация и примеры библиотеки предоставляют руководство для этих расширенных сценариев.

#### В: Можно ли импортировать данные из внешних источников, таких как базы данных или электронные таблицы, для заполнения элементов массива?

A: Да, вы можете импортировать данные из внешних источников для заполнения элементов массива. Вы можете использовать методы извлечения и преобразования данных в C# для извлечения данных из баз данных, электронных таблиц или других источников, а затем заполнять элементы массива соответствующим образом.

#### В: Как я могу использовать знания, полученные в этом руководстве, для повышения качества и удобства использования PDF-документов, которые я создаю программным способом?

A: Знания, полученные в этом руководстве, позволяют вам создавать структурированные и визуально привлекательные элементы массива (таблицы) в документах PDF. Внедряя эти методы, вы можете улучшить читаемость, доступность и пользовательский опыт динамически генерируемых PDF-файлов, делая их более информативными и удобными для пользователя.