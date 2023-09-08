---
title: Пометить изображение в существующем PDF-файле
linktitle: Пометить изображение в существующем PDF-файле
second_title: Справочник по Aspose.PDF для .NET API
description: Узнайте, как разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Пошаговое руководство по добавлению тегов к изображениям.
type: docs
weight: 210
url: /ru/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
В этом подробном руководстве мы шаг за шагом познакомим вас с предоставленным исходным кодом C#, чтобы разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Следуйте инструкциям ниже, чтобы понять, как добавлять теги к изображению в PDF-файле.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2. Откройте существующий PDF-документ.

На этом этапе мы откроем существующий PDF-документ с помощью Aspose.PDF.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Пути к входным и выходным файлам
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Открыть документ
Document document = new Document(inFile);
```

Мы открыли существующий PDF-документ с помощью Aspose.PDF.

## Шаг 3. Получите тегированный контент и элемент корневой структуры

Теперь мы получим размеченное содержимое PDF-документа и соответствующий корневой элемент структуры.

```csharp
// Получить тегированный контент и элемент корневой структуры
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Мы получили размеченное содержимое PDF-документа и соответствующий корневой элемент структуры.

## Шаг 4. Установка заголовка PDF-документа с тегами

Теперь давайте зададим заголовок для PDF-документа с тегами.

```csharp
// Определите заголовок для PDF-документа с тегами
taggedContent.SetTitle("Document with images");
```

Мы установили заголовок для PDF-документа с тегами.

## Шаг 5. Назначьте изображению замещающий текст и ограничительную рамку.

Теперь для каждого элемента изображения мы назначим замещающий текст и ограничивающую рамку.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Назначьте альтернативный текст изображению
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Создайте и назначьте ограничивающую рамку (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Мы назначили замещающий текст и ограничивающую рамку каждому элементу изображения в документе PDF.

## Шаг 6. Перемещение элемента Span в абзац.

Теперь переместим элемент Span в абзац.

```csharp
// Переместить элемент Span в абзац (найти неправильный диапазон и абзац в первом TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Переместите элемент Span в абзац
spanElement.ChangeParentElement(paragraph);
```

Мы переместили элемент Span в указанный абзац.

## Шаг 7. Сохранение измененного PDF-документа.

Теперь, когда мы внесли необходимые изменения, мы сохраним измененный PDF-документ.

```csharp
// Сохраните PDF-документ
document. Save(outFile);
```

Мы сохранили измененный PDF-документ в указанном каталоге.

### Пример исходного кода для изображения тега в существующем PDF с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Открыть документ
Document document = new Document(inFile);

// Получает тегированное содержимое и элемент корневой структуры.
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Установить заголовок для PDF-документа с тегами
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

// Переместить элемент Span в абзац (найти неправильный диапазон и абзац в первом TD)
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

В этом уроке мы узнали, как разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Теперь вы можете использовать Aspose.PDF для добавления тегов и редактирования изображений в ваших PDF-документах.

### Часто задаваемые вопросы

#### Вопрос: Какова основная цель этого руководства по разметке изображений в существующем PDF-файле с использованием Aspose.PDF для .NET?

О: Основная цель этого руководства — провести вас через процесс разметки изображения в существующем PDF-документе с помощью Aspose.PDF для .NET. В руководстве представлены пошаговые инструкции и примеры исходного кода C#, которые помогут вам понять, как назначать альтернативный текст и ограничивающие рамки изображениям, перемещать элементы внутри документа и добавлять теги к изображениям.

#### Вопрос: Каковы необходимые условия для выполнения этого руководства по разметке изображений в PDF-файле с помощью Aspose.PDF для .NET?

О: Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

#### Вопрос: Как я могу открыть существующий PDF-документ и получить доступ к его размеченному содержимому с помощью Aspose.PDF для .NET?

Ответ: В руководстве представлены примеры исходного кода C#, которые демонстрируют, как открыть существующий PDF-документ с помощью Aspose.PDF для .NET и получить доступ к его размеченному содержимому для дальнейших манипуляций.

#### Вопрос: Какова цель назначения альтернативного текста и ограничивающих рамок изображениям в PDF-документе?

Ответ: Назначение альтернативного текста и ограничивающих рамок изображениям повышает доступность за счет предоставления описательного текста для изображений и определения их макета и положения в документе. Эта информация имеет решающее значение для программ чтения с экрана и других вспомогательных технологий.

#### Вопрос: Как я могу установить заголовок для PDF-документа с тегами, используя Aspose.PDF для .NET?

О: Учебное пособие включает примеры исходного кода C#, которые иллюстрируют, как установить заголовок для PDF-документа с тегами с помощью Aspose.PDF для .NET.

#### Вопрос: Что включает в себя процесс перемещения элементов в PDF-документе?

О: Перемещение элементов в PDF-документе предполагает изменение родительского элемента определенного элемента. В этом уроке вы узнаете, как переместить элемент Span в указанный элемент Paragraph в таблице.

#### Вопрос: Как сохранить измененный PDF-документ после добавления тегов и редактирования изображений?

 О: После того как вы добавили теги, назначили альтернативный текст, установили ограничивающие рамки и внесли изменения в PDF-документ, вы можете использовать предоставленные примеры исходного кода C#, чтобы сохранить измененный PDF-документ с помощью`Save()` метод.

#### Вопрос: Какова цель примера исходного кода, представленного в руководстве?

О: Пример исходного кода служит практическим справочником по реализации тегов и манипуляций с изображениями с помощью Aspose.PDF для .NET. Вы можете использовать этот код в качестве отправной точки и изменить его в соответствии со своими конкретными требованиями.

#### Вопрос: Могу ли я применить эти методы к другим типам элементов PDF-документа, а не только к изображениям?

О: Да, методы, продемонстрированные в этом руководстве, можно адаптировать для работы с различными типами элементов в PDF-документе. Вы можете применять аналогичные принципы для тегирования и управления другими элементами, такими как текст, таблицы и т. д.

#### Вопрос: Как я могу проверить соответствие PDF/UA измененного PDF-документа?

 Ответ: В руководстве представлены примеры исходного кода C#, которые показывают, как проверить соответствие PDF/UA измененного PDF-документа с помощью`Validate()` метод и создание отчета XML.

#### Вопрос: Какие еще функции предлагает Aspose.PDF for .NET для работы с PDF-документами?

О: Aspose.PDF для .NET предлагает широкий спектр функций для работы с PDF-документами, включая манипулирование текстом, вставку изображений, создание таблиц, управление полями форм, цифровые подписи, аннотации и многое другое. Для дальнейшего изучения обратитесь к официальной документации и ресурсам.