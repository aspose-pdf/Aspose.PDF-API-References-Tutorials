---
title: XPS в PDF
linktitle: XPS в PDF
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию файла XPS в PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 350
url: /ru/net/document-conversion/xps-to-pdf/
---

В этом руководстве мы шаг за шагом расскажем, как преобразовать файл XPS в PDF с помощью библиотеки Aspose.PDF для .NET. Мы подробно расскажем о предоставленном исходном коде C# и покажем вам, как реализовать его в ваших собственных проектах. К концу этого руководства вы сможете легко преобразовывать файлы XPS в документы PDF.

## Шаг 1: Установите каталог документов
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Заменять`"YOUR DOCUMENTS DIRECTORY"` с путем, где вы сохранили свои файлы.

## Шаг 2. Создайте экземпляр объекта LoadOptions с помощью параметров загрузки XPS.
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Создайте экземпляр объекта LoadOptions, используя параметры загрузки XPS.

## Шаг 3: Создайте объект документа
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Создайте объект Document, указав входной XPS-файл и параметры загрузки.

## Шаг 4: Сохраните полученный PDF-документ
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Сохраните полученный PDF-документ в указанную папку.

### Пример исходного кода для преобразования XPS в PDF с использованием Aspose.PDF для .NET

```csharp
try
{
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Создание экземпляра объекта LoadOption с использованием параметра загрузки XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Создать объект документа
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Сохраните полученный PDF-документ
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Заключение
В этом руководстве мы узнали, как преобразовать файл XPS в PDF с помощью библиотеки Aspose.PDF для .NET. Следуя приведенным инструкциям, вы можете легко выполнить это преобразование в своих собственных приложениях. Получите точные и профессиональные результаты при преобразовании файлов XPS в PDF.