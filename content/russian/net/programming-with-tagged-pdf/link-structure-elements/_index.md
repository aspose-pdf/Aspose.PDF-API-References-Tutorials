---
title: Элементы структуры ссылок
linktitle: Элементы структуры ссылок
second_title: Справочник по API Aspose.PDF для .NET
description: Пошаговое руководство по использованию элементов структуры ссылок с Aspose.PDF для .NET. Создавайте гиперссылки в ваших PDF-документах.
type: docs
weight: 120
url: /ru/net/programming-with-tagged-pdf/link-structure-elements/
---
В этом пошаговом руководстве мы покажем вам, как использовать элементы структуры ссылок с Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет вам создавать и обрабатывать PDF-документы программным способом. Элементы структуры ссылок позволяют вам добавлять гиперссылки в ваш PDF-документ, позволяя пользователям нажимать на ссылки и переходить к онлайн-ресурсам.

Давайте углубимся в код и узнаем, как использовать элементы структуры ссылок с Aspose.PDF для .NET.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Установлена библиотека Aspose.PDF для .NET.
2. Базовые знания языка программирования C#.

## Шаг 1: Настройка среды

Чтобы начать, откройте среду разработки C# и создайте новый проект. Убедитесь, что вы добавили ссылку на библиотеку Aspose.PDF для .NET в свой проект.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Шаг 2: Создание документа

 Первый шаг — создать новый PDF-документ с помощью`Document` сорт.

```csharp
// Создать PDF-документ
Document document = new Document();
```

## Шаг 3: Работа с тегированным контентом

Затем мы получаем помеченное содержимое документа для работы.

```csharp
// Получить помеченное содержимое документа
ITaggedContent taggedContent = document.TaggedContent;
```

## Шаг 4: Задайте название документа и язык.

Теперь мы можем задать название документа и язык.

```csharp
// Определите название документа и язык
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Шаг 5: Добавьте элементы структуры ссылок

Теперь давайте добавим элементы структуры ссылок в наш документ. Мы создадим различные типы ссылок, включая простые текстовые ссылки, ссылки-изображения и многострочные ссылки.
```csharp
// Получить корневой элемент структуры (элемент структуры документа)
StructureElement rootElement = taggedContent.RootElement;

// Добавить абзац с гиперссылкой
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Добавить абзац с гиперссылкой, содержащей форматированный текст
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Добавить абзац с гиперссылкой, содержащей частично отформатированный текст
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Добавить абзац с многострочной гиперссылкой
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Добавьте абзац с гиперссылкой, содержащей изображение
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Шаг 6: Сохраните помеченный PDF-документ.

Наконец, мы сохраняем помеченный PDF-документ.

```csharp
// Сохраните помеченный PDF-документ
document. Save(outFile);
```

## Шаг 7: Проверьте соответствие PDF/UA

 Мы также можем проверить документ на соответствие PDF/UA с помощью`Validate` Метод`Document` сорт.

```csharp
// Проверьте соответствие PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Пример исходного кода для элементов структуры ссылок с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Создание документа и получение тегированного PDF-контента
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Настройка заголовка и языка документа
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Получение корневого элемента структуры (элемент структуры документа)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Сохранить помеченный PDF-документ
document.Save(outFile);

// Проверка соответствия PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Заключение

Поздравляем! Вы узнали, как использовать элементы структуры ссылок с Aspose.PDF для .NET. Теперь вы можете создавать гиперссылки в своих PDF-документах, позволяя пользователям переходить к онлайн-ресурсам. Экспериментируйте и изучайте больше возможностей Aspose.PDF для создания интерактивных и обогащенных PDF-документов.

### Часто задаваемые вопросы

#### В: Что такое элементы структуры ссылок в PDF-документе и как они повышают интерактивность документа?

A: Элементы структуры ссылок в документе PDF используются для создания гиперссылок, которые позволяют пользователям переходить к онлайн-ресурсам или определенным местам в документе. Эти элементы повышают интерактивность, предоставляя кликабельные ссылки, которые позволяют пользователям получать доступ к связанному контенту или внешним веб-сайтам.

#### В: Какую пользу могут принести элементы структуры ссылок в PDF-документе?

A: Элементы структуры ссылок улучшают пользовательский опыт, делая PDF-документ интерактивным. Они обеспечивают быстрый доступ к дополнительной информации, связанному контенту, внешним веб-сайтам или определенным разделам в документе, улучшая навигацию и облегчая поиск информации.

#### В: Можно ли создавать различные типы гиперссылок, используя элементы структуры ссылок в Aspose.PDF для .NET?

A: Да, вы можете создавать различные типы гиперссылок, используя элементы структуры ссылок. Aspose.PDF для .NET позволяет создавать гиперссылки с простым текстом, форматированным текстом, изображениями и многострочными описаниями, предлагая универсальность в том, как вы ссылаетесь на внешний контент или местоположения в документе.

#### В: Как настроить и инициализировать элементы структуры ссылок в PDF-документе с помощью Aspose.PDF для .NET?

 A: Чтобы использовать элементы структуры ссылок, вам сначала нужно создать новый PDF-документ с помощью`Document` класс. Затем получите помеченный контент с помощью`TaggedContent`свойство документа. Оттуда вы можете создавать и настраивать элементы структуры ссылок и добавлять их в корневой элемент структуры.

#### В: Как создать простую текстовую гиперссылку, используя элементы структуры ссылки?
 A: Вы можете создать простую текстовую гиперссылку, создав`LinkElement` и устанавливая его`Hyperlink` собственность к`WebHyperlink` с URL, на который вы хотите ссылаться. Вы также можете задать отображаемый текст ссылки, используя`SetText` метод.

#### В: Можно ли создавать гиперссылки с изображениями, используя элементы структуры ссылок?

 A: Да, вы можете создавать гиперссылки с изображениями, используя элементы структуры ссылок. Вы должны создать`LinkElement` а затем добавьте`FigureElement` с изображением. Это позволяет создать гиперссылку на основе изображения.

#### В: Как я могу гарантировать, что мой PDF-документ с гиперссылками соответствует стандарту доступности PDF/UA?

 A: Aspose.PDF для .NET предоставляет возможность проверки соответствия вашего PDF-документа стандарту PDF/UA с помощью`Validate` Метод`Document`класс. Это гарантирует, что гиперссылки документа будут доступны для пользователей с ограниченными возможностями.

#### В: Каковы альтернативные описания элементов структуры ссылок и почему они важны?

A: Альтернативные описания (alt text) для элементов структуры ссылок предоставляют текстовые описания гиперссылок. Эти описания необходимы для доступности, позволяя пользователям с нарушениями зрения понимать цель ссылки и ее назначение.

#### В: Могу ли я настроить внешний вид и поведение гиперссылок, созданных с использованием элементов структуры ссылок?

A: Хотя элементы структуры ссылок в первую очередь ориентированы на создание гиперссылок, вы можете дополнительно настроить внешний вид и поведение гиперссылок, используя другие функции, предлагаемые Aspose.PDF для .NET. Это включает указание цветов, стилей и действий ссылок.

#### В: Каким образом элементы структуры ссылок способствуют повышению интерактивности и удобства использования PDF-документов?

A: Элементы структуры ссылок преобразуют статические документы PDF в интерактивные, добавляя кликабельные гиперссылки. Эта интерактивность улучшает взаимодействие пользователя, обеспечивает плавную навигацию между связанным контентом и повышает общее удобство использования документа.