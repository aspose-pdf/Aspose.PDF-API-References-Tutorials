---
title: Изображение в нижнем колонтитуле
linktitle: Изображение в нижнем колонтитуле
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить изображение в нижний колонтитул документа PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 130
url: /ru/net/programming-with-stamps-and-watermarks/image-in-footer/
---
В этом руководстве мы шаг за шагом расскажем, как добавить изображение в нижний колонтитул документа PDF с помощью Aspose.PDF для .NET. Мы будем использовать предоставленный исходный код C#, чтобы открыть существующий документ PDF, создать буфер изображения, установить его свойства и добавить его на все страницы документа PDF.

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
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором находится ваш PDF-документ.

## Шаг 3: Создание и добавление изображения в нижний колонтитул

Теперь, когда документ PDF загружен, мы можем создать штамп изображения и добавить его на все страницы документа. Вот как:

```csharp
// Создайте буфер кадра
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Установить свойства буфера изображения
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//Добавить буфер изображений на все страницы
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Приведенный выше код создает буфер изображения из файла «aspose-logo.jpg» и устанавливает его свойства, такие как нижнее поле, горизонтальное и вертикальное выравнивание. Затем буфер изображения добавляется ко всем страницам PDF-документа.

## Шаг 4: Сохранение измененного PDF-документа

Как только изображение добавлено в раздел нижнего колонтитула, мы можем сохранить измененный PDF-документ. Вот как:

```csharp
// Сохраните измененный PDF-документ
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

Приведенный выше код сохраняет отредактированный PDF-документ в указанный каталог.

### Пример исходного кода для изображения в нижнем колонтитуле с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Создать нижний колонтитул
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Установить свойства штампа
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Добавить нижний колонтитул на все страницы
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Сохранить обновленный файл PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы узнали, как добавить изображение в нижний колонтитул документа PDF с помощью Aspose.PDF для .NET. Теперь вы можете настроить нижние колонтитулы ваших PDF-документов, добавив изображения.
