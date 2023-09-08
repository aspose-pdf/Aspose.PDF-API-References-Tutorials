---
title: Алгоритм Брэдли
linktitle: Алгоритм Брэдли
second_title: Справочник по Aspose.PDF для .NET API
description: Конвертируйте PDF-документ с помощью алгоритма Брэдли с помощью Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-images/bradley-algorithm/
---
В этом пошаговом руководстве объясняется, как использовать алгоритм Брэдли с Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1. Определите каталог документов.

 Прежде чем начать, убедитесь, что вы установили правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде укажите путь к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ.

На этом этапе мы откроем PDF-документ с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передайте путь к PDF-документу.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Шаг 3. Определите выходные файлы

 Определите имена выходных файлов для результирующего изображения и двоичного изображения. Заменять`"resultant_out.tif"` и`"37116-bin_out.tif"` с желаемыми именами выходных файлов.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Шаг 4. Создайте объект разрешения.

 Создать`Resolution`объект для установки разрешения изображения TIFF. В этом примере мы используем разрешение 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Шаг 5. Создайте объект TiffSettings.

 Создать`TiffSettings`объект, чтобы указать настройки выходного файла TIFF. В этом примере мы используем сжатие LZW и глубину цвета 1 бит на пиксель (формат 1 бит на пиксель).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Шаг 6. Создайте устройство TIFF.

 Создайте устройство TIFF с помощью`TiffDevice` объект, определяющий настройки разрешения и TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Шаг 7. Конвертируйте конкретную страницу и сохраните изображение.

 Использовать`Process` метод устройства TIFF для преобразования определенной страницы PDF-документа и сохранения изображения в файл TIFF. Укажите путь вывода файла.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Шаг 8. Бинаризация изображения с помощью алгоритма Брэдли.

 Использовать`BinarizeBradley` метод устройства TIFF для бинаризации изображения с использованием алгоритма Брэдли. Этот метод принимает входной поток исходного изображения и выходной поток двоичного изображения. Укажите порог бинаризации (0,1 в этом примере).

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

### Пример исходного кода алгоритма Брэдли с использованием Aspose.PDF для .NET 
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
// Создать устройство TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//Преобразуйте определенную страницу и сохраните изображение для потоковой передачи.
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

Поздравляем! Вы успешно завершили преобразование с использованием алгоритма Брэдли с помощью Aspose.PDF для .NET. Теперь вы можете использовать полученные изображения в своих проектах или приложениях.

### Часто задаваемые вопросы

#### Вопрос: Что такое алгоритм Брэдли и как он связан с Aspose.PDF для .NET?

Ответ: Алгоритм Брэдли — это метод обработки изображений, используемый для повышения качества и четкости изображения. Aspose.PDF для .NET предоставляет удобный способ применения алгоритма Брэдли к документам PDF, что приводит к улучшению изображений.

#### Вопрос: Как настроить среду для использования алгоритма Брэдли с Aspose.PDF для .NET?

О: Прежде чем начать, убедитесь, что у вас правильно установлен Aspose.PDF for .NET и настроена ваша среда разработки.

#### Вопрос: Каково значение определения каталога документов в процессе алгоритма Брэдли?

О: Указание правильного каталога документа имеет решающее значение для обеспечения того, чтобы PDF-документ находился в правильном пути для обработки.

#### Вопрос: Как открыть PDF-документ с помощью Aspose.PDF для .NET в алгоритме Брэдли?

 А: Используйте`Document` class, чтобы открыть PDF-документ, который служит входными данными для процесса алгоритма Брэдли.

#### Вопрос: Какова цель определения имен выходных файлов для изображения и двоичного изображения в процессе алгоритма Брэдли?

О: Определение имен выходных файлов позволяет вам указать, где результирующее изображение и двоичное изображение будут сохранены после применения алгоритма Брэдли.

#### Вопрос: Как настройка разрешения влияет на качество изображения TIFF в процессе алгоритма Брэдли?

О: Настройка разрешения определяет уровень детализации и четкости результирующего изображения TIFF после применения алгоритма Брэдли.

#### Вопрос: Какие параметры можно настроить для выходного изображения TIFF в процессе алгоритма Брэдли?
О: Вы можете настроить такие параметры, как тип сжатия и глубину цвета, чтобы добиться желаемого результата для изображения TIFF.

#### Вопрос: Как устройство TIFF участвует в алгоритме Брэдли?

О: Устройство TIFF действует как инструмент для обработки изображений и применения алгоритма Брэдли, что приводит к повышению качества изображения.

#### Вопрос: Как преобразовать определенную страницу PDF-документа в изображение TIFF в процессе алгоритма Брэдли?

 А: Используйте`Process` метод устройства TIFF для преобразования определенной страницы PDF-документа в изображение TIFF, которое затем может быть обработано с использованием алгоритма Брэдли.