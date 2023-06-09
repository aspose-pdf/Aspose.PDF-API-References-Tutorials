---
title: Поиск и получение изображений
linktitle: Поиск и получение изображений
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по поиску и получению изображений в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 260
url: /ru/net/programming-with-images/search-and-get-images/
---

В этом руководстве мы расскажем, как искать и получать изображения в документе PDF с помощью Aspose.PDF для .NET. Выполните следующие действия, чтобы легко выполнить эту операцию.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Обязательно укажите правильный путь к документу PDF.

## Шаг 2: Поиск местоположений изображений

Чтобы найти расположение изображений в документе PDF, используйте следующий код:

```csharp
// Создайте объект ImagePlacementAbsorber для поиска местоположений изображения.
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Принять поглотитель для всех страниц документа
doc.Pages.Accept(abs);
```

Это соберет расположение изображений в поглотителе.

## Шаг 3. Найдите расположение изображений и получите изображения и их свойства.

Далее мы просмотрим расположение собранных изображений и получим изображения и их свойства. Используйте следующий код:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //Получить изображение с помощью объекта ImagePlacement
     XImage image = imagePlacement.Image;

     // Отображение свойств местоположения изображения
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Это позволит просмотреть все местоположения изображений, получить соответствующие изображения и отобразить их свойства.

### Пример исходного кода для поиска и получения изображений с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Создайте объект ImagePlacementAbsorber для выполнения поиска размещения изображения.
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Примите поглотитель для всех страниц
doc.Pages.Accept(abs);
// Перебрать все ImagePlacements, получить изображение и свойства ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Получить изображение с помощью объекта ImagePlacement
	XImage image = imagePlacement.Image;
	// Показать свойства размещения изображения для всех мест размещения
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Заключение

Поздравляем! Вы успешно выполнили поиск и получили изображения в документе PDF с помощью Aspose.PDF для .NET. Теперь вы можете применить этот метод к своим собственным проектам для извлечения изображений и получения их свойств из файлов PDF.