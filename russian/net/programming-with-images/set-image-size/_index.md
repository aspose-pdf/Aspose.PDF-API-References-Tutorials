---
title: Установить размер изображения
linktitle: Установить размер изображения
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по установке размера изображения в документе PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 270
url: /ru/net/programming-with-images/set-image-size/
---

В этом руководстве мы расскажем, как установить размер изображения в документе PDF с помощью Aspose.PDF для .NET. Выполните следующие действия, чтобы легко выполнить эту операцию.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная и настроенная Visual Studio или любая другая среда разработки.
- Базовые знания языка программирования C#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете скачать его с официального сайта Aspose.

## Шаг 1: Создание документа PDF

Для начала используйте следующий код для создания нового PDF-документа:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Создание экземпляра объекта Document
Document doc = new Document();

// Добавить страницу в коллекцию страниц файла PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Шаг 2: Добавлено изображение

Далее мы добавим изображение на страницу документа PDF. Используйте следующий код:

```csharp
// Создать экземпляр изображения
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Установите ширину и высоту изображения в пунктах
img. FixWidth = 100;
img. FixHeight = 100;

// Установите тип изображения на неизвестный (неизвестный)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Путь к исходному файлу изображения
img.File = dataDir + "aspose-logo.jpg";

// Добавьте изображение в коллекцию абзацев страницы
page.Paragraphs.Add(img);
```

Обязательно укажите правильный путь к исходному файлу изображения.

## Шаг 3: Настройка свойств страницы

Наконец, мы установим свойства страницы, включая ее ширину и высоту. Используйте следующий код:

```csharp
// Установить свойства страницы
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Пример исходного кода для установки размера изображения с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать объект документа
Document doc = new Document();
//добавить страницу в коллекцию страниц файла PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Создать экземпляр изображения
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Установите ширину и высоту изображения в точках
img.FixWidth = 100;
img.FixHeight = 100;
// Установите тип изображения как SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Путь к исходному файлу
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Установить свойства страницы
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// сохранить полученный файл PDF
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы успешно установили размер изображения в документе PDF, используя Aspose.PDF для .NET. Теперь вы можете применить этот метод к своим собственным проектам, чтобы настроить размер изображений в файлах PDF.