---
title: Элементы структуры ссылок
linktitle: Элементы структуры ссылок
second_title: Справочник по Aspose.PDF для .NET API
description: Пошаговое руководство по использованию элементов структуры ссылок в Aspose.PDF для .NET. Создавайте гиперссылки в PDF-документах.
type: docs
weight: 120
url: /ru/net/programming-with-tagged-pdf/link-structure-elements/
---
В этом пошаговом руководстве мы покажем вам, как использовать элементы структуры ссылок с Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет создавать PDF-документы и управлять ими программно. Элементы структуры ссылок позволяют добавлять гиперссылки в документ PDF, позволяя пользователям щелкать ссылки и переходить к онлайн-ресурсам.

Давайте углубимся в код и узнаем, как использовать элементы структуры ссылок с Aspose.PDF для .NET.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Установлена библиотека Aspose.PDF для .NET.
2. Базовые знания языка программирования C#.

## Шаг 1. Настройка среды

Для начала откройте среду разработки C# и создайте новый проект. Убедитесь, что вы добавили ссылку на библиотеку Aspose.PDF для .NET в свой проект.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Шаг 2: Создание документа

 Первым шагом является создание нового PDF-документа с помощью`Document` сорт.

```csharp
// Создайте PDF-документ
Document document = new Document();
```

## Шаг 3. Работайте с тегированным контентом

Затем мы получаем размеченное содержимое документа для работы.

```csharp
// Получить тегированное содержимое документа
ITaggedContent taggedContent = document.TaggedContent;
```

## Шаг 4. Установите название и язык документа.

Теперь мы можем установить заголовок и язык документа.

```csharp
// Определите название документа и язык
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Шаг 5. Добавьте элементы структуры ссылок.

Теперь добавим в наш документ элементы структуры ссылок. Мы будем создавать различные типы ссылок, включая простые текстовые ссылки, ссылки на изображения и многострочные ссылки.
```csharp
// Получить корневой элемент структуры (элемент структуры документа)
StructureElement rootElement = taggedContent.RootElement;

// Добавьте абзац с гиперссылкой
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Добавьте абзац с гиперссылкой, содержащей форматированный текст.
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Добавьте абзац с гиперссылкой, содержащей частично отформатированный текст.
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

// Добавьте абзац с гиперссылкой, содержащей изображение.
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

## Шаг 6. Сохраните PDF-документ с тегами.

Наконец, мы сохраняем PDF-документ с тегами.

```csharp
// Сохраните PDF-документ с тегами
document. Save(outFile);
```

## Шаг 7. Проверьте соответствие PDF/UA

 Мы также можем проверить документ на соответствие PDF/UA с помощью`Validate` метод`Document` сорт.

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

// Создание документа и получение размеченного PDF-контента
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Настройка заголовка и естественного языка для документа
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Получение элемента структуры Root (Элемент структуры документа)
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

// Сохранить PDF-документ с тегами
document.Save(outFile);

// Проверка соответствия PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Заключение

Поздравляем! Вы узнали, как использовать элементы структуры ссылок с Aspose.PDF для .NET. Теперь вы можете создавать гиперссылки в своих PDF-документах, позволяя пользователям переходить к онлайн-ресурсам. Экспериментируйте и изучайте дополнительные возможности Aspose.PDF для создания интерактивных и расширенных PDF-документов.

### Часто задаваемые вопросы

#### Вопрос. Что такое элементы структуры ссылок в документе PDF и как они повышают интерактивность документа?

Ответ: Элементы структуры ссылок в документе PDF используются для создания гиперссылок, которые позволяют пользователям переходить к онлайн-ресурсам или определенным местам в документе. Эти элементы повышают интерактивность, предоставляя интерактивные ссылки, которые позволяют пользователям получать доступ к соответствующему контенту или внешним веб-сайтам.

#### Вопрос: Какую пользу могут принести элементы структуры ссылок в PDF-документе?

Ответ: Элементы структуры ссылок повышают удобство работы пользователя, делая PDF-документ интерактивным. Они обеспечивают быстрый доступ к дополнительной информации, соответствующему контенту, внешним веб-сайтам или определенным разделам документа, улучшая навигацию и облегчая поиск информации.

#### Вопрос: Могу ли я создавать различные типы гиперссылок, используя элементы структуры ссылок в Aspose.PDF для .NET?

О: Да, вы можете создавать различные типы гиперссылок, используя элементы структуры ссылок. Aspose.PDF для .NET позволяет создавать гиперссылки с обычным текстом, форматированным текстом, изображениями и многострочными описаниями, предлагая универсальность в том, как вы ссылаетесь на внешний контент или места внутри документа.

#### Вопрос: Как настроить и инициализировать элементы структуры ссылок в PDF-документе с помощью Aspose.PDF для .NET?

 О: Чтобы использовать элементы структуры ссылок, сначала необходимо создать новый PDF-документ с помощью`Document` сорт. Затем получите тегированный контент, используя`TaggedContent`свойство документа. Отсюда вы можете создавать и настраивать элементы структуры ссылок и добавлять их в корневой элемент структуры.

#### Вопрос: Как создать простую текстовую гиперссылку, используя элементы структуры ссылки?
 О: Вы можете создать простую текстовую гиперссылку, создав`LinkElement` и установка его`Hyperlink` собственность на`WebHyperlink` с URL-адресом, на который вы хотите создать ссылку. Вы также можете настроить отображаемый текст ссылки с помощью`SetText` метод.

#### Вопрос: Можно ли создавать гиперссылки с изображениями, используя элементы структуры ссылки?

 О: Да, вы можете создавать гиперссылки с изображениями, используя элементы структуры ссылок. Вы бы создали`LinkElement` а затем добавьте`FigureElement` с изображением к нему. Это позволяет вам создать гиперссылку на основе изображения.

#### Вопрос: Как я могу гарантировать, что мой PDF-документ с гиперссылками соответствует стандарту доступности PDF/UA?

 О: Aspose.PDF для .NET предоставляет возможность проверить соответствие вашего PDF-документа стандарту PDF/UA с помощью`Validate` метод`Document`сорт. Это гарантирует, что гиперссылки документа будут доступны пользователям с ограниченными возможностями.

#### Вопрос: Каковы альтернативные описания элементов структуры ссылок и почему они важны?

О: Альтернативные описания (замещающий текст) для элементов структуры ссылок предоставляют текстовые описания гиперссылок. Эти описания необходимы для доступности, позволяя пользователям с нарушениями зрения понять назначение ссылки и ее назначение.

#### Вопрос: Могу ли я настроить внешний вид и поведение гиперссылок, созданных с использованием элементов структуры ссылок?

О: Хотя элементы структуры ссылок в первую очередь ориентированы на создание гиперссылок, вы можете дополнительно настроить внешний вид и поведение гиперссылок, используя другие функции, предлагаемые Aspose.PDF для .NET. Сюда входит указание цветов, стилей и действий со ссылками.

#### Вопрос: Как элементы структуры ссылок помогают сделать PDF-документы более интерактивными и удобными для пользователя?

Ответ: Элементы структуры ссылок преобразуют статические PDF-документы в интерактивные элементы путем добавления кликабельных гиперссылок. Такая интерактивность повышает вовлеченность пользователей, обеспечивает плавную навигацию между связанным контентом и повышает общее удобство использования документа.