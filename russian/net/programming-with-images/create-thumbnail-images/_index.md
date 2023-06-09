---
title: Создание эскизов изображений
linktitle: Создание эскизов изображений
second_title: Aspose.PDF для справочника API .NET
description: Легко создавайте миниатюры изображений из файлов PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-images/create-thumbnail-images/
---

Это руководство шаг за шагом расскажет вам, как создавать миниатюры изображений из файлов PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с путем к каталогу, содержащему ваши файлы PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Получите имена всех файлов PDF в каталоге

 На этом шаге мы получим имена всех PDF-файлов, присутствующих в указанном каталоге, с помощью C#.`Directory`сорт. Файлы будут храниться в массиве строк.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Шаг 3. Просмотрите все файлы PDF и их страницы.

 На этом этапе мы пройдемся по всем файлам PDF и их страницам, чтобы создать миниатюры изображений. Мы будем использовать`for` цикл для перебора всех файлов.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Откройте PDF-документ
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Пройтись по всем страницам документа
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Создайте поток для сохранения эскиза изображения
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Создайте объект разрешения
             Resolution resolution = new Resolution(300);
            
             // Создайте устройство JPEG с указанными атрибутами
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Преобразование определенной страницы и сохранение изображения в поток
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Закрыть поток
             imageStream.Close();
         }
     }
}
```

### Пример исходного кода для создания эскизов изображений с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Получить имена всех файлов PDF в определенном каталоге
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Перебрать все записи файлов в массиве
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Открыть документ
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Создать объект разрешения
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = новый JpegDevice(500, 700, разрешение, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Преобразование определенной страницы и сохранение изображения в поток
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Закрыть поток
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Заключение

Поздравляем! Вы успешно создали эскизы изображений из файлов PDF с помощью Aspose.PDF для .NET. Миниатюры изображений сохраняются в указанном каталоге. Теперь вы можете использовать эти эскизы для визуального предварительного просмотра файлов PDF.