---
title: XML в PDF
linktitle: XML в PDF
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию файла XML в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 330
url: /ru/net/document-conversion/xml-to-pdf/
---

В этом руководстве мы шаг за шагом расскажем, как преобразовать файл XML в PDF с помощью библиотеки Aspose.PDF для .NET. Мы подробно расскажем о предоставленном исходном коде C# и покажем вам, как реализовать его в ваших собственных проектах. К концу этого руководства вы сможете легко преобразовывать файлы XML в документы PDF.

## Шаг 1: Установите каталог документов
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Заменять`"YOUR DOCUMENTS DIRECTORY"` с указанием пути, по которому вы хотите сохранить сгенерированный PDF-файл.

## Шаг 2: Создайте экземпляр объекта Document
```csharp
Document doc = new Document();
```
Создайте экземпляр объекта Document.

## Шаг 3. Свяжите исходный XML-файл
```csharp
doc.BindXml(dataDir + "sample.xml");
```
Связывает исходный файл XML с документом.

## Шаг 4. Получите ссылку на объект страницы из XML
```csharp
Page page = (Page)doc.GetObjectById("mainSection");
```
Получите ссылку на объект Page из XML, используя его идентификатор.

## Шаг 5: Получите ссылку на текстовый сегмент из XML
```csharp
TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
segment = (TextSegment)doc.GetObjectById("strongHtml");
```
Получить ссылку на текстовые сегменты из XML, используя их идентификаторы. При необходимости вы можете добавить больше сегментов.

## Шаг 6: Сохраните полученный PDF-файл
```csharp
doc.Save(dataDir + "XMLToPDF_out.pdf");
```
Сохраните полученный PDF-файл в указанную папку.

### Пример исходного кода для преобразования XML в PDF с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создать объект документа
Document doc = new Document();
// Привязать исходный XML-файл
doc.BindXml( dataDir + "sample.xml");
// Получить ссылку на объект страницы из XML
Page page = (Page)doc.GetObjectById("mainSection");
// Получить ссылку на первый TextSegment с идентификатором boldHtml
TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
// Получить ссылку на второй TextSegment с идентификатором strongHtml
segment = (TextSegment)doc.GetObjectById("strongHtml");
// Сохраните полученный файл PDF
doc.Save(dataDir + "XMLToPDF_out.pdf");
```

## Заключение
В этом руководстве мы узнали, как преобразовать файл XML в PDF с помощью библиотеки Aspose.PDF для .NET. Мы подробно описали предоставленный исходный код C# и объяснили каждый шаг процесса преобразования. Следуя этим инструкциям, вы сможете легко интегрировать функции преобразования XML в PDF в свои собственные приложения .NET.