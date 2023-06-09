---
title: Создать ссылку на приложение
linktitle: Создать ссылку на приложение
second_title: Aspose.PDF для справочника API .NET
description: С легкостью создавайте ссылки на приложения в своих PDF-файлах с помощью Aspose.PDF для .NET.
type: docs
weight: 20
url: /ru/net/programming-with-links-and-actions/create-application-link/
---

Создание ссылки на приложение в документе PDF позволяет создавать ссылки на внешние приложения, такие как исполняемые файлы или URL-адреса. С помощью Aspose.PDF для .NET вы можете легко создавать ссылки на приложения, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Шаг 2. Укажите путь к папке с документами.

На этом шаге вам нужно указать путь к папке, содержащей файл PDF, в который вы хотите добавить ссылку на приложение. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы откроем документ PDF, в который мы хотим добавить ссылку на приложение, используя следующий код:

```csharp
Document document = new Document(dataDir + "CreateApplicationLink.pdf");
```

## Шаг 4: Создайте ссылку на приложение

 На этом шаге мы создадим ссылку на приложение, используя`LinkAnnotation` аннотация. Укажем координаты и область ссылки, а также действие запуска приложения. Вот соответствующий код:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
```

## Шаг 5: Сохраните обновленный файл

Теперь давайте сохраним обновленный PDF-файл, используя`Save` метод`document` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "CreateApplicationLink_out.pdf";
document. Save(dataDir);
```

### Пример исходного кода для создания ссылки на приложение с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document document = new Document( dataDir + "CreateApplicationLink.pdf");
// Создать ссылку
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new LaunchAction(document, dataDir + "CreateApplicationLink.pdf");
page.Annotations.Add(link);
dataDir = dataDir + "CreateApplicationLink_out.pdf";
// Сохранить обновленный документ
document.Save(dataDir);
Console.WriteLine("\nApplication link created successfully.\nFile saved at " + dataDir);
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по созданию ссылок на приложения с помощью Aspose.PDF для .NET. Вы можете использовать этот код для добавления ссылок на внешние приложения в ваши PDF-документы.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях интерактивных ссылок.