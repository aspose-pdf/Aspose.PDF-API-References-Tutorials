---
title: Текст и изображение как абзац
linktitle: Текст и изображение как абзац
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавить текст и изображение в виде встроенных абзацев в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 530
url: /ru/net/programming-with-text/text-and-image-as-paragraph/
---

В этом руководстве объясняется, как добавить текст и изображение в виде встроенных абзацев в документ PDF с помощью Aspose.PDF для .NET. Предоставленный исходный код C# демонстрирует пошаговый процесс.

## Предпосылки

Прежде чем приступить к обучению, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования С#.
- Установлена библиотека Aspose.PDF для .NET. Вы можете получить его с веб-сайта Aspose или использовать NuGet для установки в своем проекте.

## Шаг 1: Настройте проект

Начните с создания нового проекта C# в выбранной вами интегрированной среде разработки (IDE) и добавьте ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2. Импортируйте необходимые пространства имен

Добавьте следующие директивы using в начало файла C#, чтобы импортировать необходимые пространства имен:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Шаг 3: Установите путь к каталогу документов

 Укажите путь к папке с документами с помощью`dataDir` переменная:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

## Шаг 4: Создайте новый документ и страницу

 Создать новый`Document` объект и добавьте страницу в его коллекцию страниц:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Шаг 5: Создайте TextFragment и добавьте его как абзац

 Создать`TextFragment`объект и добавьте его в коллекцию абзацев страницы:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Шаг 6. Добавьте изображение в качестве встроенного абзаца

 Создать`Aspose.Pdf.Image` объект и установите его как встроенный абзац, чтобы он отображался сразу после предыдущего абзаца:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Необязательно: установите высоту изображения
image.FixWidth = 100; // Необязательно: установите ширину изображения
page.Paragraphs.Add(image);
```

 Заменять`"aspose-logo.jpg"` с фактическим именем файла изображения и отрегулируйте дополнительную высоту и ширину изображения по желанию.

## Шаг 7. Добавьте еще один TextFragment в качестве встроенного абзаца.

 Повторно инициализируйте`TextFragment` объект с другим содержимым и добавьте его как встроенный абзац:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Шаг 8: Сохраните PDF-документ

Сохраните измененный PDF-документ:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Обязательно замените`"TextAndImageAsParagraph_out.pdf"` с желаемым именем выходного файла.

### Пример исходного кода для текста и изображения как абзаца с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создать экземпляр документа
Document doc = new Document();
// Добавить страницу в коллекцию страниц экземпляра документа
Page page = doc.Pages.Add();
// Создать TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Добавить текстовый фрагмент в коллекцию абзацев объекта Page
page.Paragraphs.Add(text);
// Создать экземпляр изображения
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Установите изображение как встроенный абзац, чтобы оно появлялось сразу после
// Объект предыдущего абзаца (TextFragment)
image.IsInLineParagraph = true;
// Укажите путь к файлу изображения
image.File = dataDir + "aspose-logo.jpg";
// Установите высоту изображения (необязательно)
image.FixHeight = 30;
// Установите ширину изображения (необязательно)
image.FixWidth = 100;
//Добавить изображение в коллекцию абзацев объекта страницы
page.Paragraphs.Add(image);
// Повторно инициализировать объект TextFragment с другим содержимым
text = new TextFragment(" Hello Again..");
// Установить TextFragment как встроенный абзац
text.IsInLineParagraph = true;
// Добавить вновь созданный TextFragment в коллекцию абзацев страницы
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Вы успешно научились добавлять текст и изображение в виде встроенных абзацев в документ PDF с помощью Aspose.PDF для .NET. В этом руководстве представлено пошаговое руководство от настройки проекта до сохранения измененного документа. Теперь вы можете включить этот код в свои собственные проекты C#, чтобы настроить макет текста и изображений в файлах PDF.