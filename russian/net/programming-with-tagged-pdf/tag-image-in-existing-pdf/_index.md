---
title: Пометить изображение в существующем PDF
linktitle: Пометить изображение в существующем PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Пошаговое руководство по добавлению тегов к изображениям.
type: docs
weight: 210
url: /ru/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
В этом подробном руководстве мы шаг за шагом проведем вас через предоставленный исходный код C#, чтобы разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Следуйте приведенным ниже инструкциям, чтобы понять, как добавлять теги к изображению в PDF-файле.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2: Откройте существующий PDF-документ

На этом этапе мы откроем существующий PDF-документ с помощью Aspose.PDF.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Пути входных и выходных файлов
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Откройте документ
Document document = new Document(inFile);
```

Мы открыли существующий PDF-документ с помощью Aspose.PDF.

## Шаг 3: Получите тегированный контент и элемент корневой структуры

Теперь мы получим тегированное содержимое документа PDF и соответствующий элемент корневой структуры.

```csharp
// Получить помеченный контент и элемент корневой структуры
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Мы получили тегированное содержимое документа PDF и соответствующий элемент корневой структуры.

## Шаг 4: Установка заголовка для документа PDF с тегами

Теперь давайте установим заголовок для документа PDF с тегами.

```csharp
// Определите заголовок для документа PDF с тегами
taggedContent.SetTitle("Document with images");
```

Мы установили заголовок для документа PDF с тегами.

## Шаг 5. Назначьте замещающий текст и ограничивающую рамку изображению.

Теперь для каждого элемента изображения мы назначим замещающий текст и ограничивающую рамку.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Назначить альтернативный текст изображению
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Создайте и назначьте ограничивающую рамку (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Мы назначили замещающий текст и ограничивающую рамку каждому элементу изображения в документе PDF.

## Шаг 6: Перемещение элемента Span в абзац

Теперь давайте переместим элемент Span в абзац.

```csharp
// Переместите элемент Span в абзац (найдите неправильный диапазон и абзац в первом TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Переместите элемент Span в абзаце
spanElement.ChangeParentElement(paragraph);
```

Мы переместили элемент Span в указанный абзац.

## Шаг 7: Сохранение измененного PDF-документа

Теперь, когда мы внесли необходимые изменения, мы сохраним измененный PDF-документ.

```csharp
// Сохраните PDF-документ
document. Save(outFile);
```

Мы сохранили измененный PDF-документ в указанном каталоге.

### Пример исходного кода для тега изображения в существующем PDF-файле с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Открыть документ
Document document = new Document(inFile);

// Получает помеченный контент и элемент корневой структуры
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Установить заголовок для pdf-документа с тегами
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Установить альтернативный текст для рисунка
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Создайте и установите атрибут BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Переместить элемент диапазона в абзац (найти неправильный диапазон и абзац в первом TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Переместить элемент Span в абзац
spanElement.ChangeParentElement(paragraph);

// Сохранить документ
document.Save(outFile);

//Проверка соответствия PDF/UA для нашего документа
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом руководстве мы узнали, как разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Теперь вы можете использовать Aspose.PDF для добавления тегов и редактирования изображений в ваших PDF-документах.

### Часто задаваемые вопросы

#### В: Какова основная цель этого руководства по маркировке изображений в существующем PDF-файле с помощью Aspose.PDF для .NET?

О: Основная цель этого руководства — провести вас через процесс разметки изображения в существующем документе PDF с помощью Aspose.PDF для .NET. В учебнике представлены пошаговые инструкции и примеры исходного кода C#, которые помогут вам понять, как назначать альтернативный текст и ограничивающие рамки изображениям, перемещать элементы в документе и добавлять теги к изображениям.

#### В: Каковы предварительные условия для выполнения этого руководства по маркировке изображений в PDF с помощью Aspose.PDF для .NET?

О: Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

#### В: Как я могу открыть существующий документ PDF и получить доступ к его содержимому с тегами, используя Aspose.PDF для .NET?

О: В руководстве представлены примеры исходного кода C#, которые демонстрируют, как открыть существующий PDF-документ с помощью Aspose.PDF для .NET и получить доступ к его тегированному содержимому для дальнейшей обработки.

#### В: Какова цель назначения альтернативного текста и ограничивающих рамок изображениям в документе PDF?

О: Назначение альтернативного текста и ограничивающих рамок изображениям повышает доступность за счет предоставления описательного текста для изображений и определения их расположения и положения в документе. Эта информация имеет решающее значение для программ чтения с экрана и других вспомогательных технологий.

#### В: Как я могу установить заголовок для документа PDF с тегами, используя Aspose.PDF для .NET?

О: Учебное пособие включает примеры исходного кода C#, которые иллюстрируют, как установить заголовок для документа PDF с тегами, используя Aspose.PDF для .NET.

#### В: Что включает в себя процесс перемещения элементов в документе PDF?

О: Перемещение элементов в документе PDF связано с изменением родительского элемента определенного элемента. В этом руководстве вы узнаете, как переместить элемент Span в указанный элемент Paragraph в таблице.

#### В: Как сохранить измененный PDF-документ после добавления тегов и внесения изменений в изображения?

 О: После того как вы добавили теги, назначили альтернативный текст, установили ограничивающие рамки и внесли изменения в документ PDF, вы можете использовать предоставленные примеры исходного кода C#, чтобы сохранить измененный документ PDF с помощью`Save()` метод.

#### В: Какова цель примера исходного кода, представленного в руководстве?

О: Пример исходного кода служит практическим справочником по реализации тегов изображений и манипулирования ими с помощью Aspose.PDF для .NET. Вы можете использовать этот код в качестве отправной точки и изменить его в соответствии с вашими конкретными требованиями.

#### Вопрос. Можно ли применить эти методы к другим типам элементов в документе PDF, а не только к изображениям?

О: Да, методы, продемонстрированные в этом руководстве, можно адаптировать для работы с различными типами элементов в документе PDF. Вы можете применять аналогичные принципы для пометки и управления другими элементами, такими как текст, таблицы и т. д.

#### Вопрос. Как проверить соответствие модифицированного PDF-документа PDF/UA?

 О: В руководстве представлены примеры исходного кода C#, которые показывают, как проверить соответствие PDF/UA измененного документа PDF с помощью`Validate()` метод и создание XML-отчета.

#### В: Какие еще функции предлагает Aspose.PDF для .NET для работы с PDF-документами?

О: Aspose.PDF для .NET предлагает широкий спектр функций для работы с PDF-документами, включая работу с текстом, вставку изображений, создание таблиц, управление полями форм, цифровые подписи, аннотации и многое другое. Обратитесь к официальной документации и ресурсам для дальнейшего изучения.