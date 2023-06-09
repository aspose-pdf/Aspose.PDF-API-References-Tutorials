---
title: Конвертировать все страницы в PNG
linktitle: Конвертировать все страницы в PNG
second_title: Aspose.PDF для справочника API .NET
description: Легко конвертируйте все страницы документа PDF в файлы PNG с помощью Aspose.PDF для .NET.
type: docs
weight: 60
url: /ru/net/programming-with-images/convert-all-pages-to-png/
---

Это руководство поможет вам шаг за шагом преобразовать все страницы документа PDF в файлы PNG с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
```

## Шаг 3. Конвертируйте каждую страницу в PNG

 На этом этапе мы пройдемся по каждой странице документа PDF и преобразуем их в отдельные файлы PNG. Мы будем использовать`for`цикл для перебора всех страниц.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     //Создайте поток для сохранения изображения PNG
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Создайте устройство PNG с указанными атрибутами
         // Ширина, высота, разрешение, качество
         // Качество [0-100], 100 — максимальное
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
        
         // Преобразование определенной страницы и сохранение изображения в поток
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Закрыть поток
         imageStream.Close();
     }
}
```

### Пример исходного кода для преобразования всех страниц в PNG с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
	{
		// Создать устройство PNG с указанными атрибутами
		// Ширина, высота, разрешение, качество
		// Качество [0–100], 100 – максимальное значение.
		// Создать объект разрешения
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		// Преобразование определенной страницы и сохранение изображения в поток
		pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Закрыть поток
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to PNG successfully!");
```

## Заключение

Поздравляем! Вы успешно преобразовали все страницы документа PDF в файлы PNG с помощью Aspose.PDF для .NET. Отдельные файлы PNG сохраняются в указанном каталоге. Теперь вы можете использовать эти файлы PNG в своих проектах или приложениях.