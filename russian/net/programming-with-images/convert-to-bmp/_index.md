---
title: Конвертировать в BMP
linktitle: Конвертировать в BMP
second_title: Aspose.PDF для справочника API .NET
description: Легко конвертируйте PDF в отдельные изображения BMP с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-images/convert-to-bmp/
---

Это руководство поможет вам шаг за шагом преобразовать файл PDF в отдельные изображения BMP с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Шаг 3. Преобразуйте каждую страницу в формат BMP.

 На этом этапе мы пройдемся по каждой странице документа PDF и преобразуем их в отдельные изображения BMP. Мы будем использовать`for`цикл для перебора всех страниц.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Создайте поток для сохранения изображения BMP
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // Создайте объект разрешения
         Resolution resolution = new Resolution(300);
        
         // Создать BMP-устройство с указанными атрибутами
         //Ширина, высота, разрешение, размер страницы
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // Преобразование определенной страницы и сохранение изображения в поток
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Закрыть поток
         imageStream.Close();
     }
}
```

### Пример исходного кода для преобразования в BMP с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// Создать объект разрешения
		Resolution resolution = new Resolution(300);
		// Создать BMP-устройство с указанными атрибутами
		// Ширина, высота, разрешение, размер страницы
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// Преобразование определенной страницы и сохранение изображения в поток
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Закрыть поток
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## Заключение

Поздравляем! Вы успешно преобразовали файл PDF в отдельные изображения BMP с помощью Aspose.PDF для .NET. Изображения BMP сохраняются в указанном каталоге. Теперь вы можете использовать эти изображения в своих проектах или приложениях.