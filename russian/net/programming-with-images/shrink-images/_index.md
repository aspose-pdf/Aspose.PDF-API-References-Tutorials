---
title: Уменьшить изображения
linktitle: Уменьшить изображения
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по уменьшению размера изображений в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 280
url: /ru/net/programming-with-images/shrink-images/
---

В этом уроке мы расскажем вам, как уменьшить размер изображений в документе PDF с помощью Aspose.PDF для .NET. Выполните следующие действия, чтобы легко выполнить эту операцию.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная и настроенная Visual Studio или любая другая среда разработки.
- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете скачать его с официального сайта Aspose.

## Шаг 1: Загрузка PDF-документа

Для начала используйте следующий код для загрузки PDF-документа:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Откройте документ
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

Обязательно укажите правильный путь к документу PDF.

## Шаг 2: Инициализация опций оптимизации

Далее мы инициализируем параметры оптимизации, чтобы уменьшить размер изображений. Используйте следующий код:

```csharp
// Инициализировать параметры оптимизации
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Активируйте опцию «Сжать изображения».
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Установить качество изображения
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

Вы можете настроить параметры оптимизации в соответствии с вашими потребностями.

## Шаг 3: Оптимизация документа PDF

Теперь мы собираемся оптимизировать документ PDF, уменьшив размер изображений. Используйте следующий код:

```csharp
// Оптимизируйте PDF-документ с помощью OptimizationOptions.
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// Сохраните обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

Обязательно укажите желаемый путь и имя файла для обновленного документа PDF.

### Пример исходного кода для сжатия изображений с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Инициализировать параметры оптимизации
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Установите параметр CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Установите параметр ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// Оптимизируйте документ PDF с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы успешно уменьшили размер изображений в документе PDF, используя Aspose.PDF для .NET. Теперь вы можете применить этот метод к своим собственным проектам, чтобы оптимизировать размер изображений в файлах PDF.