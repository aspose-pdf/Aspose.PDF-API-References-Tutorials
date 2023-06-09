---
title: Размещение изображений
linktitle: Размещение изображений
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как использовать Aspose.PDF для .NET для размещения изображений в документе PDF.
type: docs
weight: 170
url: /ru/net/programming-with-images/image-placements/
---

В этом руководстве мы будем использовать библиотеку Aspose.PDF для .NET для работы с PDF-документами и выполнения операций с изображениями. Мы загрузим документ PDF, извлечем информацию о размещении изображения и получим изображения с видимыми размерами.

## Шаг 1. Настройка среды
Прежде чем начать, убедитесь, что вы настроили среду разработки со следующим:
- Aspose.PDF для .NET установлен на вашем компьютере.
- Проект AC# готов к использованию.

## Шаг 2: Загрузка документа PDF
Для начала нам нужно загрузить документ PDF, который мы хотим обработать. Убедитесь, что вы указали правильный путь к каталогу, содержащему PDF-документ.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Загрузите исходный PDF-документ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу ваших документов, содержащему файл PDF.

## Шаг 3. Извлеките информацию о месте размещения из изображений
 Теперь, когда мы загрузили документ PDF, мы можем извлечь информацию о размещении из изображений. Мы будем использовать`ImagePlacementAbsorber`чтобы впитать расположение изображений с первой страницы документа.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Загрузить содержимое первой страницы
doc.Pages[1].Accept(abs);
```

Теперь мы извлекли информацию о размещении изображения с первой страницы документа.

## Шаг 4: Получение изображений с видимыми размерами
Теперь мы получим изображения с их видимыми размерами из информации о размещении, которую мы извлекли ранее.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Получить свойства изображения
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Получить изображение с видимыми размерами
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Получить изображение из ресурсов
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Создайте изображение с реальными размерами
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

В этом цикле мы извлекаем свойства каждого изображения, такие как ширина, высота, координаты X и Y левого нижнего угла, а также разрешение по горизонтали и вертикали. Затем мы извлекаем каждое изображение с его видимыми размерами, используя информацию о размещении.

### Пример исходного кода для размещения изображений с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузите исходный PDF-документ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Загрузить содержимое первой страницы
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Получить свойства изображения
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Получить изображение с видимыми размерами
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Получить изображение из ресурсов
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Создание растрового изображения с реальными размерами
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Заключение
Поздравляем! Теперь вы узнали, как использовать Aspose.PDF для .NET для размещения изображений в документе PDF. Мы объяснили предоставленный исходный код C#, который позволяет загружать PDF-документ, извлекать информацию о размещении из изображений и извлекать изображения с видимыми размерами. Не стесняйтесь экспериментировать с Aspose.PDF, чтобы изучить многие другие его функции.