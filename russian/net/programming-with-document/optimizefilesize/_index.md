---
title: Оптимизировать размер файла
linktitle: Оптимизировать размер файла
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как оптимизировать размер файлов ваших PDF-документов с помощью Aspose.PDF для .NET, используя это пошаговое руководство.
type: docs
weight: 250
url: /ru/net/programming-with-document/optimizefilesize/
---
Aspose.PDF для .NET — это библиотека, которая позволяет разработчикам создавать, редактировать и манипулировать файлами PDF в своих приложениях .NET. Одной из самых полезных функций этой библиотеки является возможность оптимизировать размер файла PDF-документа. В этой статье мы предоставим пошаговое руководство по оптимизации размера файла PDF-документа с помощью Aspose.PDF для .NET.

## Шаг 1: Загрузите PDF-документ

 Первым шагом в оптимизации размера файла PDF-документа является загрузка документа в ваше приложение. Вы можете сделать это с помощью`Document`класс, предоставляемый библиотекой Aspose.PDF для .NET. Вот пример того, как загрузить PDF-документ:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Обязательно замените`YOUR DOCUMENT DIRECTORY` с путем к каталогу, содержащему ваш PDF-документ.

## Шаг 2: Установите параметры оптимизации

 После того, как вы загрузили документ PDF, вы можете установить параметры оптимизации, чтобы указать, какие части документа вы хотите оптимизировать.`OptimizationOptions` Класс, предоставляемый библиотекой Aspose.PDF для .NET, позволяет указать различные параметры для оптимизации размера файла PDF-документа. Вот пример того, как установить некоторые параметры оптимизации:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

В этом примере мы устанавливаем следующие параметры:
- `LinkDuplcateStreams`: этот параметр позволяет удалять повторяющиеся потоки в документе PDF, что может помочь уменьшить размер файла.
- `RemoveUnusedObjects`: этот параметр позволяет удалить любые неиспользуемые объекты в документе PDF, что также может помочь уменьшить размер файла.
- `RemoveUnusedStreams`этот параметр позволяет удалить любые неиспользуемые потоки в документе PDF, что может еще больше уменьшить размер файла.
- `CompressImages`: этот параметр включает сжатие изображений в документе PDF, что может значительно уменьшить размер файла.
- `ImageQuality`: Этот параметр устанавливает качество сжатых изображений. Установка более низкого качества приведет к уменьшению размера файла, но также может привести к ухудшению качества изображения.

## Шаг 4. Оптимизируйте PDF-документ

 Теперь, когда вы установили параметры оптимизации, вы можете оптимизировать документ PDF, используя`OptimizeResources` метод, предоставляемый`Document` сорт. Вот пример того, как оптимизировать документ PDF:

```csharp
// Оптимизируйте размер файла, удалив неиспользуемые объекты.
pdfDocument.OptimizeResources(optimizationOptions);
```

## Шаг 5: Сохраните оптимизированный PDF-документ

После того, как вы оптимизировали документ PDF, вы можете сохранить оптимизированную версию в новый файл. Вот пример того, как сохранить оптимизированный PDF-документ:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Сохранить выходной документ
pdfDocument.Save(dataDir);
```

### Пример исходного кода для оптимизации размера файла с использованием Aspose.PDF для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Открыть документ
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

	OptimizationOptions optimizationOptions = new OptimizationOptions();
	optimizationOptions.LinkDuplcateStreams = true;
	optimizationOptions.RemoveUnusedObjects = true;
	optimizationOptions.RemoveUnusedStreams = true;
	optimizationOptions.ImageCompressionOptions.CompressImages = true;
	optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
	// Оптимизируйте размер файла, удалив неиспользуемые объекты.
	pdfDocument.OptimizeResources(optimizationOptions);
	dataDir = dataDir + "OptimizeFileSize_out.pdf";
	// Сохранить выходной документ
	pdfDocument.Save(dataDir);

```
