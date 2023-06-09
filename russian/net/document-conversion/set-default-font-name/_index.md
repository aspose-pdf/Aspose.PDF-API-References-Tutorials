---
title: Установить имя шрифта по умолчанию
linktitle: Установить имя шрифта по умолчанию
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по установке имени шрифта по умолчанию в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 270
url: /ru/net/document-conversion/set-default-font-name/
---

В этом руководстве мы покажем вам, как установить имя шрифта по умолчанию в файле PDF с помощью Aspose.PDF для .NET. Иногда при извлечении изображений из PDF-файла могут возникать проблемы с отсутствием шрифта. Указав имя шрифта по умолчанию, вы можете гарантировать правильное отображение извлеченного текста. Выполните следующие действия, чтобы установить имя шрифта по умолчанию в файле PDF.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1: Загрузка PDF-документа
 Первым шагом является загрузка документа PDF в`Document` объект. Используйте следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Код для добавления
}
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл PDF.

## Шаг 2: Установите имя шрифта по умолчанию
 Далее мы установим имя шрифта по умолчанию, используя`DefaultFontName` вариант`RenderingOptions` объект. Используйте следующий код:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Код для добавления
     }
}
```

 Обязательно замените`"Arial"` с желаемым названием шрифта.

## Шаг 3: Извлечение изображения
Далее мы извлечем изображение с указанной страницы PDF-документа. Используйте следующий код:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Не забудьте указать правильный номер страницы в`pdfDocument.Pages[1]`.

### Пример исходного кода для установки имени шрифта по умолчанию с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Заключение
В этом руководстве мы узнали, как установить имя шрифта по умолчанию в файле PDF с помощью Aspose.PDF для .NET. Указав имя шрифта по умолчанию, вы можете гарантировать правильное отображение извлеченного текста. Используйте этот метод для устранения проблем с отсутствующими шрифтами при извлечении изображений из файлов PDF.