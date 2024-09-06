---
title: Алгоритм Брэдли
linktitle: Алгоритм Брэдли
second_title: Справочник по API Aspose.PDF для .NET
description: Конвертируйте PDF-документ с помощью алгоритма Брэдли с помощью Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-images/bradley-algorithm/
---
Это пошаговое руководство объясняет, как использовать алгоритм Брэдли с Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие шаги:

## Шаг 1: Определите каталог документов

Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменить`"YOUR DOCUMENT DIRECTORY"` в коде укажите путь к каталогу, где находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте документ.

 На этом этапе мы откроем PDF-документ с помощью`Document` класс Aspose.PDF. Используйте`Document` конструктор и передайте путь к PDF-документу.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Шаг 3: Определите выходные файлы

 Определите имена выходных файлов для результирующего изображения и двоичного изображения. Заменить`"resultant_out.tif"` и`"37116-bin_out.tif"` с желаемыми именами выходных файлов.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Шаг 4: Создайте объект «Разрешение»

 Создать`Resolution` объект для установки разрешения изображения TIFF. В этом примере мы используем разрешение 300 точек на дюйм.

```csharp
Resolution resolution = new Resolution(300);
```

## Шаг 5: Создайте объект TiffSettings

 Создать`TiffSettings` объект для указания настроек для выходного файла TIFF. В этом примере мы используем сжатие LZW и глубину цвета 1 бит на пиксель (формат 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Шаг 6: Создание устройства TIFF

 Создайте устройство TIFF с помощью`TiffDevice` объект, указывающий разрешение и настройки TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Шаг 7: Преобразуйте определенную страницу и сохраните изображение.

 Используйте`Process` Метод устройства TIFF для преобразования определенной страницы документа PDF и сохранения изображения в файл TIFF. Укажите путь к выходному файлу.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Шаг 8: Бинаризуем изображение с помощью алгоритма Брэдли.

 Используйте`BinarizeBradley`Метод устройства TIFF для бинаризации изображения с использованием алгоритма Брэдли. Этот метод берет входной поток исходного изображения и выходной поток для бинарного изображения. Укажите порог бинаризации (0,1 в этом примере).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Пример исходного кода для алгоритма Брэдли с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Создать объект резолюции
Resolution resolution = new Resolution(300);
// Создать объект TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Создать устройство TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Конвертируйте определенную страницу и сохраните изображение в потоке
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Заключение

Поздравляем! Вы успешно завершили преобразование с использованием алгоритма Брэдли с Aspose.PDF для .NET. Теперь вы можете использовать полученные изображения в своих проектах или приложениях.

### Часто задаваемые вопросы

#### В: Что такое алгоритм Брэдли и как он связан с Aspose.PDF для .NET?

A: Алгоритм Брэдли — это метод обработки изображений, используемый для улучшения качества и четкости изображений. Aspose.PDF для .NET предоставляет удобный способ применения алгоритма Брэдли к документам PDF, что приводит к улучшению изображений.

#### В: Как настроить среду для использования алгоритма Брэдли с Aspose.PDF для .NET?

A: Прежде чем начать, убедитесь, что у вас правильно установлен Aspose.PDF для .NET и настроена среда разработки.

#### В: Каково значение определения каталога документов в процессе алгоритма Брэдли?

A: Указание правильного каталога документа имеет решающее значение для обеспечения того, чтобы PDF-документ был расположен по правильному пути для обработки.

#### В: Как открыть PDF-документ с помощью Aspose.PDF для .NET в алгоритме Брэдли?

 А: Используйте`Document` класс для открытия PDF-документа, который служит входными данными для процесса алгоритма Брэдли.

#### В: Какова цель определения имен выходных файлов для изображения и двоичного изображения в процессе алгоритма Брэдли?

A: Определение имен выходных файлов позволяет указать, где будут сохранены результирующее изображение и двоичное изображение после применения алгоритма Брэдли.

#### В: Как настройка разрешения влияет на качество изображения TIFF в процессе алгоритма Брэдли?

A: Настройка разрешения определяет уровень детализации и четкости конечного изображения TIFF после применения алгоритма Брэдли.

#### В: Какие параметры можно настроить для выходного изображения TIFF в процессе алгоритма Брэдли?
A: Вы можете настроить такие параметры, как тип сжатия и глубину цвета, чтобы добиться желаемого результата для изображения TIFF.

#### В: Как устройство TIFF участвует в работе алгоритма Брэдли?

A: Устройство TIFF выступает в качестве инструмента для обработки изображений и применения алгоритма Брэдли, что приводит к повышению качества изображения.

#### В: Как преобразовать определенную страницу документа PDF в изображение TIFF с помощью алгоритма Брэдли?

 A: Используйте`Process` Метод устройства TIFF для преобразования определенной страницы документа PDF в изображение TIFF, которое затем может быть дополнительно обработано с использованием алгоритма Брэдли.