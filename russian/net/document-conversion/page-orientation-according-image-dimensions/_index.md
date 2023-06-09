---
title: Ориентация страницы в соответствии с размерами изображения
linktitle: Ориентация страницы в соответствии с размерами изображения
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по настройке ориентации страницы на основе размеров изображения с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/document-conversion/page-orientation-according-image-dimensions/
---

В этом руководстве мы познакомим вас с процессом настройки ориентации страницы на основе размеров изображения с помощью Aspose.PDF для .NET. Мы пройдемся по списку изображений JPG в заданном каталоге и автоматически настроим ориентацию страницы в зависимости от ширины каждого изображения. Следуйте приведенным ниже инструкциям, чтобы добиться этого.

## Предпосылки
Прежде чем начать, убедитесь, что выполнены следующие условия:

- Базовые знания языка программирования С#.
- Библиотека Aspose.PDF для .NET, установленная в вашей системе.
- Среда разработки, такая как Visual Studio.

## Шаг 1. Просмотр изображений JPG
На этом этапе мы просмотрим все изображения JPG в заданном каталоге. Следуйте приведенному ниже коду:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте новый PDF-документ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//Получить имена всех файлов JPG в определенном каталоге
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Обязательно замените`"YOUR DOCUMENTS DIRECTORY"` с фактическим каталогом, в котором находятся ваши изображения JPG.

## Шаг 2: Создание страницы и изображения
После просмотра файлов JPG мы создадим страницу и изображение для каждого файла. Используйте следующий код:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Создать объект страницы
Aspose.Pdf.Page page = doc.Pages.Add();

// Создайте объект изображения
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Шаг 3: Проверка размеров изображения
Теперь давайте проверим размеры каждого изображения, чтобы определить ориентацию страницы. Используйте следующий код:

```csharp
// Создайте объект BitMap для получения информации из файла изображения.
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Проверьте, больше ли ширина изображения ширины страницы или нет
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Если ширина изображения меньше ширины страницы, установите ориентацию страницы на книжную.
page.PageInfo.IsLandscape = false;
```

## Шаг 4: Добавление изображения в документ PDF
После проверки размеров изображения мы добавим изображение в коллекцию абзацев документа PDF. Используйте следующий код:

```csharp
//Добавьте изображение в коллекцию абзацев документа PDF.
page.Paragraphs.Add(image1);
```

## Шаг 5: Сохранение PDF-файла
После того, как мы добавили все изображения в документ PDF, теперь мы можем сохранить полученный файл PDF. Вот последний шаг:

```csharp
// Сохраните PDF-файл
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с желаемым каталогом, где вы хотите сохранить выходной файл PDF.

### Пример исходного кода для ориентации страницы в соответствии с размерами изображения с использованием Aspose.PDF для .NET

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Получить имена всех файлов JPG в определенном каталоге
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Создать объект страницы
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Создайте объект изображения
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Создайте объект BitMap, чтобы получить информацию о файле изображения.
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Проверьте, превышает ли ширина файла изображения ширину страницы или нет.
	if (myimage.Width > page.PageInfo.Width)
		// Если ширина изображения больше ширины страницы, установите ориентацию страницы на Альбомную.
		page.PageInfo.IsLandscape = true;
	else
		// Если ширина изображения меньше ширины страницы, установите ориентацию страницы на книжную.
		page.PageInfo.IsLandscape = false;
	// Добавьте изображение в коллекцию абзацев документа PDF.
	page.Paragraphs.Add(image1);
}
// Сохраните PDF-файл
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Заключение
В этом руководстве мы рассмотрели пошаговый процесс настройки ориентации страницы на основе размеров изображения с помощью Aspose.PDF для .NET. Следуя приведенным выше инструкциям, теперь вы сможете создать PDF-документ с правильной ориентацией страницы для каждого изображения. Эта функция полезна, когда у вас есть изображения разных размеров и вы хотите встроить их в документ PDF.