---
title: Элементы структуры ссылок
linktitle: Элементы структуры ссылок
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по использованию элементов структуры ссылок с Aspose.PDF для .NET. Создавайте гиперссылки в своих документах PDF.
type: docs
weight: 120
url: /ru/net/programming-with-tagged-pdf/link-structure-elements/
---
В этом пошаговом руководстве мы покажем вам, как использовать элементы структуры ссылок с Aspose.PDF для .NET. Aspose.PDF — мощная библиотека, позволяющая программно создавать PDF-документы и управлять ими. Элементы структуры ссылок позволяют добавлять гиперссылки в документ PDF, позволяя пользователям щелкать ссылки и переходить к онлайн-ресурсам.

Давайте углубимся в код и узнаем, как использовать элементы структуры ссылок с Aspose.PDF для .NET.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Установлена библиотека Aspose.PDF для .NET.
2. Базовые знания языка программирования C#.

## Шаг 1. Настройка среды

Для начала откройте среду разработки C# и создайте новый проект. Убедитесь, что вы добавили в свой проект ссылку на библиотеку Aspose.PDF для .NET.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Шаг 5: Добавьте элементы ссылочной структуры

Теперь добавим в наш документ элементы структуры ссылок. Мы создадим различные типы ссылок, включая простые текстовые ссылки, ссылки на изображения и многострочные ссылки.
```csharp
// Получить элемент корневой структуры (элемент структуры документа)
StructureElement rootElement = taggedContent.RootElement;

// Добавить абзац с гиперссылкой
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Добавьте абзац с гиперссылкой, содержащей форматированный текст
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Добавьте абзац с гиперссылкой, содержащей частично отформатированный текст
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

## Шаг 6: Сохраните документ PDF с тегами

Наконец, мы сохраняем документ PDF с тегами.

```csharp
// Сохраните документ PDF с тегами
document. Save(outFile);
```

## Шаг 7. Проверьте соответствие PDF/UA

 Мы также можем проверить документ на соответствие PDF/UA, используя`Validate` метод`Document` сорт.

```csharp
// Проверить соответствие PDF/UA
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

// Создание документа и получение тегированного содержимого Pdf
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Установка заголовка и естественного языка для документа
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Получение элемента структуры Root (элемент структуры Document)
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

// Сохранить документ в формате PDF с тегами
document.Save(outFile);

// Проверка соответствия PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Заключение

Поздравляем! Вы узнали, как использовать элементы структуры ссылок с Aspose.PDF для .NET. Теперь вы можете создавать гиперссылки в своих PDF-документах, позволяя пользователям переходить к онлайн-ресурсам. Экспериментируйте и изучайте дополнительные возможности Aspose.PDF для создания интерактивных и обогащенных PDF-документов.

### Часто задаваемые вопросы

#### Вопрос. Что такое элементы структуры ссылок в документе PDF и как они повышают интерактивность документа?

О: Элементы структуры ссылок в документе PDF используются для создания гиперссылок, которые позволяют пользователям переходить к сетевым ресурсам или определенным местам в документе. Эти элементы повышают интерактивность, предоставляя интерактивные ссылки, которые позволяют пользователям получать доступ к соответствующему контенту или внешним веб-сайтам.

#### В: Как элементы структуры ссылок могут быть полезны в документе PDF?

О: Элементы структуры ссылок улучшают взаимодействие с пользователем, делая PDF-документ интерактивным. Они обеспечивают быстрый доступ к дополнительной информации, связанному содержимому, внешним веб-сайтам или определенным разделам документа, улучшая навигацию и облегчая поиск информации.

#### В: Могу ли я создавать различные типы гиперссылок, используя элементы структуры ссылок в Aspose.PDF для .NET?

О: Да, вы можете создавать различные типы гиперссылок, используя элементы структуры ссылок. Aspose.PDF для .NET позволяет создавать гиперссылки с простым текстом, форматированным текстом, изображениями и многострочными описаниями, предлагая гибкость в том, как вы ссылаетесь на внешний контент или места в документе.

#### В: Как настроить и инициализировать элементы структуры ссылок в документе PDF с помощью Aspose.PDF для .NET?

 О: Чтобы использовать элементы структуры ссылок, сначала необходимо создать новый PDF-документ, используя`Document` сорт. Затем получите помеченный контент с помощью`TaggedContent`свойство документа. Оттуда вы можете создавать и настраивать элементы структуры ссылок и добавлять их в корневой элемент структуры.

#### Q: Как я могу создать простую текстовую гиперссылку, используя элементы структуры ссылки?
 О: Вы можете создать простую текстовую гиперссылку, создав`LinkElement` и установка его`Hyperlink` собственность на`WebHyperlink` с URL-адресом, на который вы хотите сослаться. Вы также можете установить отображаемый текст ссылки с помощью`SetText` метод.

#### В: Можно ли создавать гиперссылки с изображениями с помощью элементов структуры ссылок?

 О: Да, вы можете создавать гиперссылки с изображениями, используя элементы структуры ссылок. Вы бы создали`LinkElement` а затем добавить`FigureElement` с изображением к нему. Это позволяет создать гиперссылку на основе изображения.

#### Вопрос. Как я могу убедиться, что мой PDF-документ с гиперссылками соответствует стандарту специальных возможностей PDF/UA?

 A: Aspose.PDF для .NET предоставляет возможность проверить соответствие вашего PDF-документа стандарту PDF/UA с помощью`Validate` метод`Document`сорт. Это гарантирует, что гиперссылки документа будут доступны для пользователей с ограниченными возможностями.

#### В: Какие существуют альтернативные описания элементов структуры ссылок и почему они важны?

A: Альтернативные описания (альтернативный текст) для элементов структуры ссылок содержат текстовые описания гиперссылок. Эти описания необходимы для доступности, позволяя пользователям с нарушениями зрения понять цель ссылки и ее назначение.

#### В: Можно ли настроить внешний вид и поведение гиперссылок, созданных с помощью элементов структуры ссылок?

О: В то время как элементы структуры ссылок в первую очередь предназначены для создания гиперссылок, вы можете дополнительно настроить внешний вид и поведение гиперссылок, используя другие функции, предлагаемые Aspose.PDF для .NET. Это включает в себя указание цветов, стилей и действий со ссылками.

#### В: Как элементы структуры ссылок способствуют тому, чтобы документы PDF стали более интерактивными и удобными для пользователя?

О: Элементы структуры ссылок преобразуют статические PDF-документы в интерактивные объекты, добавляя интерактивные гиперссылки. Эта интерактивность улучшает взаимодействие с пользователем, обеспечивает плавную навигацию между связанным содержимым и повышает общее удобство использования документа.