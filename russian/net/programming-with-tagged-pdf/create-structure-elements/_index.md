---
title: Создать элементы структуры
linktitle: Создать элементы структуры
second_title: Aspose.PDF для справочника API .NET
description: В этом руководстве вы узнаете, как использовать Aspose.PDF для .NET для создания структурных элементов в документе PDF с тегами.
type: docs
weight: 60
url: /ru/net/programming-with-tagged-pdf/create-structure-elements/
---
Следующий исходный код C# использует Aspose.PDF для .NET для создания элементов структуры. Выполните следующие шаги, чтобы понять, как работает код.

## Шаг 1. Импортируйте необходимые библиотеки

```csharp
using Aspose.Pdf;
```

## Шаг 2: Определите каталог ваших документов

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Обязательно укажите правильный путь к папке с документами.

## Шаг 3: Создайте PDF-документ

```csharp
Document document = new Document();
```

Мы создаем новый объект Document, который представляет PDF-документ.

## Шаг 4. Настройте контент для работы с TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Мы извлекаем тегированное содержимое документа PDF. Это позволит нам манипулировать структурными элементами.

## Шаг 5: Установите название документа и язык

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Мы устанавливаем заголовок и язык документа PDF с тегами. Это улучшает доступность документа.

## Шаг 6: Создайте элементы группировки

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Мы создаем различные структурные элементы для группировки содержимого в документе PDF.

## Шаг 7: Создайте элементы структуры абзаца

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Мы создаем структурные элементы на уровне блоков для абзацев и заголовков. В приведенном выше примере показано создание заголовка уровня 1.

## Шаг 8: Создайте элементы структуры встроенного уровня

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Мы создаем элементы структуры встроенного уровня для частей текста, которые появляются внутри абзаца или заголовка.

## Шаг 9: Создайте элементы структуры изображения

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Создаем структурные элементы для иллюстраций и математических формул, присутствующих в документе.

## Шаг 10: Сохраните документ PDF с тегами

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Сохраняем размеченный PDF-документ с созданными элементами структуры.

### Пример исходного кода для создания элементов структуры с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать PDF-документ
Document document = new Document();
// Получить контент для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Установить заголовок и язык для Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Создать группирующие элементы
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Создание элементов структуры текстового блока
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
//Создание текстовых элементов структуры встроенного уровня
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Создание элементов структуры иллюстрации
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Методы находятся в разработке
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "StructureElements.pdf");

```

## Заключение

В этом руководстве мы узнали, как использовать Aspose.PDF для .NET для создания элементов структуры в документе PDF с тегами. Структурные элементы помогают улучшить доступность документов и упорядочить содержимое осмысленным образом. Теперь вы можете использовать эти знания для создания структурированных PDF-документов с удобной навигацией.
