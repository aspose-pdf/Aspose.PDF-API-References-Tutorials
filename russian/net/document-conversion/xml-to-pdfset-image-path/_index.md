---
title: XML в PDFSet Путь к изображению
linktitle: XML в PDFSet Путь к изображению
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по установке пути к изображению при преобразовании XML в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 340
url: /ru/net/document-conversion/xml-to-pdfset-image-path/
---

В этом руководстве мы пошагово расскажем, как задать путь к изображению при преобразовании файла XML в PDF с использованием библиотеки Aspose.PDF для .NET. Мы подробно расскажем о предоставленном исходном коде C# и покажем вам, как реализовать его в ваших собственных проектах. К концу этого руководства вы сможете легко указать путь к изображению при преобразовании XML в PDF.

## Шаг 1. Задайте пути к файлам
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Определите пути к входным файлам XML, используемому изображению и выходному файлу PDF. Заменять`"YOUR DOCUMENTS DIRECTORY"` с путем, где вы сохранили свои файлы.

## Шаг 2: Создайте экземпляр объекта Document
```csharp
Document doc = new Document();
```
Создайте экземпляр объекта Document.

## Шаг 3. Свяжите исходный XML-файл
```csharp
doc. BindXml(inXml);
```
Связывает исходный файл XML с документом.

## Шаг 4: Установите путь к изображению
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Получите ссылку на объект изображения из XML, используя его идентификатор, и задайте путь к используемому изображению.

## Шаг 5: Сохраните полученный PDF-файл
```csharp
doc.Save(outFile);
```
Сохраните полученный PDF-файл в указанную папку.

### Пример исходного кода для XML в PDFSet Image Path с использованием Aspose.PDF для .NET

```csharp
try
{
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение
В этом руководстве мы узнали, как установить путь к изображению при преобразовании XML в PDF с использованием библиотеки Aspose.PDF для .NET. Следуя приведенным инструкциям, вы можете легко указать путь к изображению в своих собственных преобразованиях XML в PDF.