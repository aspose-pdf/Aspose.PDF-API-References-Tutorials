---
title: Создать ссылку на документ
linktitle: Создать ссылку на документ
second_title: Aspose.PDF для справочника API .NET
description: С легкостью создавайте ссылки на другие PDF-документы с помощью Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-links-and-actions/create-document-link/
---

Ссылка на другой документ в файле PDF позволяет создавать кликабельные ссылки, которые перенаправляют пользователей на другие документы PDF. С Aspose.PDF для .NET вы можете легко создавать такие ссылки, следуя следующему исходному коду:

## Шаг 1. Импортируйте необходимые библиотеки

Прежде чем начать, вам нужно импортировать необходимые библиотеки для вашего проекта C#. Вот необходимая директива импорта:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Шаг 2. Укажите путь к папке с документами.

 На этом шаге вам необходимо указать путь к папке, содержащей файл PDF, в который вы хотите добавить ссылку на другой документ. Заменять`"YOUR DOCUMENT DIRECTORY"` в следующем коде с фактическим путем к вашей папке документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 3: Откройте PDF-документ

Теперь мы откроем документ PDF, к которому мы хотим добавить ссылку на другой документ, используя следующий код:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Шаг 4: Создайте ссылку на другой документ

 На этом шаге мы создадим ссылку на другой документ, используя`LinkAnnotation` аннотация. Укажем координаты и область ссылки, а также действие перехода к внешнему документу. Вот соответствующий код:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Шаг 5: Сохраните обновленный файл

Теперь давайте сохраним обновленный PDF-файл, используя`Save` метод`document` объект. Вот соответствующий код:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Пример исходного кода для создания ссылки на документ с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Создать ссылку
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Сохранить обновленный документ
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Заключение

Поздравляем! Теперь у вас есть пошаговое руководство по созданию ссылок на другие документы с помощью Aspose.PDF для .NET. Вы можете использовать этот код для создания кликабельных ссылок в ваших PDF-файлах, перенаправляя пользователей на другие документы.

Обязательно ознакомьтесь с официальной документацией Aspose.PDF для получения дополнительной информации о расширенных функциях интерактивных ссылок.