---
title: Добавить элемент структуры в элемент
linktitle: Добавить элемент структуры в элемент
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по добавлению элемента структуры в элемент в документе PDF с использованием Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
В этом руководстве мы предоставим вам пошаговое руководство о том, как добавить элемент структуры к элементу в документе PDF с помощью Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно создавать, обрабатывать и конвертировать PDF-документы. Используя отмеченные функции структуры содержимого Aspose.PDF, вы можете создать иерархическую структуру в своем документе PDF.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio установлена с .NET framework.
2. Библиотека Aspose.PDF для .NET.

## Шаг 1: Настройка проекта

Для начала создайте новый проект в Visual Studio и добавьте ссылку на библиотеку Aspose.PDF для .NET. Вы можете загрузить библиотеку с официального сайта Aspose и установить ее на свой компьютер.

## Шаг 2. Импортируйте необходимые пространства имен

В файле кода C# импортируйте пространства имен, необходимые для доступа к классам и методам, предоставляемым Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Шаг 3: Создание документа PDF и определение структурированных элементов

Используйте следующий код для создания документа PDF и определения структурированных элементов:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Этот код создает пустой документ PDF и добавляет структурированные элементы, такие как абзацы и интервалы. Каждый элемент структуры создается с использованием методов, предоставляемых Aspose.PDF.

## Шаг 4: Сохранение PDF-документа

Используйте следующий код для сохранения PDF-документа:

```csharp
document. Save(outFile);
```

Этот код сохраняет документ PDF со структурированными элементами в указанный файл.

### Пример исходного кода для добавления элемента структуры в элемент с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Создание документа и получение тегированного содержимого Pdf
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Установка заголовка и естественного языка для документа
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Получение элемента структуры Root (элемент структуры Document)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Сохранить документ в формате PDF с тегами
document.Save(outFile);
// Проверка соответствия PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Заключение

В этом руководстве вы узнали, как добавить элемент структуры к элементу документа PDF с помощью Aspose.PDF для .NET. Используя отмеченные функции структуры содержимого Aspose.PDF, вы можете создать иерархическую структуру в своем документе PDF, что упрощает управление и навигацию по содержимому.

### Часто задаваемые вопросы

#### В: Какова цель добавления элемента структуры к элементу в документе PDF с помощью Aspose.PDF для .NET?

О: Добавление элемента структуры к элементу документа PDF с помощью Aspose.PDF для .NET позволяет создать иерархическую структуру содержимого документа. Эта иерархическая структура улучшает организацию содержимого и навигацию по нему, упрощая управление и доступ к определенным элементам.

#### В: Как библиотека Aspose.PDF помогает добавлять элементы структуры в документ PDF?

О: Aspose.PDF для .NET — это мощная библиотека, предоставляющая возможности для создания, обработки и преобразования PDF-документов программным путем. В этом руководстве функции помеченной структуры содержимого библиотеки используются для создания и добавления элементов структуры к содержимому документа PDF.

#### В: Каковы предварительные условия для добавления элементов структуры в документ PDF с помощью Aspose.PDF для .NET?

О: Прежде чем начать, убедитесь, что у вас установлена Visual Studio с платформой .NET и что в вашем проекте есть ссылка на библиотеку Aspose.PDF для .NET.

#### Вопрос: Как предоставленный код C# создает и добавляет элементы структуры к содержимому документа PDF?

A: Код демонстрирует, как создать PDF-документ, определить корневой элемент структуры и добавить к нему различные структурированные элементы, такие как абзацы и интервалы. Каждый структурированный элемент создается с использованием методов, предоставляемых Aspose.PDF, что позволяет создавать иерархическую структуру.

#### Вопрос. Можно ли настроить типы элементов структуры, которые я добавляю в документ PDF?

О: Да, вы можете настраивать типы элементов структуры, изучая различные методы, предоставляемые библиотекой Aspose.PDF. Код демонстрирует абзацы и диапазоны в качестве примеров, но вы можете создавать и добавлять другие типы структурированных элементов по мере необходимости.

#### В: Как определить иерархическую связь между добавленными элементами структуры?

 A: Иерархическая связь между элементами структуры определяется порядком, в котором вы добавляете их к их родительским элементам. В коде отношения родитель-потомок устанавливаются с помощью`AppendChild` метод.

#### В: Каковы преимущества создания иерархической структуры в документе PDF?

О: Создание иерархической структуры в документе PDF повышает его доступность, навигацию и организацию. Это позволяет вспомогательным технологиям лучше интерпретировать и передавать содержание документа, делая его более удобным для людей с ограниченными возможностями.

#### Вопрос. Как проверить соответствие PDF/UA после добавления элементов структуры?

 О: Код, представленный в руководстве, демонстрирует, как проверить соответствие PDF/UA с помощью`Validate` метод. Проверяя документ на соответствие стандарту PDF/UA, вы можете убедиться, что добавленные элементы структуры соответствуют рекомендациям по доступности.

#### Вопрос. Можно ли использовать этот подход для добавления элементов структуры в существующий документ PDF?

О: Да, вы можете изменить предоставленный подход, чтобы добавить элементы структуры в существующий документ PDF. Вместо создания нового документа вы должны загрузить существующий документ с помощью Aspose.PDF, а затем выполнить аналогичные действия для добавления элементов структуры.