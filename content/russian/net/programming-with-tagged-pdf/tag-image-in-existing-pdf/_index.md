---
title: Тег изображения в существующем PDF-файле
linktitle: Тег изображения в существующем PDF-файле
second_title: Справочник по API Aspose.PDF для .NET
description: Узнайте, как разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Пошаговое руководство по добавлению тегов к изображениям.
type: docs
weight: 210
url: /ru/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
В этом подробном руководстве мы шаг за шагом проведем вас по предоставленному исходному коду C#, чтобы разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Следуйте инструкциям ниже, чтобы понять, как добавлять теги к изображению в PDF-файле.

## Шаг 1: Настройка среды

Прежде чем начать, убедитесь, что вы настроили среду разработки для использования Aspose.PDF для .NET. Это включает установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2: Откройте существующий PDF-документ.

На этом этапе мы откроем существующий PDF-документ с помощью Aspose.PDF.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Пути входных и выходных файлов
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Открыть документ
Document document = new Document(inFile);
```

Мы открыли существующий PDF-документ с помощью Aspose.PDF.

## Шаг 3: Получите тегированный контент и корневой элемент структуры

Теперь мы получим тегированное содержимое PDF-документа и соответствующий ему корневой элемент структуры.

```csharp
// Получить помеченный контент и корневой элемент структуры
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Мы получили размеченное содержимое PDF-документа и соответствующий ему корневой элемент структуры.

## Шаг 4: Установка заголовка для помеченного PDF-документа

Теперь давайте зададим заголовок для помеченного PDF-документа.

```csharp
// Определите заголовок для помеченного PDF-документа.
taggedContent.SetTitle("Document with images");
```

Мы задали заголовок для помеченного PDF-документа.

## Шаг 5: Назначьте альтернативный текст и ограничивающую рамку изображению.

Теперь для каждого элемента изображения мы назначим альтернативный текст и ограничивающую рамку.

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

Мы назначили альтернативный текст и ограничивающую рамку каждому элементу изображения в PDF-документе.

## Шаг 6: Перемещение элемента Span в абзац

Теперь переместим элемент Span в абзац.

```csharp
// Переместить элемент Span в абзац (найти неправильный span и абзац в первом TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Переместить элемент Span в абзаце
spanElement.ChangeParentElement(paragraph);
```

Мы переместили элемент Span в указанный абзац.

## Шаг 7: Сохранение измененного PDF-документа

Теперь, когда мы внесли необходимые изменения, сохраним измененный PDF-документ.

```csharp
// Сохраните PDF-документ
document. Save(outFile);
```

Мы сохранили измененный PDF-документ в указанном каталоге.

### Пример исходного кода для тега изображения в существующем PDF с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Открыть документ
Document document = new Document(inFile);

// Получает помеченный контент и корневой элемент структуры
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Установить заголовок для помеченного документа PDF
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Установить альтернативный текст для рисунка
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Создать и установить атрибут BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Переместить элемент Span в абзац (найти неправильный span и абзац в первом TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Переместить элемент Span в абзац
spanElement.ChangeParentElement(paragraph);

// Сохранить документ
document.Save(outFile);

//Проверка соответствия нашего документа стандартам PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом уроке мы узнали, как разметить изображение в существующем PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать Aspose.PDF для добавления тегов и внесения изменений в изображения в ваших PDF-документах.

### Часто задаваемые вопросы

#### В: Какова основная цель этого руководства по маркировке изображений в существующем PDF-файле с помощью Aspose.PDF для .NET?

A: Основная цель этого руководства — провести вас через процесс разметки изображения в существующем документе PDF с помощью Aspose.PDF для .NET. Руководство содержит пошаговые инструкции и примеры исходного кода C#, которые помогут вам понять, как назначать альтернативный текст и ограничивающие рамки изображениям, перемещать элементы в документе и добавлять теги к изображениям.

#### В: Каковы предварительные условия для прохождения этого руководства по маркировке изображений в PDF-файле с использованием Aspose.PDF для .NET?

A: Перед началом убедитесь, что вы настроили среду разработки для использования Aspose.PDF для .NET. Это включает установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

#### В: Как открыть существующий PDF-документ и получить доступ к его помеченному содержимому с помощью Aspose.PDF для .NET?

A: В руководстве приведены примеры исходного кода C#, демонстрирующие, как открыть существующий PDF-документ с помощью Aspose.PDF для .NET и получить доступ к его помеченному содержимому для дальнейшей обработки.

#### В: Какова цель назначения альтернативного текста и ограничивающих рамок изображениям в PDF-документе?

A: Назначение альтернативного текста и ограничивающих рамок изображениям повышает доступность, предоставляя описательный текст для изображений и определяя их макет и положение в документе. Эта информация имеет решающее значение для программ чтения с экрана и других вспомогательных технологий.

#### В: Как задать заголовок для помеченного PDF-документа с помощью Aspose.PDF для .NET?

A: Учебное пособие содержит примеры исходного кода C#, которые иллюстрируют, как задать заголовок для тегированного PDF-документа с помощью Aspose.PDF для .NET.

#### В: Что включает в себя процесс перемещения элементов в документе PDF?

A: Перемещение элементов в документе PDF подразумевает изменение родительского элемента определенного элемента. В этом уроке вы узнаете, как переместить элемент Span в указанный элемент Paragraph в таблице.

#### В: Как сохранить измененный PDF-документ после добавления тегов и внесения изменений в изображения?

 A: После добавления тегов, назначения альтернативного текста, установки ограничивающих рамок и внесения изменений в документ PDF вы можете использовать предоставленные примеры исходного кода C# для сохранения измененного документа PDF с помощью`Save()` метод.

#### В: Каково назначение примера исходного кода, представленного в руководстве?

A: Исходный код примера служит практическим справочником по реализации тегирования и манипуляции изображениями с помощью Aspose.PDF для .NET. Вы можете использовать этот код в качестве отправной точки и изменять его в соответствии с вашими конкретными требованиями.

#### В: Могу ли я применить эти методы к другим типам элементов в PDF-документе, а не только к изображениям?

A: Да, методы, продемонстрированные в этом руководстве, можно адаптировать для работы с различными типами элементов в документе PDF. Вы можете применять аналогичные принципы для тегирования и управления другими элементами, такими как текст, таблицы и т. д.

#### В: Как я могу проверить соответствие измененного PDF-документа стандартам PDF/UA?

 A: В руководстве приведены примеры исходного кода C#, которые показывают, как проверить соответствие измененного PDF-документа стандартам PDF/UA с помощью`Validate()` метод и создание XML-отчета.

#### В: Какие еще функции предлагает Aspose.PDF for .NET для работы с PDF-документами?

A: Aspose.PDF для .NET предлагает широкий спектр функций для работы с PDF-документами, включая обработку текста, вставку изображений, создание таблиц, управление полями форм, цифровые подписи, аннотации и многое другое. Ознакомьтесь с официальной документацией и ресурсами для дальнейшего изучения.