---
title: Плоское декодирование сжатия
linktitle: Плоское декодирование сжатия
second_title: Aspose.PDF для справочника API .NET
description: Эффективно сжимайте изображения в PDF, используя сжатие Flate Decode с Aspose.PDF для .NET.
type: docs
weight: 140
url: /ru/net/programming-with-images/flate-decode-compression/
---

Это руководство шаг за шагом расскажет вам, как сжимать изображения с помощью сжатия Flate Decode в файл PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Убедитесь, что вы установили правильный каталог документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте PDF-документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## Шаг 3. Инициализируйте параметры оптимизации

 На этом шаге мы инициализируем параметры оптимизации для сжатия изображений. Создайте экземпляр`OptimizationOptions` и установите соответствующие параметры. В этом примере мы используем сжатие Flate Decode для оптимизации изображений.

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## Шаг 4. Оптимизируйте PDF-документ

 На этом этапе мы оптимизируем документ PDF, используя параметры оптимизации, определенные ранее. Позвоните`OptimizeResources` метод`doc` объект и передать параметры оптимизации.

```csharp
doc.OptimizeResources(optimizationOptions);
```

## Шаг 5. Сохраните обновленный PDF-документ.

 Сохраните обновленный PDF-документ, используя`Save` метод`doc` объект. Укажите выходной путь для файла PDF.

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### Пример исходного кода для Flate Decode Compression с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document doc = new Document(dataDir + "AddImage.pdf");
// Инициализировать параметры оптимизации
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
//Чтобы оптимизировать изображение с помощью сжатия FlateDecode, установите параметры оптимизации Flate.
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
// Установить параметры оптимизации
doc.OptimizeResources(optimizationOptions);
// Сохранить документ
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Заключение

Поздравляем! Вы успешно сжали изображения в PDF, используя сжатие Flate Decode с Aspose.PDF для .NET. Оптимизированный файл PDF сохраняется в указанном каталоге. Теперь вы можете использовать этот PDF-файл для более эффективного хранения или совместного использования.