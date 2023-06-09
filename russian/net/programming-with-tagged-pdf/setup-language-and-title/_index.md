---
title: Настройка языка и названия
linktitle: Настройка языка и названия
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по настройке языка и заголовка PDF-документа с помощью Aspose.PDF для .NET. Создавайте персонализированные многоязычные документы.
type: docs
weight: 140
url: /ru/net/programming-with-tagged-pdf/setup-language-and-title/
---
В этом руководстве мы расскажем вам, как настроить язык и заголовок PDF-документа с помощью библиотеки Aspose.PDF для .NET. Aspose.PDF — это мощная библиотека, которая позволяет программно создавать, манипулировать и преобразовывать PDF-файлы.

Давайте углубимся в код и узнаем, как настроить язык и заголовок PDF-документа с помощью Aspose.PDF для .NET.

## Предпосылки

Прежде чем начать, убедитесь, что вы установили Aspose.PDF для .NET и настроили среду разработки.

## Шаг 1: Создание документа

 Первым шагом является создание нового документа PDF с помощью`Document` сорт.

```csharp
// Создайте PDF-документ
Document document = new Document();
```

## Шаг 2. Получите доступ к тегированному содержимому

 Затем мы получаем доступ к тегированному содержимому документа с помощью`ITaggedContent` объект.

```csharp
//Доступ к тегированному контенту
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## Шаг 3. Установите название и язык

 Теперь мы можем установить название документа и язык с помощью`SetTitle` и`SetLanguage` методы`ITaggedContent` объект.

```csharp
// Определить название документа
taggedContent.SetTitle("Example of tagged document");

// Установить язык документа
taggedContent.SetLanguage("fr-FR");
```

## Шаг 4. Добавьте многоязычный контент

Далее мы добавляем в документ многоязычный контент, используя элементы абзаца для каждого языка.

```csharp
// Добавить абзац на английском
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Добавить абзац на немецком
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Добавить абзац на французском
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Добавить абзац на испанском
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## Шаг 5: Сохраните документ PDF с тегами

Наконец, мы сохраняем документ PDF с тегами.

```csharp
// Сохраните документ PDF с тегами
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Пример исходного кода для языка установки и заголовка с использованием Aspose.PDF для .NET 
```csharp

Document document = new Document();

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Получить тегированный контент
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Установить название и язык
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// Заголовок (en-US, унаследован от документа)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Абзац (английский)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Абзац (немецкий)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Абзац (французский)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Абзац (испанский)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Заключение

Поздравляем! Теперь вы знаете, как настроить язык и заголовок PDF-документа с помощью Aspose.PDF для .NET. Вы можете дополнительно изучить возможности Aspose.PDF для создания персонализированных и многоязычных PDF-документов.
