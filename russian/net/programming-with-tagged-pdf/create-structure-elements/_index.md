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
// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "StructureElements.pdf");

```

## Заключение

В этом руководстве мы узнали, как использовать Aspose.PDF для .NET для создания элементов структуры в документе PDF с тегами. Структурные элементы помогают улучшить доступность документов и упорядочить содержимое осмысленным образом. Теперь вы можете использовать эти знания для создания структурированных PDF-документов с удобной навигацией.

### Часто задаваемые вопросы

#### В: Какова цель создания элементов структуры в документе PDF с помощью Aspose.PDF для .NET?

О: Создание структурных элементов в документе PDF с помощью Aspose.PDF для .NET повышает доступность и организацию содержимого документа. Структурные элементы обеспечивают иерархическую структуру, улучшающую навигацию, семантику и совместимость с вспомогательными технологиями.

#### Вопрос: Как предоставленный код C# создает элементы структуры в документе PDF?

О: В примере кода показано, как создавать различные типы структурных элементов, включая группирующие элементы (такие как части, разделы и элементы div), элементы блочного уровня (такие как абзацы и заголовки), встроенные элементы (диапазон, цитата, примечание). ) и элементы изображения (такие как рисунки и формулы). Эти элементы структуры помогают организовать контент.

####  В: Почему важно задавать название документа и язык с помощью`SetTitle` and `SetLanguage` methods?

 О: Установка названия и языка документа с помощью`SetTitle` и`SetLanguage`методы улучшают доступность и семантику документа. Заголовок дает краткое описание цели документа, а языковой атрибут улучшает визуализацию и доступность для конкретного языка.

####  Q: Как группируются элементы, такие как`PartElement` and `SectElement`, contribute to the structure of the PDF document?

О: Элементы группировки создают иерархическую структуру в документе PDF, что позволяет логически организовать и сгруппировать связанное содержимое. Это улучшает навигацию и обеспечивает четкую структуру для пользователей.

#### Вопрос. Что такое структурные элементы блочного и встроенного уровня и чем они отличаются?

О: Структурные элементы блочного уровня представляют более крупные блоки содержимого, такие как абзацы и заголовки, в то время как элементы встроенного уровня представляют собой части текста внутри абзаца или заголовка, такие как промежутки, кавычки и примечания. Они помогают определить иерархию и отношения содержимого.

####  В: Как структурируются элементы художественного произведения, например`FigureElement` and `FormulaElement`, contribute to the document?

О: Элементы структуры иллюстраций позволяют добавлять в документ иллюстрации, рисунки и математические формулы. Они обеспечивают структурированный способ включения визуального и математического контента.

#### Вопрос. Можно ли использовать аналогичные методы для создания других типов элементов структуры, таких как списки, таблицы или аннотации?

О: Да, вы можете использовать аналогичные методы для создания других типов элементов структуры, таких как списки, таблицы, аннотации, ссылки и многое другое. Aspose.PDF предоставляет широкий спектр методов создания элементов структуры.

####  В: Как сохранить документ PDF с тегами с помощью`Save` method ensure the preservation of structure elements?

 А:`Save` Метод сохраняет документ PDF вместе с созданными элементами структуры, обеспечивая сохранение иерархической и семантической структуры документа для доступности и навигации.

#### Вопрос. Какие преимущества структурные элементы привносят в документы PDF с точки зрения доступности и совместимости с вспомогательными технологиями?

A: Структурные элементы улучшают доступность, обеспечивая осмысленную структуру и семантику документа. Это позволяет вспомогательным технологиям, таким как программы чтения с экрана, более эффективно интерпретировать и передавать содержимое документа пользователям с ограниченными возможностями.

#### В: Как я могу дополнительно настраивать и комбинировать различные типы элементов структуры в своих PDF-документах?

О: Вы можете комбинировать и настраивать элементы структуры, используя соответствующие методы создания, предоставляемые Aspose.PDF. Поэкспериментируйте с различными элементами и их свойствами, чтобы создать хорошо структурированный и организованный PDF-документ.