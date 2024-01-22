---
title: Создание элементов структуры
linktitle: Создание элементов структуры
second_title: Справочник по Aspose.PDF для .NET API
description: В этом руководстве вы узнаете, как использовать Aspose.PDF для .NET для создания структурных элементов в PDF-документе с тегами.
type: docs
weight: 60
url: /ru/net/programming-with-tagged-pdf/create-structure-elements/
---
Следующий исходный код C# использует Aspose.PDF для .NET для создания элементов структуры. Выполните следующие действия, чтобы понять, как работает код.

## Шаг 1. Импортируйте необходимые библиотеки.

```csharp
using Aspose.Pdf;
```

## Шаг 2. Определите каталог ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Обязательно укажите правильный путь к каталогу ваших документов.

## Шаг 3. Создайте PDF-документ.

```csharp
Document document = new Document();
```

Мы создаем новый объект Document, который представляет документ PDF.

## Шаг 4. Обеспечьте работу контента с TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Мы извлекаем размеченное содержимое PDF-документа. Это позволит нам манипулировать структурными элементами.

## Шаг 5. Установите название и язык документа.

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Устанавливаем заголовок и язык размеченного PDF-документа. Это улучшает доступность документа.

## Шаг 6. Создайте элементы группировки

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

## Шаг 7. Создайте элементы структуры абзаца

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Создаём блочные структурные элементы для абзацев и заголовков. В приведенном выше примере показано создание заголовка уровня 1.

## Шаг 8. Создайте элементы структуры встроенного уровня.

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Мы создаем элементы структуры встроенного уровня для частей текста, которые появляются внутри абзаца или заголовка.

## Шаг 9: Создайте элементы структуры графического изображения

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Создаем структурные элементы для иллюстраций и математических формул, присутствующих в документе.

## Шаг 10. Сохраните PDF-документ с тегами.

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
// Установите заголовок и язык для Documentnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Создание элементов группировки
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
// Создание элементов структуры на уровне текстового блока
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Создание текстовых элементов структуры встроенного уровня
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
// Сохранить PDF-документ с тегами
document.Save(dataDir + "StructureElements.pdf");

```

## Заключение

В этом уроке мы узнали, как использовать Aspose.PDF для .NET для создания элементов структуры в PDF-документе с тегами. Структурные элементы помогают улучшить доступность документа и осмысленно организовать контент. Теперь вы можете использовать эти знания для создания структурированных PDF-документов с удобной навигацией.

### Часто задаваемые вопросы

#### Вопрос: Какова цель создания элементов структуры в PDF-документе с помощью Aspose.PDF для .NET?

О: Создание элементов структуры в PDF-документе с помощью Aspose.PDF для .NET повышает доступность и организацию содержимого документа. Элементы структуры обеспечивают иерархическую структуру, которая улучшает навигацию, семантику и совместимость со вспомогательными технологиями.

#### Вопрос: Как предоставленный код C# создает элементы структуры в документе PDF?

Ответ: В примере кода показано, как создавать различные типы структурных элементов, включая элементы группировки (например, части, разделы и элементы div), элементы уровня блока (например, абзацы и заголовки), элементы строкового уровня (диапазон, кавычка, примечание). ) и элементы графического изображения (например, рисунки и формулы). Эти элементы структуры помогают организовать контент.

####  Вопрос: Почему важно задавать название и язык документа с помощью`SetTitle` and `SetLanguage` methods?

 О: Установка названия и языка документа с помощью`SetTitle` и`SetLanguage`методы улучшают доступность и семантику документов. Заголовок дает краткое описание цели документа, а атрибут языка улучшает отображение и доступность для конкретного языка.

####  Вопрос: Как группируются элементы, например`PartElement` and `SectElement`, contribute to the structure of the PDF document?

О: Группировка элементов создает иерархическую структуру в PDF-документе, позволяя логически организовывать и группировать связанный контент. Это улучшает навигацию и обеспечивает четкую структуру для пользователей.

#### Вопрос: Что такое элементы структуры уровня блока и строчного уровня и чем они отличаются?

Ответ: Элементы структуры уровня блока представляют собой более крупные блоки контента, такие как абзацы и заголовки, тогда как элементы строчного уровня представляют собой части текста внутри абзаца или заголовка, такие как промежутки, кавычки и примечания. Они помогают определить иерархию и отношения содержания.

####  Вопрос: Как элементы структуры произведения искусства, например`FigureElement` and `FormulaElement`, contribute to the document?

О: Элементы структуры графического изображения позволяют добавлять в документ иллюстрации, рисунки и математические формулы. Они обеспечивают структурированный способ включения визуального и математического контента.

#### Вопрос: Могу ли я использовать аналогичные методы для создания других типов структурных элементов, таких как списки, таблицы или аннотации?

О: Да, вы можете использовать аналогичные методы для создания других типов структурных элементов, таких как списки, таблицы, аннотации, ссылки и т. д. Aspose.PDF предоставляет широкий спектр методов создания элементов структуры.

####  Вопрос: Как сохранить PDF-документ с тегами с помощью`Save` method ensure the preservation of structure elements?

 А:`Save` Метод сохраняет PDF-документ вместе с созданными элементами структуры, гарантируя сохранение иерархической и семантической структуры документа для обеспечения доступности и навигации.

#### Вопрос: Какие преимущества структурные элементы приносят PDF-документам с точки зрения доступности и совместимости со вспомогательными технологиями?

Ответ: Элементы структуры повышают доступность, обеспечивая осмысленную структуру и семантику документа. Это позволяет вспомогательным технологиям, таким как программы чтения с экрана, более эффективно интерпретировать и передавать содержимое документа пользователям с ограниченными возможностями.

#### Вопрос: Как я могу дополнительно настраивать и комбинировать различные типы структурных элементов в своих PDF-документах?

О: Вы можете комбинировать и настраивать элементы структуры, используя соответствующие методы создания, предоставляемые Aspose.PDF. Поэкспериментируйте с различными элементами и их свойствами, чтобы создать хорошо структурированный и организованный PDF-документ.