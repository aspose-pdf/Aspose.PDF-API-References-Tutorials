---
title: Подсказка шрифта PDF в PNG
linktitle: Подсказка шрифта PDF в PNG
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по преобразованию PDF в PNG с подсказкой шрифта с использованием Aspose.PDF для .NET.
type: docs
weight: 160
url: /ru/net/document-conversion/pdf-to-png-font-hinting/
---

В этом руководстве мы познакомим вас с процессом преобразования изображений PDF в PNG с помощью Aspose.PDF для .NET, включив подсказку шрифта. Подсказка шрифта — это метод, улучшающий читаемость мелкого шрифта. Следуя приведенным ниже инструкциям, вы сможете преобразовать каждую страницу PDF-файла в изображение PNG с подсказкой шрифта.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1. Открытие исходного PDF-документа
На этом этапе мы откроем исходный PDF-файл, используя Aspose.PDF для .NET. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Откройте документ
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находится ваш файл PDF.

## Шаг 2. Включите подсказку шрифта
После открытия файла PDF мы включим подсказку шрифта, используя параметры рендеринга. Используйте следующий код:

```csharp
// Создайте параметры рендеринга, чтобы включить подсказку шрифта
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Шаг 3. Конвертируйте изображения в PNG
Теперь мы собираемся преобразовать каждую страницу PDF в изображение PNG с подсказкой шрифта. Используйте следующий код:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Создайте объект PNGDevice с указанными атрибутами
         // Ширина, высота, разрешение, качество
         // Качество [0-100], 100 — максимальное
         // Создайте объект разрешения
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Установите предопределенные параметры рендеринга
         pngDevice.RenderingOptions = opts;

         // Преобразование определенной страницы и сохранение изображения в поток
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Закрыть поток
         imageStream.Close();
     }
}
```

Приведенный выше код преобразует каждую страницу PDF-файла в изображение PNG с подсказкой шрифта и сохраняет каждое изображение в виде отдельного файла PNG.

### Пример исходного кода для хинтинга PDF в PNGFont с использованием Aspose.Words для .NET

```csharp
try
{
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Открыть документ
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Создайте Aspose.Pdf.RenderingOptions, чтобы включить подсказку шрифта.
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
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
			// Установите предопределенные параметры рендеринга
			pngDevice.RenderingOptions = opts;

			// Преобразование определенной страницы и сохранение изображения в поток
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Закрыть поток
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс преобразования изображений PDF в PNG с подсказкой шрифта с использованием Aspose.PDF для .NET. Следуя инструкциям, изложенным выше, теперь вы сможете преобразовать каждую страницу PDF в изображение PNG с подсказкой шрифта. Эта функция полезна, когда вы хотите сохранить читаемость мелких шрифтов при преобразовании в изображения PNG.