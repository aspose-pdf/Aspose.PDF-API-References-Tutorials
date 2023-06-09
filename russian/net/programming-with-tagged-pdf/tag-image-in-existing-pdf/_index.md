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
//Определите заголовок для документа PDF с тегами
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

// Проверка соответствия PDF/UA для нашего документа
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом руководстве мы узнали, как разметить изображение в существующем PDF-файле с помощью Aspose.PDF для .NET. Теперь вы можете использовать Aspose.PDF для добавления тегов и редактирования изображений в ваших PDF-документах.
