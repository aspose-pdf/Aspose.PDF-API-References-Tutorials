---
title: Добавить гиперссылку
linktitle: Добавить гиперссылку
second_title: Aspose.PDF для справочника API .NET
description: С легкостью добавляйте интерактивные гиперссылки в файлы PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-links-and-actions/add-hyperlink/
---

Добавление гиперссылок в документ PDF позволяет создавать интерактивные гиперссылки на другие страницы, веб-сайты или места назначения в документе. С помощью Aspose.PDF для .NET вы можете легко добавлять гиперссылки, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам нужно указать путь к папке, содержащей PDF-файл, на который вы хотите добавить гиперссылку. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы откроем документ PDF, к которому мы хотим добавить гиперссылку, используя следующий код:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## Шаг 4: Создайте ссылку

 На этом шаге мы создадим гиперссылку, используя`LinkAnnotation` аннотация. Мы укажем контактные данные и область ссылки, тип ссылки и содержание ссылки. Вот соответствующий код:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## Шаг 5: Добавьте дополнительный текст

 В дополнение к гиперссылке мы также можем добавить дополнительный текст, используя`FreeTextAnnotation` аннотация. Мы укажем координаты, внешний вид текста и содержание текста. Вот соответствующий код:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## Шаг 6: Сохраните обновленный файл

Теперь давайте сохраним обновленный PDF-файл, используя`Save` метод`document` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### Пример исходного кода для добавления гиперссылки с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document document = new Document(dataDir + "AddHyperlink.pdf");
// Создать ссылку
Page page = document.Pages[1];
//Создать объект аннотации «Ссылка»
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// Создайте объект границы для LinkAnnotation
Border border = new Border(link);
// Установите значение ширины границы как 0
border.Width = 0;
// Установите границу для LinkAnnotation
link.Border = border;
// Укажите тип ссылки как удаленный URI
link.Action = new GoToURIAction("www.aspose.com");
// Добавить аннотацию ссылки в коллекцию аннотаций первой страницы PDF-файла
page.Annotations.Add(link);
// Создание произвольной текстовой аннотации
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// Строка, которая будет добавлена как произвольный текст
textAnnotation.Contents = "Link to Aspose website";
// Установите границу для произвольной текстовой аннотации
textAnnotation.Border = border;
// Добавить аннотацию FreeText в коллекцию аннотаций первой страницы документа
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// Сохранить обновленный документ
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по добавлению гиперссылок с помощью Aspose.PDF для .NET. Вы можете использовать этот код для создания интерактивных ссылок в ваших документах PDF.