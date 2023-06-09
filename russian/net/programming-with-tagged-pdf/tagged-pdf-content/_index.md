---
title: Помеченный PDF-контент
linktitle: Помеченный PDF-контент
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как работать с размеченным содержимым в документе PDF с помощью Aspose.PDF для .NET. Пошаговое руководство по использованию тегов.
type: docs
weight: 200
url: /ru/net/programming-with-tagged-pdf/tagged-pdf-content/
---
В этом подробном руководстве мы шаг за шагом проведем вас через предоставленный исходный код C# для работы с размеченным содержимым документа PDF с использованием Aspose.PDF для .NET. Следуйте приведенным ниже инструкциям, чтобы понять, как использовать тег для содержимого PDF.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили свою среду разработки для использования Aspose.PDF для .NET. Это включает в себя установку библиотеки Aspose.PDF и настройку вашего проекта для ссылки на нее.

## Шаг 2: Создание PDF-документа

На этом этапе мы создадим новый объект документа PDF с помощью Aspose.PDF.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте PDF-документ
Document document = new Document();
```

Мы создали новый PDF-документ с помощью Aspose.PDF.

## Шаг 3. Настройте содержимое для работы с помеченным PDF-файлом

На этом шаге мы получим содержимое PDF-документа для работы с теговым PDF-файлом.

```csharp
// Получите содержимое для работы с помеченным PDF
ITaggedContent taggedContent = document.TaggedContent;
```

Мы получили содержимое документа PDF для работы с тегированным PDF.

## Шаг 4. Работа с содержимым PDF с тегами

Теперь мы будем работать с размеченным содержимым PDF, используя соответствующие теги.

```csharp
// Работа с размеченным содержимым PDF
taggedContent.SetTitle("Simple tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Мы установили заголовок и язык документа PDF с тегами.

## Шаг 5: Сохранение документа PDF с тегами

Теперь, когда мы поработали с размеченным содержимым документа PDF, давайте сохраним его как размеченный документ PDF.

```csharp
// Сохраните документ PDF с тегами
document.Save(dataDir + "ContentPDFTag.pdf");
```

Мы сохранили помеченный PDF-документ в указанном каталоге.

### Пример исходного кода для Tagged PDFContent с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать PDF-документ
Document document = new Document();

// Получить контент для работы с TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Работа с теговым содержимым Pdf
// Установить заголовок и язык для Documnet
taggedContent.SetTitle("Simple Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Сохранить документ в формате PDF с тегами
document.Save(dataDir + "TaggedPDFContent.pdf");

```
## Заключение

В этом руководстве мы узнали, как работать с размеченным содержимым в документе PDF с помощью Aspose.PDF для .NET. Теперь вы можете использовать Aspose.PDF для создания PDF-документов с соответствующими тегами.
