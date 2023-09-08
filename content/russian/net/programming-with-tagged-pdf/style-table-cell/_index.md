---
title: Ячейка таблицы стилей
linktitle: Ячейка таблицы стилей
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как стилизовать ячейки таблицы с помощью Aspose.PDF для .NET. Пошаговое руководство по созданию и настройке таблиц.
type: docs
weight: 160
url: /ru/net/programming-with-tagged-pdf/style-table-cell/
---
Добро пожаловать в это подробное руководство по форматированию ячеек таблицы с использованием Aspose.PDF для .NET. В этом руководстве мы подробно объясним каждый шаг предоставленного исходного кода C#, чтобы помочь вам понять, как стилизовать ячейки таблицы. Прежде чем начать, убедитесь, что вы установили Aspose.PDF для .NET и настроили среду разработки.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2. Создание документа

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

Мы создали новый документ и установили заголовок и язык документа.

## Шаг 3: Получение корневого элемента структуры

На этом этапе мы получим корневой элемент структуры для нашего документа.

```csharp
//Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;
```

Мы получили корневой элемент структуры, который будет служить контейнером для элементов массива.

## Шаг 4: Создание элемента структуры массива

Теперь давайте создадим новый элемент структуры таблицы для нашего документа.

```csharp
// Создайте элемент структуры массива
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Мы создали новый элемент структуры массива и добавили его в корневой элемент структуры. Мы также создали элементы заголовка, тела и нижнего колонтитула таблицы.

## Шаг 5. Добавление заголовков таблиц

На этом этапе мы добавим заголовки таблиц в нашу таблицу.

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

## Шаг 6. Добавление строк тела таблицы

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

Мы добавили строки в тело таблицы, используя циклы для обхода каждой ячейки таблицы. Мы устанавливаем свойства форматирования для каждой ячейки, такие как цвет фона, границы, поля, выравнивание текста и т. д.

## Шаг 7: Добавляем нижний колонтитул

Наконец, мы добавим нижний колонтитул к нашей таблице.

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



## Шаг 8. Сохранение PDF-документа с тегами

Теперь, когда мы создали документ со стилизованной таблицей, мы сохраним его как PDF-документ с тегами.

```csharp
// Сохраните PDF-документ с тегами
document.Save(dataDir + "StyleTableCell.pdf");
```

Мы сохранили PDF-документ с тегами в указанном каталоге.

## Шаг 9. Проверка соответствия PDF/UA

Далее мы проверим соответствие нашего документа PDF/UA.

```csharp
// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Мы загрузили PDF-документ с тегами и проверили его соответствие PDF/UA, создав отчет XML.

### Пример исходного кода для ячейки таблицы стилей с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Получить элемент корневой структуры
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

// Сохранить PDF-документ с тегами
document.Save(dataDir + "StyleTableCell.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом уроке мы узнали, как стилизовать ячейки таблицы с помощью Aspose.PDF для .NET. Мы увидели, как создать документ, добавить таблицу с заголовками, строками основного текста и нижним колонтитулом, а также настроить стили ячеек. Наконец, мы сохранили PDF-документ с тегами и проверили его соответствие PDF/UA. Теперь вы можете использовать Aspose.PDF для .NET для создания и стилизации таблиц в ваших .NET-приложениях.

### Часто задаваемые вопросы

#### Вопрос: Какова цель этого руководства по форматированию ячеек таблицы с помощью Aspose.PDF для .NET?

О: Целью данного руководства является предоставление подробного руководства по стилизации ячеек таблицы в PDF-документе с использованием библиотеки Aspose.PDF для .NET. Он содержит пошаговые инструкции и примеры исходного кода C#, которые помогут вам понять и реализовать форматирование ячеек таблицы.

#### Вопрос: Каковы необходимые условия для изучения этого руководства?

О: Прежде чем начать, убедитесь, что вы установили Aspose.PDF для .NET и настроили среду разработки. Это включает в себя настройку вашего проекта для ссылки на библиотеку Aspose.PDF.

#### Вопрос: Как создать новый PDF-документ с помощью Aspose.PDF для .NET?

О: Чтобы создать новый PDF-документ, вам необходимо создать экземпляр`Document` объект из библиотеки Aspose.PDF. Приведенный исходный код C# демонстрирует, как создать документ и установить его заголовок и язык.

#### Вопрос: Каково значение элемента корневой структуры в PDF-документе?

Ответ: Элемент корневой структуры служит контейнером для других элементов структуры, помогая организовать и классифицировать содержимое PDF-документа. Он играет решающую роль в установлении логической структуры документа.

#### Вопрос: Как создать элемент структуры таблицы и настроить его внешний вид с помощью Aspose.PDF для .NET?

 О: Создать элемент структуры таблицы можно с помощью`CreateTableElement()` метод. Предоставленный исходный код демонстрирует, как настроить внешний вид таблицы, включая ее верхний, основной и нижний колонтитулы, путем установки таких свойств, как цвет фона, границы, поля и выравнивание.

#### Вопрос: Могу ли я добавить в тело таблицы несколько строк и столбцов и настроить их форматирование?

О: Да, в руководстве показано, как добавить несколько строк и столбцов в тело таблицы с помощью циклов. Он также предоставляет примеры настройки форматирования ячеек, таких как цвет фона, границы, выравнивание текста, стиль шрифта и многое другое.

#### Вопрос: Какова цель проверки соответствия PDF/UA и как я могу выполнить эту проверку?

 Ответ: Проверка соответствия PDF/UA гарантирует, что документ PDF соответствует стандартам доступности, что делает его более доступным для пользователей с ограниченными возможностями. В этом руководстве показано, как проверить соответствие PDF/UA с помощью`Validate()` метод и сгенерируйте отчет XML.

#### Вопрос: Как я могу применить эти концепции к своим собственным .NET-приложениям?

О: Вы можете использовать предоставленные примеры исходного кода C# в качестве руководства по реализации форматирования ячеек таблицы в ваших собственных .NET-приложениях. Настройте код по мере необходимости в соответствии с вашими требованиями и интегрируйте его в свои проекты.

#### Вопрос: Существуют ли какие-либо рекомендации по стилизации ячеек таблицы в документах PDF?

Ответ: При оформлении ячеек таблицы учитывайте потребности своей аудитории, включая требования к доступности. Используйте контрастные цвета, подходящие шрифты и четкое выравнивание ячеек, чтобы улучшить читабельность. Кроме того, проверьте соответствие PDF/UA, чтобы обеспечить соблюдение стандартов доступности.

#### Вопрос: Какие еще возможности Aspose.PDF for .NET я могу изучить для манипулирования PDF-документами?

О: Aspose.PDF для .NET предлагает широкий спектр функций для манипулирования PDF-документами, включая извлечение текста, вставку изображений, управление полями формы, цифровые подписи и многое другое. Изучите официальную документацию и ресурсы, чтобы узнать о дополнительных функциях.
