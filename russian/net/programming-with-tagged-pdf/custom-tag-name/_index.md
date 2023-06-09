---
title: Пользовательское имя тега
linktitle: Пользовательское имя тега
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по использованию пользовательского имени тега с Aspose.PDF для .NET. Улучшите структуру ваших PDF-файлов с помощью пользовательских тегов.
type: docs
weight: 90
url: /ru/net/programming-with-tagged-pdf/custom-tag-name/
---
В этом пошаговом руководстве мы расскажем, как использовать собственное имя тега с Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, позволяющая программно управлять PDF-документами. Использование пользовательских тегов позволяет добавлять определенную структурную информацию в документ PDF, что упрощает его использование и доступ к нему.

Давайте углубимся в код и узнаем, как использовать собственное имя тега с Aspose.PDF для .NET.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Установлена библиотека Aspose.PDF для .NET.
2. Базовые знания языка программирования C#.

## Шаг 1. Настройка среды

Для начала откройте среду разработки C# и создайте новый проект. Убедитесь, что вы добавили в свой проект ссылку на библиотеку Aspose.PDF для .NET.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа

 Первым шагом является создание нового документа PDF с помощью`Document` сорт.

```csharp
// Создайте PDF-документ
Document document = new Document();
```

## Шаг 3. Работа с размеченным контентом

Затем мы получаем тегированное содержимое документа для работы.

```csharp
// Получить тегированное содержимое документа
ITaggedContent taggedContent = document.TaggedContent;
```

## Шаг 4: Установите название документа и язык

Теперь мы можем установить название документа и язык.

```csharp
// Определите название документа и язык
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Шаг 5: Создайте элементы логической структуры

Теперь давайте создадим несколько элементов логической структуры для организации нашего контента.

```csharp
// Создание элементов логической структуры
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Здесь мы создаем элементы абзаца и элементы span для нашего контента и назначаем им пользовательские теги.

## Шаг 6: Сохраните документ PDF с тегами

Наконец, мы сохраняем документ PDF с тегами.

```csharp
// Сохраните документ PDF с тегами
document.Save(dataDir + "CustomTag.pdf");
```

### Пример исходного кода для пользовательского имени тега с использованием Aspose.PDF для .NET 
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

// Создайте элементы логической структуры
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "CustomTag.pdf");

```

## Заключение

Поздравляем! Вы узнали, как использовать собственное имя тега с Aspose.PDF для .NET. Теперь вы можете добавлять определенную структурную информацию в документ PDF с помощью пользовательских тегов. Изучите дополнительные функции Aspose.PDF, чтобы раскрыть весь его потенциал.
