---
title: Создать элементы структуры
linktitle: Создать элементы структуры
second_title: Справочник по API Aspose.PDF для .NET
description: В этом уроке вы узнаете, как использовать Aspose.PDF для .NET для создания структурных элементов в тегированном PDF-документе.
type: docs
weight: 60
url: /ru/net/programming-with-tagged-pdf/create-structure-elements/
---
Следующий исходный код C# использует Aspose.PDF для .NET для создания структурных элементов. Выполните следующие шаги, чтобы понять, как работает код.

## Шаг 1: Импортируйте необходимые библиотеки

```csharp
using Aspose.Pdf;
```

## Шаг 2: Определите каталог ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Обязательно укажите правильный путь к каталогу ваших документов.

## Шаг 3: Создайте PDF-документ

```csharp
Document document = new Document();
```

Мы создаем новый объект Document, представляющий PDF-документ.

## Шаг 4: Получите контент для работы с TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Мы извлекаем помеченное содержимое PDF-документа. Это позволит нам манипулировать структурными элементами.

## Шаг 5: Задайте название документа и язык.

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Мы задаем заголовок и язык тегированного PDF-документа. Это улучшает доступность документа.

## Шаг 6: Создание группирующих элементов

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

Мы создаем различные структурные элементы для группировки контента в PDF-документе.

## Шаг 7: Создание элементов структуры абзаца

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Мы создаем структурные элементы блочного уровня для абзацев и заголовков. В примере выше показано создание заголовка уровня 1.

## Шаг 8: Создание элементов структуры встроенного уровня

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Мы создаем элементы структуры встроенного уровня для частей текста, которые появляются внутри абзаца или заголовка.

## Шаг 9: Создание структурных элементов художественного произведения

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Мы создаем структурные элементы для иллюстраций и математических формул, присутствующих в документе.

## Шаг 10: Сохраните помеченный PDF-документ.

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Сохраняем размеченный PDF-документ с созданными структурными элементами.

### Пример исходного кода для создания элементов структуры с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать PDF-документ
Document document = new Document();
// Получите контент для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Установить заголовок и язык для Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Создать элементы группировки
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
// Создание текстовых блочных структурных элементов
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Создание текстовых элементов структуры на уровне строки
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Создание элементов структуры иллюстрации
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Методы находятся в стадии разработки.
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
// Сохранить помеченный PDF-документ
document.Save(dataDir + "StructureElements.pdf");

```

## Заключение

В этом уроке мы узнали, как использовать Aspose.PDF для .NET для создания структурных элементов в тегированном PDF-документе. Структурные элементы помогают улучшить доступность документа и организовать контент осмысленным образом. Теперь вы можете использовать эти знания для создания структурированных, простых в навигации PDF-документов.

### Часто задаваемые вопросы

#### В: Какова цель создания структурных элементов в PDF-документе с помощью Aspose.PDF для .NET?

A: Создание структурных элементов в документе PDF с помощью Aspose.PDF для .NET улучшает доступность и организацию содержимого документа. Структурные элементы обеспечивают иерархическую структуру, которая улучшает навигацию, семантику и совместимость со вспомогательными технологиями.

#### В: Как предоставленный код C# создает элементы структуры в PDF-документе?

A: В примере кода показано, как создавать различные типы структурных элементов, включая элементы группировки (например, части, разделы и div), элементы блочного уровня (например, абзацы и заголовки), элементы встроенного уровня (span, quote, note) и элементы художественных произведений (например, рисунки и формулы). Эти структурные элементы помогают организовать контент.

####  В: Почему важно задать название и язык документа с помощью`SetTitle` and `SetLanguage` methods?

 A: Установка названия и языка документа с помощью`SetTitle` и`SetLanguage`methods улучшает доступность и семантику документа. Заголовок содержит краткое описание цели документа, в то время как атрибут языка улучшает языковую визуализацию и доступность.

####  В: Как группировать элементы, такие как`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Группировка элементов создает иерархическую структуру в документе PDF, позволяя логически организовывать и группировать связанный контент. Это улучшает навигацию и обеспечивает четкую структуру для пользователей.

#### В: Что такое блочные и строчные элементы структуры и чем они отличаются?

A: Элементы структуры блочного уровня представляют более крупные блоки контента, такие как абзацы и заголовки, в то время как элементы строчного уровня представляют части текста внутри абзаца или заголовка, такие как пробелы, цитаты и примечания. Они помогают определить иерархию и отношения контента.

####  В: Как структурируются элементы художественного произведения, например`FigureElement` and `FormulaElement`, contribute to the document?

A: Элементы структуры Artwork позволяют добавлять иллюстрации, рисунки и математические формулы в документ. Они обеспечивают структурированный способ включения визуального и математического контента.

#### В: Могу ли я использовать аналогичные методы для создания других типов структурных элементов, таких как списки, таблицы или аннотации?

A: Да, вы можете использовать аналогичные методы для создания других типов структурных элементов, таких как списки, таблицы, аннотации, ссылки и т. д. Aspose.PDF предоставляет широкий спектр методов создания структурных элементов.

####  В: Как сохранить помеченный PDF-документ с помощью`Save` method ensure the preservation of structure elements?

 А:`Save` Метод сохраняет PDF-документ вместе с созданными структурными элементами, гарантируя сохранение иерархической и семантической структуры документа для обеспечения доступности и навигации.

#### В: Какие преимущества привносят структурные элементы в документы PDF с точки зрения доступности и совместимости со вспомогательными технологиями?

A: Элементы структуры улучшают доступность, предоставляя осмысленную структуру и семантику документу. Это позволяет вспомогательным технологиям, таким как программы чтения с экрана, более эффективно интерпретировать и передавать содержимое документа пользователям с ограниченными возможностями.

#### В: Как я могу дополнительно настраивать и комбинировать различные типы структурных элементов в моих PDF-документах?

A: Вы можете комбинировать и настраивать элементы структуры, используя соответствующие методы создания, предоставляемые Aspose.PDF. Экспериментируйте с различными элементами и их свойствами, чтобы создать хорошо структурированный и организованный PDF-документ.