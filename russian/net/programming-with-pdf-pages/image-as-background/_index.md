---
title: Установить изображение в качестве фона
linktitle: Установить изображение в качестве фона
second_title: Aspose.PDF для справочника API .NET
description: Пошаговое руководство по установке изображения в качестве фона страницы в документе PDF с использованием Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-pdf-pages/image-as-background/
---
В этом руководстве мы пошагово проведем вас через процесс установки изображения в качестве фона страницы с помощью Aspose.PDF для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как добавить изображение в качестве фона страницы в документ PDF с помощью Aspose.PDF для .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:

- Базовые знания языка программирования C#
- Aspose.PDF для .NET, установленный в вашей среде разработки

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это место, где вы хотите сохранить отредактированный PDF-документ. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создайте новый документ
 Затем вы можете создать новый объект Document, используя`Document` сорт.

```csharp
Document doc = new Document();
```

## Шаг 3. Добавьте новую страницу в документ.
 Теперь вы можете добавить новую страницу в объект Document с помощью`Add()` метод`Pages` сорт.

```csharp
Page page = doc.Pages.Add();
```

## Шаг 4: Создайте объект фонового артефакта
Затем вы можете создать новый объект BackgroundArtifact для установки фонового изображения.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Шаг 5: Добавьте фон на страницу
 Затем вы можете добавить объект BackgroundArtifact в коллекцию артефактов страницы, используя метод`Artifacts` собственность`Page` сорт.

```csharp
page. Artifacts. Add(background);
```

## Шаг 6: Сохраните PDF-документ
 Наконец, вы можете сохранить документ PDF в файл, используя`Save()` метод`Document`сорт. Обязательно укажите правильный путь и имя файла.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Пример исходного кода для изображения в качестве фона с использованием Aspose.PDF для .NET 

```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Создайте новый объект документа
Document doc = new Document();
// Добавить новую страницу в объект документа
Page page = doc.Pages.Add();
// Создать объект фонового артефакта
BackgroundArtifact background = new BackgroundArtifact();
// Укажите изображение для объекта backgroundartifact
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Добавить backgroundartifact в коллекцию артефактов страницы
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Сохраните документ
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Заключение
В этом уроке мы узнали, как установить изображение в качестве фона страницы в документе PDF с помощью Aspose.PDF для .NET. Следуя этому пошаговому руководству, вы сможете легко добавить фоновое изображение в свои PDF-документы. Aspose.PDF предлагает мощный и гибкий API для работы с файлами PDF, включая настройку фона страницы. Теперь вы можете применять эту функцию в своих проектах для создания PDF-документов с пользовательскими фоновыми изображениями.
