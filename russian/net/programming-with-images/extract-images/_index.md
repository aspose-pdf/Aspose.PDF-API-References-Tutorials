---
title: Извлечь изображения
linktitle: Извлечь изображения
second_title: Aspose.PDF для справочника API .NET
description: Легко извлекайте изображения из файла PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-images/extract-images/
---

Это руководство шаг за шагом расскажет вам, как извлечь изображения из файла PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Откройте PDF-документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Шаг 3. Извлеките конкретное изображение

 На этом этапе мы собираемся извлечь определенное изображение с определенной страницы. Использовать`Images` коллекция страницы`s `Объект ресурсов для доступа к нужному изображению. В приведенном ниже примере мы извлекаем изображение с индексом 1 с первой страницы.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Шаг 4: Сохраните извлеченное изображение

 Сохраните извлеченное изображение в файл с помощью`Save` метод`xImage`объект. Укажите выходной путь и формат изображения (в этом примере мы используем формат JPEG).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Шаг 5. Сохраните обновленный PDF-файл.

 Сохраните обновленный файл PDF с помощью`Save` метод`pdfDocument` объект. Укажите выходной путь для файла PDF.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для извлечения изображений с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Извлечь конкретное изображение
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Сохранить выходное изображение
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Сохранить обновленный файл PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Заключение

Поздравляем! Вы успешно извлекли изображения из PDF с помощью Aspose.PDF для .NET. Извлеченное изображение сохраняется в указанном каталоге, а также сохраняется обновленный файл PDF. Теперь вы можете использовать эти файлы для своих конкретных нужд.