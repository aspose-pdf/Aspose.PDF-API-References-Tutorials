---
title: Строка таблицы стилей
linktitle: Строка таблицы стилей
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как настроить строки таблицы с помощью Aspose.PDF для .NET, пошаговое руководство по стилизации и форматированию строк.
type: docs
weight: 180
url: /ru/net/programming-with-tagged-pdf/style-table-row/
---
В этом подробном руководстве мы шаг за шагом познакомим вас с предоставленным исходным кодом C# для форматирования строки таблицы с помощью Aspose.PDF для .NET. Следуйте инструкциям ниже, чтобы понять, как настроить стили и свойства строк таблицы.

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
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

Мы создали новый документ и установили заголовок и язык документа.

## Шаг 3: Получение корневого элемента структуры

На этом этапе мы получим корневой элемент структуры для нашего документа.

```csharp
//Получить корневой элемент структуры
StructureElement rootElement = taggedContent.RootElement;
```

Мы получили корневой элемент структуры, который будет служить контейнером для элемента массива.

## Шаг 4: Создание элемента структуры массива

Теперь давайте создадим новый элемент структуры таблицы для нашего документа.

```csharp
// Создайте элемент структуры массива
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Мы создали новый элемент структуры массива и добавили его в корневой элемент структуры.

## Шаг 5. Настройте стили и свойства строк таблицы

На этом этапе мы настроим стили и свойства строк таблицы.

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

Мы настроили различные аспекты строки таблицы, такие как цвет фона, границы, высота строки, нумерация страниц, стиль ячейки по умолчанию и многое другое.

## Шаг 6. Сохранение PDF-документа с тегами

Теперь, когда мы создали документ со стилизованной строкой таблицы, мы сохраним его как PDF-документ с тегами.
```csharp
// Сохраните PDF-документ с тегами
document.Save(dataDir + "StyleTableRow.pdf");
```

Мы сохранили PDF-документ с тегами в указанном каталоге.

## Шаг 7. Проверка соответствия PDF/UA

Далее мы проверим соответствие нашего документа PDF/UA.

```csharp
// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Мы загрузили PDF-документ с тегами и проверили его соответствие PDF/UA, создав отчет XML.


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

// Сохранить PDF-документ с тегами
document.Save(dataDir + "StyleTableRow.pdf");

// Проверка соответствия PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом уроке мы узнали, как форматировать строку таблицы с помощью Aspose.PDF для .NET. Мы настроили стили и свойства строк таблицы, добавили заголовки, основные строки и нижний колонтитул, сохранили PDF-документ с тегами и проверили его соответствие PDF/UA.

### Часто задаваемые вопросы

#### Вопрос: Какова цель этого руководства по форматированию строк таблицы с использованием Aspose.PDF для .NET?

О: Цель этого руководства — провести вас через процесс форматирования строк таблицы в PDF-документе с помощью Aspose.PDF для .NET. Он содержит пошаговые инструкции и примеры исходного кода C#, которые помогут вам настроить стили и свойства строк таблицы.

#### Вопрос: Каковы необходимые условия для изучения этого руководства?

О: Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

#### Вопрос: Как создать новый PDF-документ и установить его заголовок и язык с помощью Aspose.PDF для .NET?

 О: Чтобы создать новый PDF-документ, вам необходимо создать`Document` объект из библиотеки Aspose.PDF. Приведенный в руководстве исходный код C# демонстрирует, как создать документ и установить его заголовок и свойства языка.

#### Вопрос: Каково значение элемента корневой структуры в PDF-документе?

Ответ: Элемент корневой структуры действует как контейнер для других элементов структуры, помогая организовать и классифицировать содержимое PDF-документа. Он играет решающую роль в установлении логической структуры документа.

#### Вопрос: Как создать и настроить элемент структуры таблицы для форматирования строк таблицы с помощью Aspose.PDF для .NET?

О: В руководстве объясняется, как создать элемент структуры таблицы и настроить его свойства для форматирования строк таблицы. Он охватывает такие аспекты, как цвет фона, границы, высота строки, нумерация страниц, стиль ячейки по умолчанию и многое другое.

#### Вопрос: Могу ли я настроить стили и свойства отдельных ячеек в строке таблицы?

О: Да, вы можете настроить стили и свойства отдельных ячеек в строке таблицы. В этом руководстве показано, как задать такие свойства, как цвет фона, границы, цвет текста, отступы и т. д., для ячеек таблицы в отформатированной строке таблицы.

#### Вопрос: Как добавить заголовки, основные строки и нижний колонтитул в отформатированную строку таблицы?

О: В руководстве приведены примеры создания и добавления заголовков, строк тела и нижнего колонтитула к элементу структуры таблицы. Эти элементы можно дополнительно настроить, используя свойства, описанные в руководстве.

#### Вопрос: Что такое соответствие PDF/UA и как я могу проверить его для моего PDF-документа с тегами?

 Ответ: Соответствие PDF/UA гарантирует, что PDF-документ соответствует стандартам доступности, что делает его более доступным для пользователей с ограниченными возможностями. В этом руководстве показано, как проверить соответствие PDF/UA с помощью`Validate()` метод и сгенерируйте отчет о соответствии XML.

#### Вопрос: Как я могу включить эти концепции в свои собственные .NET-приложения?

О: Вы можете использовать предоставленные примеры исходного кода C# в качестве руководства по реализации форматирования строк таблицы в ваших собственных .NET-приложениях. Измените и адаптируйте код в соответствии с вашими требованиями и интегрируйте его в свои проекты.

#### Вопрос. Существуют ли какие-либо рекомендации по форматированию строк таблиц в документах PDF?

О: При форматировании строк таблицы учитывайте читаемость и доступность содержимого. Убедитесь, что цвета имеют достаточный контраст, используйте четкие и разборчивые шрифты и сохраняйте единообразие макета. Проверьте соответствие PDF/UA, чтобы обеспечить соблюдение стандартов доступности.

#### Вопрос: Какие еще функции Aspose.PDF для .NET я могу изучить для настройки PDF-документа?

О: Aspose.PDF для .NET предлагает широкий спектр функций для настройки PDF-документов, включая манипулирование текстом, вставку изображений, управление полями формы, цифровые подписи, аннотации и многое другое. Обратитесь к официальной документации и ресурсам, чтобы изучить дополнительные функции.