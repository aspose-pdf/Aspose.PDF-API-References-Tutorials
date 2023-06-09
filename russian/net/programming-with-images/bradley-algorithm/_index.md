---
title: Алгоритм Брэдли
linktitle: Алгоритм Брэдли
second_title: Aspose.PDF для справочника API .NET
description: Преобразуйте документ PDF, используя алгоритм Брэдли с Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-images/bradley-algorithm/
---

В этом пошаговом руководстве объясняется, как использовать алгоритм Брэдли с Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Шаг 3: Определите выходные файлы

 Определите имена выходных файлов для результирующего изображения и двоичного изображения. Заменять`"resultant_out.tif"` и`"37116-bin_out.tif"` с желаемыми именами для выходных файлов.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Шаг 4: Создайте объект разрешения

 Создать`Resolution` объект для установки разрешения изображения TIFF. В этом примере мы используем разрешение 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Шаг 5: Создайте объект TiffSettings

 Создать`TiffSettings` объект, чтобы указать параметры для выходного файла TIFF. В этом примере мы используем сжатие LZW и глубину цвета 1 бит на пиксель (формат 1 бит на пиксель).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Шаг 6: Создайте устройство TIFF

 Создайте устройство TIFF, используя`TiffDevice` объекта, указав разрешение и настройки TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Шаг 7: Преобразуйте конкретную страницу и сохраните изображение

 Использовать`Process` метод устройства TIFF для преобразования определенной страницы документа PDF и сохранения изображения в файл TIFF. Укажите путь к выходному файлу.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Шаг 8. Бинаризируйте изображение с помощью алгоритма Брэдли.

 Использовать`BinarizeBradley`метод устройства TIFF для бинаризации изображения с использованием алгоритма Брэдли. Этот метод принимает входной поток исходного изображения и выходной поток для двоичного изображения. Задайте порог бинаризации (0,1 в этом примере).

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
// Создать объект разрешения
Resolution resolution = new Resolution(300);
// Создать объект TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Создать TIFF-устройство
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Преобразование определенной страницы и сохранение изображения в поток
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