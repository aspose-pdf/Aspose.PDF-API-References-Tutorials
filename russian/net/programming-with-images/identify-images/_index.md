---
title: Идентифицировать изображения
linktitle: Идентифицировать изображения
second_title: Aspose.PDF для справочника API .NET
description: Легко идентифицируйте изображения в файле PDF и определяйте их тип цвета с помощью Aspose.PDF для .NET.
type: docs
weight: 150
url: /ru/net/programming-with-images/identify-images/
---

Это руководство шаг за шагом расскажет вам, как идентифицировать изображения в файле PDF с помощью Aspose.PDF для .NET. Убедитесь, что вы уже настроили свою среду, и выполните следующие действия:

## Шаг 1: Определите каталог документов

 Убедитесь, что вы установили правильный каталог документов. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с указанием пути к каталогу, в котором находится ваш PDF-документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Инициализируйте счетчики

На этом шаге мы инициализируем счетчики для изображений в градациях серого и изображений RGB.

```csharp
int grayscaled = 0; // Счетчик изображений в градациях серого
int rdg = 0; // Счетчик для изображений RGB
```

## Шаг 3: Откройте PDF-документ

 На этом шаге мы откроем документ PDF с помощью`Document` класс Aspose.PDF. Использовать`Document` конструктор и передать путь к документу PDF.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## Шаг 4. Просмотрите страницы документа

На этом этапе мы пройдемся по всем страницам PDF-документа и найдем изображения на каждой странице.

```csharp
foreach(Page page in document.Pages)
{
```

## Шаг 5. Получите места размещения изображений

 На этом этапе мы будем использовать`ImagePlacementAbsorber` для получения мест размещения изображений на каждой странице.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## Шаг 6: Подсчитайте изображения и определите их цветотип

На этом этапе мы подсчитаем количество изображений на каждой странице и определим их тип цвета (оттенки серого или RGB).

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### Пример исходного кода для идентификации изображений с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Счетчик изображений в градациях серого
int grayscaled = 0;
// Счетчик для изображений RGB
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// Получить количество изображений на определенной странице
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Document.Pages[29].Accept(abs);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## Заключение

Поздравляем! Вы успешно идентифицировали изображения в PDF, используя Aspose.PDF для .NET. Изображения были подсчитаны и определен их цветовой тип (оттенки серого или RGB). Теперь вы можете использовать эту информацию для своих конкретных нужд.