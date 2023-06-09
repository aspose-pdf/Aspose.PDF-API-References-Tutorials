---
title: Изображение в шапке
linktitle: Изображение в шапке
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить изображение в раздел заголовка PDF-документа с помощью Aspose.PDF для .NET.
type: docs
weight: 140
url: /ru/net/programming-with-stamps-and-watermarks/image-in-header/
---
В этом руководстве мы шаг за шагом расскажем, как добавить изображение в раздел заголовка документа PDF с помощью Aspose.PDF для .NET. Мы будем использовать предоставленный исходный код C#, чтобы открыть существующий документ PDF, создать буфер изображения, установить его свойства и добавить его на все страницы документа PDF.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная среда разработки .NET.
- Библиотека Aspose.PDF для .NET загружена и указана в вашем проекте.

## Шаг 2: Загрузка существующего документа PDF

Первым шагом является загрузка существующего документа PDF в ваш проект. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Откройте существующий PDF-документ
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором находится ваш PDF-документ.

## Шаг 3: Создание и добавление изображения в раздел заголовка

Теперь, когда документ PDF загружен, мы можем создать буфер изображений и добавить его на все страницы документа в качестве раздела заголовка. Вот как:

```csharp
// Создайте буфер кадра
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Установить свойства буфера изображения
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

//Добавить буфер изображений на все страницы
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Приведенный выше код создает буфер изображения из файла «aspose-logo.jpg» и устанавливает его свойства, такие как верхнее поле, горизонтальное и вертикальное выравнивание. Затем штамп изображения добавляется ко всем страницам PDF-документа в качестве раздела заголовка.

## Шаг 4: Сохранение измененного PDF-документа

Как только изображение добавлено в раздел заголовка, мы можем сохранить измененный PDF-документ. Вот как:

```csharp
// Сохраните измененный PDF-документ
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

Приведенный выше код сохраняет отредактированный PDF-документ в указанный каталог.

### Пример исходного кода для заголовка Imagein с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Создать заголовок
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Установить свойства штампа
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Добавить заголовок на всех страницах
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Заключение

Поздравляем! Вы узнали, как добавить изображение в раздел заголовка PDF-документа, используя Aspose.PDF для .NET. Теперь вы можете настраивать заголовки ваших PDF-документов, добавляя изображения.
