---
title: Изменить размер изображений
linktitle: Изменить размер изображений
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по изменению размера изображений в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 250
url: /ru/net/programming-with-images/resize-images/
---

В этом руководстве мы расскажем, как изменить размер изображений в документе PDF с помощью Aspose.PDF для .NET. Выполните следующие действия, чтобы легко выполнить эту операцию.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная и настроенная Visual Studio или любая другая среда разработки.
- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете скачать его с официального сайта Aspose.

## Шаг 1: Загрузка PDF-документа

Для начала используйте следующий код для загрузки PDF-документа:

```csharp
// Инициализировать время
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Откройте документ
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Обязательно укажите правильный путь к документу PDF.

## Шаг 2: Инициализация опций оптимизации

Перед изменением размера изображений нам нужно инициализировать параметры оптимизации. Используйте следующий код:

```csharp
// Инициализировать параметры оптимизации
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Активируйте опцию «Сжать изображения».
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Установить качество изображения
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Активируйте опцию ResizeImages
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Установить максимальное разрешение
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

Вы можете настроить параметры оптимизации в соответствии с вашими потребностями.

## Шаг 3: Оптимизация документа PDF

Теперь мы собираемся оптимизировать документ PDF, используя определенные нами параметры оптимизации. Используйте следующий код:

```csharp
// Оптимизируйте PDF-документ с помощью OptimizationOptions.
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Сохраните обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Обязательно укажите желаемый путь и имя файла для обновленного документа PDF.

### Пример исходного кода для изменения размера изображений с использованием Aspose.PDF для .NET 
```csharp
// Инициализировать время
var time = DateTime.Now.Ticks;
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Инициализировать параметры оптимизации
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Установите параметр CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Установите параметр ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Установите параметр ResizeImage
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Установите параметр MaxResolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// Оптимизируйте документ PDF с помощью OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы успешно изменили размер изображений в документе PDF с помощью Aspose.PDF для .NET. Теперь вы можете применить этот метод к своим собственным проектам, чтобы изменить размер изображений в файлах PDF.