---
title: Сохранить изображение в коллекции XImage
linktitle: Сохранить изображение в коллекции XImage
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по сохранению изображения в коллекции XImage с использованием Aspose.PDF для .NET.
type: docs
weight: 290
url: /ru/net/programming-with-images/store-image-in-ximage-collection/
---

В этом руководстве мы расскажем, как сохранить изображение в коллекции XImage с помощью Aspose.PDF для .NET. Выполните следующие действия, чтобы легко выполнить эту операцию.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная и настроенная Visual Studio или любая другая среда разработки.
- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете скачать его с официального сайта Aspose.

## Шаг 1: Инициализация PDF-документа

Для начала используйте следующий код для инициализации нового PDF-документа:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Инициализировать документ
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Шаг 2. Добавление изображения в коллекцию XImage

Далее мы добавим изображение в коллекцию XImage документа PDF. Используйте следующий код:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Обязательно укажите правильный путь к исходному файлу изображения.

## Шаг 3: Размещение изображения на странице

Теперь давайте поместим изображение на страницу документа PDF. Используйте следующий код:

```csharp
page. Contents. Add(new GSave());

// Установить координаты
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//Использование оператора ConcatenateMatrix: определите, как должно быть размещено изображение
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Это поместит изображение в указанные координаты на странице.

## Шаг 4: Сохранение PDF-документа

Наконец, мы сохраним обновленный PDF-документ. Используйте следующий код:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Обязательно укажите желаемый путь и имя файла для конечного PDF-документа.

### Пример исходного кода для сохранения изображения в коллекции XImage с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Инициализировать документ
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Установить координаты
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//Использование оператора ConcatenateMatrix (сцепление матрицы): определяет, как должно быть размещено изображение.
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Заключение

Поздравляем! Вы успешно сохранили изображение в коллекции XImage, используя Aspose.PDF для .NET. Теперь вы можете применять этот метод к своим собственным проектам для управления и персонализации изображений в файлах PDF.