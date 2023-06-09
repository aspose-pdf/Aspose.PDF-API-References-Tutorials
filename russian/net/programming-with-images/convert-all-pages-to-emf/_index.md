---
title: Преобразовать все страницы в EMF
linktitle: Преобразовать все страницы в EMF
second_title: Aspose.PDF для справочника API .NET
description: Легко конвертируйте все страницы документа PDF в файлы EMF с помощью Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-images/convert-all-pages-to-emf/
---

Это руководство шаг за шагом расскажет вам, как преобразовать все страницы PDF-документа в файлы EMF (расширенный метафайл) с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToEMF.pdf");
```

## Шаг 3. Преобразуйте каждую страницу в формат EMF.

 На этом этапе мы просмотрим каждую страницу документа PDF и преобразуем их в отдельные файлы EMF. Мы будем использовать`for`цикл для перебора всех страниц.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Создайте поток для сохранения изображения EMF
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
     {
         // Создайте объект разрешения
         Resolution resolution = new Resolution(300);
        
         // Создайте устройство EMF с указанными атрибутами
         // Ширина, высота, разрешение
         EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
        
         // Преобразование определенной страницы и сохранение изображения в поток
         emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Закрыть поток
         imageStream.Close();
     }
}
```

### Пример исходного кода для преобразования всех страниц в EMF с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir+ "ConvertAllPagesToEMF.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
	{
		// Создать объект разрешения
		Resolution resolution = new Resolution(300);
		// Создать устройство PNG с указанными атрибутами
		// Ширина, высота, разрешение
		EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
		// Преобразование определенной страницы и сохранение изображения в поток
		emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Закрыть поток
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to EMF successfully!");
```

## Заключение

Поздравляем! Вы успешно преобразовали все страницы документа PDF в файлы EMF, используя Aspose.PDF для .NET. Отдельные файлы EMF сохраняются в указанном каталоге. Теперь вы можете использовать эти файлы EMF в своих проектах или приложениях.