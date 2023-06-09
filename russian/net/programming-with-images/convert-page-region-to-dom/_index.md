---
title: Преобразование области страницы в DOM
linktitle: Преобразование области страницы в DOM
second_title: Aspose.PDF для справочника API .NET
description: Легко преобразуйте определенную область страницы PDF в объектную модель документа (DOM) с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-images/convert-page-region-to-dom/
---

В этом руководстве вы шаг за шагом узнаете, как преобразовать определенную область страницы в объектную модель документа (DOM) с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Прежде чем начать, убедитесь, что вы указали правильный каталог для документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Шаг 3: Получите прямоугольник области страницы

 На этом шаге мы определим прямоугольник, представляющий конкретную область страницы, которую мы хотим преобразовать в DOM. Использовать`Aspose.Pdf.Rectangle` класс для определения координат прямоугольника.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Шаг 4: Определите область обрезки страницы

 Использовать`CropBox` собственность`Page` объект, чтобы установить рамку обрезки страницы в желаемый прямоугольник области.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Шаг 5. Сохраните обрезанный PDF-документ в поток

 На этом шаге мы сохраним обрезанный PDF-документ в поток, используя`MemoryStream` сорт.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Шаг 6. Откройте обрезанный PDF-документ и преобразуйте его в изображение.

 Откройте обрезанный PDF-документ с помощью`Document` класс и преобразовать его в изображение. Мы будем использовать разрешение 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Шаг 7. Преобразуйте конкретную страницу в изображение

 Преобразуйте конкретную страницу в изображение, используя`Process` метод`pngDevice` объект. Укажите путь вывода изображения.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Пример исходного кода для преобразования области страницы в DOM с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document document = new Document( dataDir + "AddImage.pdf");
// Получить прямоугольник определенной области страницы
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//Установите значение CropBox в соответствии с прямоугольником желаемой области страницы.
document.Pages[1].CropBox = pageRect;
// Сохранить обрезанный документ в поток
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Откройте обрезанный PDF-документ и преобразуйте его в изображение
document = new Document(ms);
// Создать объект разрешения
Resolution resolution = new Resolution(300);
// Создать устройство PNG с указанными атрибутами
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Преобразование определенной страницы и сохранение изображения в поток
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Заключение

Поздравляем! Вы успешно преобразовали определенную область страницы в объектную модель документа (DOM) с помощью Aspose.PDF для .NET. Полученное изображение сохраняется в указанном каталоге. Теперь вы можете использовать это изображение в своих проектах или приложениях.