---
title: Строка таблицы стилей
linktitle: Строка таблицы стилей
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как настраивать строки таблицы с помощью Aspose.PDF для .NET. Пошаговое руководство по стилю и форматированию строк.
type: docs
weight: 180
url: /ru/net/programming-with-tagged-pdf/style-table-row/
---
В этом подробном руководстве мы шаг за шагом проведем вас через предоставленный исходный код C#, чтобы отформатировать строку таблицы с помощью Aspose.PDF для .NET. Следуйте приведенным ниже инструкциям, чтобы понять, как настроить стили и свойства строк таблицы.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Шаг 5. Настройте стили и свойства строк таблицы

На этом шаге мы настроим стили и свойства строк таблицы.

```csharp
// Настройка стилей и свойств строк таблицы
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

// Настройка строк тела таблицы
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

Мы настроили различные аспекты строки таблицы, такие как цвет фона, границы, высота строки, нумерация страниц, стиль ячейки по умолчанию и многое другое.

## Шаг 6: Сохранение документа PDF с тегами

Теперь, когда мы создали наш документ со стилизованной строкой таблицы, мы сохраним его как PDF-документ с тегами.
```csharp
// Сохраните документ PDF с тегами
document.Save(dataDir + "StyleTableRow.pdf");
```

Мы сохранили помеченный PDF-документ в указанном каталоге.

## Шаг 7. Проверка соответствия PDF/UA

Далее мы проверим соответствие PDF/UA нашего документа.

```csharp
// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Мы загрузили документ PDF с тегами и проверили его соответствие формату PDF/UA, создав отчет XML.


### Пример исходного кода для строки таблицы стилей с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать документ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Получить элемент корневой структуры
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

// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "StyleTableRow.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом руководстве мы узнали, как форматировать строку таблицы с помощью Aspose.PDF для .NET. Мы настроили стили и свойства строк таблицы, добавили заголовки, основные строки и нижний колонтитул, сохранили документ PDF с тегами и проверили его соответствие формату PDF/UA.

### Часто задаваемые вопросы

#### В: Какова цель этого руководства по форматированию строк таблицы с помощью Aspose.PDF для .NET?

О: Цель этого руководства — провести вас через процесс форматирования строк таблицы в документе PDF с помощью Aspose.PDF для .NET. Он содержит пошаговые инструкции и примеры исходного кода C#, которые помогут вам настроить стили и свойства строк таблицы.

#### В: Каковы предварительные условия для прохождения этого руководства?

О: Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

#### В: Как я могу создать новый PDF-документ и установить его название и язык, используя Aspose.PDF для .NET?

 О: Чтобы создать новый документ PDF, вам необходимо создать`Document` объект из библиотеки Aspose.PDF. Предоставленный в руководстве исходный код C# демонстрирует, как создать документ и установить его заголовок и языковые свойства.

#### В: Каково значение элемента корневой структуры в документе PDF?

О: Элемент корневой структуры выступает в качестве контейнера для других элементов структуры, помогая организовать и классифицировать содержимое документа PDF. Он играет решающую роль в установлении логической структуры документа.

#### Вопрос. Как создать и настроить элемент структуры таблицы для форматирования строк таблицы с помощью Aspose.PDF для .NET?

О: В этом руководстве объясняется, как создать элемент структуры таблицы и настроить его свойства для форматирования строк таблицы. Он охватывает такие аспекты, как цвет фона, границы, высота строки, нумерация страниц, стиль ячейки по умолчанию и многое другое.

#### Вопрос. Можно ли настроить стили и свойства отдельных ячеек в строке таблицы?

О: Да, вы можете настроить стили и свойства отдельных ячеек в строке таблицы. В этом учебнике показано, как задать такие свойства, как цвет фона, границы, цвет текста, отступы и т. д., для ячеек таблицы в отформатированной строке таблицы.

#### Вопрос. Как добавить заголовки, основные строки и нижний колонтитул к отформатированной строке таблицы?

О: В руководстве приведены примеры создания и добавления заголовков, основных строк и нижнего колонтитула к элементу структуры таблицы. Эти элементы можно дополнительно настроить, используя свойства, описанные в руководстве.

#### Вопрос. Что такое соответствие требованиям PDF/UA и как я могу проверить его для своего PDF-документа с тегами?

 О: Соответствие PDF/UA гарантирует, что PDF-документ соответствует стандартам специальных возможностей, что делает его более доступным для пользователей с ограниченными возможностями. В этом руководстве показано, как проверить соответствие PDF/UA с помощью`Validate()` метод и создать отчет о соответствии XML.

#### Вопрос: Как я могу включить эти концепции в свои собственные приложения .NET?

О: Вы можете использовать предоставленные примеры исходного кода C# в качестве руководства по реализации форматирования строк таблицы в ваших собственных приложениях .NET. Измените и адаптируйте код в соответствии с вашими требованиями и интегрируйте его в свои проекты.

#### Вопрос: Существуют ли какие-либо рекомендации по форматированию строк таблицы в документах PDF?

О: При форматировании строк таблицы учитывайте удобочитаемость и доступность содержимого. Убедитесь, что цвета имеют достаточную контрастность, используйте четкие и разборчивые шрифты и поддерживайте единообразие макета. Подтвердите соответствие PDF/UA, чтобы обеспечить соблюдение стандартов доступности.

#### В: Какие еще функции Aspose.PDF для .NET можно использовать для настройки PDF-документа?

О: Aspose.PDF для .NET предлагает широкий спектр функций для настройки PDF-документов, включая работу с текстом, вставку изображений, управление полями форм, цифровые подписи, аннотации и многое другое. Обратитесь к официальной документации и ресурсам, чтобы изучить дополнительные функции.