---
title: Быстрое уменьшение изображений
linktitle: Быстрое уменьшение изображений
second_title: Aspose.PDF для справочника API .NET
description: Быстро уменьшайте размер изображений в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 130
url: /ru/net/programming-with-images/fast-shrink-images/
---

Это руководство шаг за шагом расскажет вам, как быстро уменьшить размер изображений в файле PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Инициализируйте время

Прежде чем мы начнем, мы установим время для измерения производительности сжатия. Добавьте следующий код для записи времени начала:

```csharp
var time = DateTime.Now.Ticks;
```

## Шаг 2: Определите каталог документов

 Убедитесь, что вы установили правильный каталог документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## Шаг 4. Инициализируйте параметры оптимизации

 На этом шаге мы инициализируем параметры оптимизации для сжатия изображений. Создайте экземпляр`OptimizationOptions` и установите соответствующие параметры. В этом примере мы включаем сжатие изображений, устанавливаем качество изображения на 75 и используем версию с быстрым сжатием.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## Шаг 5. Оптимизируйте PDF-документ

 На этом этапе мы оптимизируем документ PDF, используя параметры оптимизации, определенные ранее. Позвоните`OptimizeResources` метод`pdfDocument` объект и передать параметры оптимизации.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Шаг 6: Сохраните обновленный PDF-документ

 Сохраните обновленный PDF-документ, используя`Save` метод`pdfDocument` объект. Укажите выходной путь для файла PDF.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для быстрого сжатия изображений с использованием Aspose.PDF для .NET 
```csharp
// Инициализировать время
var time = DateTime.Now.Ticks;
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Инициализировать параметры оптимизации
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Установите параметр CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Установите параметр ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// Установите версию сжатия Imagae на быструю
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// Оптимизируйте документ PDF с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы быстро уменьшили размер изображений в PDF, используя Aspose.PDF для .NET. Оптимизированный файл PDF сохраняется в указанном каталоге. Теперь вы можете использовать этот PDF-файл с уменьшенными изображениями для более эффективного хранения или совместного использования.