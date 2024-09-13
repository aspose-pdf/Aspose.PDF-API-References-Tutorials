---
title: Стиль строки таблицы
linktitle: Стиль строки таблицы
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как настраивать строки таблицы с помощью пошагового руководства Aspose.PDF для .NET по стилю и форматированию строк.
type: docs
weight: 180
url: /ru/net/programming-with-tagged-pdf/style-table-row/
---
В этом подробном руководстве мы шаг за шагом проведем вас через предоставленный исходный код C#, чтобы отформатировать строку таблицы с помощью Aspose.PDF для .NET. Следуйте инструкциям ниже, чтобы понять, как настраивать стили и свойства строк таблицы.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Шаг 5: Настройте стили и свойства строк таблицы

На этом этапе мы настроим стили и свойства строк таблицы.

```csharp
// Настройте стили и свойства строк таблицы
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Настройте строки тела таблицы
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Создайте строку нижнего колонтитула таблицы
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Мы настроили различные аспекты строки таблицы, такие как цвет фона, границы, высоту строки, нумерацию страниц, стиль ячеек по умолчанию и многое другое.

## Шаг 6: Сохранение помеченного PDF-документа

Теперь, когда мы создали документ со стилизованной строкой таблицы, мы сохраним его как тегированный PDF-документ.
```csharp
// Сохраните помеченный PDF-документ
document.Save(dataDir + "StyleTableRow.pdf");
```

Мы сохранили помеченный PDF-документ в указанном каталоге.

## Шаг 7: Проверка соответствия PDF/UA

Далее мы проверим соответствие нашего документа формату PDF/UA.

```csharp
// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Мы загрузили помеченный PDF-документ и проверили его соответствие PDF/UA, создав XML-отчет.


### Пример исходного кода для строки таблицы стилей с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;

// Создать элемент структуры таблицы
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом уроке мы узнали, как форматировать строку таблицы с помощью Aspose.PDF для .NET. Мы настроили стили и свойства строки таблицы, добавили заголовки, строки тела и нижний колонтитул, сохранили помеченный PDF-документ и проверили его соответствие PDF/UA.

### Часто задаваемые вопросы

#### В: Какова цель этого руководства по форматированию строк таблицы с помощью Aspose.PDF для .NET?

A: Цель этого руководства — провести вас через процесс форматирования строк таблицы в документе PDF с помощью Aspose.PDF для .NET. Оно предоставляет пошаговые инструкции и примеры исходного кода C#, которые помогут вам настроить стили и свойства строк таблицы.

#### В: Каковы предварительные условия для прохождения этого урока?

A: Перед началом убедитесь, что вы настроили среду разработки для использования Aspose.PDF для .NET. Это включает установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

#### В: Как создать новый PDF-документ и задать его заголовок и язык с помощью Aspose.PDF для .NET?

 A: Чтобы создать новый PDF-документ, вам необходимо создать`Document` объект из библиотеки Aspose.PDF. Исходный код C#, предоставленный в учебнике, демонстрирует, как создать документ и задать его заголовок и языковые свойства.

#### В: Каково значение корневого элемента структуры в PDF-документе?

A: Элемент корневой структуры действует как контейнер для других элементов структуры, помогая организовать и категоризировать содержимое документа PDF. Он играет решающую роль в установлении логической структуры документа.

#### В: Как создать и настроить элемент структуры таблицы для форматирования строк таблицы с помощью Aspose.PDF для .NET?

A: В руководстве объясняется, как создать элемент структуры таблицы и настроить его свойства для форматирования строк таблицы. Оно охватывает такие аспекты, как цвет фона, границы, высота строки, нумерация страниц, стиль ячейки по умолчанию и многое другое.

#### В: Могу ли я настраивать стили и свойства отдельных ячеек в строке таблицы?

A: Да, вы можете настраивать стили и свойства отдельных ячеек в строке таблицы. В руководстве показано, как задать такие свойства, как цвет фона, границы, цвет текста, отступы и многое другое для ячеек таблицы в отформатированной строке таблицы.

#### В: Как добавить заголовки, основные строки и нижний колонтитул в отформатированную строку таблицы?

A: В руководстве приведены примеры создания и добавления заголовков, строк тела и нижнего колонтитула к элементу структуры таблицы. Эти элементы можно дополнительно настроить с помощью свойств, описанных в руководстве.

#### В: Что такое соответствие стандарту PDF/UA и как я могу проверить его для моего помеченного PDF-документа?

 A: Соответствие PDF/UA гарантирует, что документ PDF соответствует стандартам доступности, что делает его более доступным для пользователей с ограниченными возможностями. В руководстве показано, как проверить соответствие PDF/UA с помощью`Validate()` метод и сформировать отчет о соответствии XML.

#### В: Как я могу включить эти концепции в свои собственные приложения .NET?

A: Вы можете использовать предоставленные примеры исходного кода C# в качестве руководства по реализации форматирования строк таблиц в ваших собственных приложениях .NET. Измените и адаптируйте код в соответствии с вашими требованиями и интегрируйте его в свои проекты.

#### В: Существуют ли какие-либо рекомендуемые методы форматирования строк таблиц в PDF-документах?

A: При форматировании строк таблицы учитывайте читаемость и доступность контента. Убедитесь, что цвета достаточно контрастны, используйте четкие и разборчивые шрифты и поддерживайте единообразную компоновку. Проверьте соответствие PDF/UA, чтобы убедиться в соблюдении стандартов доступности.

#### В: Какие еще функции Aspose.PDF для .NET я могу изучить для настройки PDF-документов?

A: Aspose.PDF для .NET предлагает широкий спектр функций для настройки PDF-документов, включая обработку текста, вставку изображений, управление полями форм, цифровые подписи, аннотации и многое другое. Ознакомьтесь с официальной документацией и ресурсами, чтобы изучить дополнительные функции.