---
title: Извлечь ссылки
linktitle: Извлечь ссылки
second_title: Aspose.PDF для справочника API .NET
description: Легко извлекайте ссылки из документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-links-and-actions/extract-links/
---

Извлечение ссылок из PDF-документа позволяет восстановить все гипертекстовые ссылки, присутствующие в документе. С Aspose.PDF для .NET вы можете легко извлечь эти ссылки, следуя следующему исходному коду:

## Шаг 1. Импорт необходимых библиотек

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей файл PDF, из которого вы хотите извлечь ссылки. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

 Мы откроем документ PDF с помощью`Document` сорт. Вот соответствующий код:

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Шаг 4: Извлеките ссылки

 На этом этапе мы извлечем ссылки, присутствующие в документе PDF, с помощью`AnnotationSelector` сорт. Вот соответствующий код:

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Шаг 5: Сохраните обновленный документ

Теперь давайте сохраним обновленный PDF-файл, используя`Save` метод`document` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Пример исходного кода для извлечения ссылок с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Извлечь действия
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Сохранить обновленный документ
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по извлечению ссылок из документа PDF с помощью Aspose.PDF для .NET. Вы можете использовать этот код для получения всех гиперссылок, присутствующих в документе.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях извлечения ссылок.