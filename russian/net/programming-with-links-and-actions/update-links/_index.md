---
title: Обновить ссылки
linktitle: Обновить ссылки
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как обновить ссылки в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 120
url: /ru/net/programming-with-links-and-actions/update-links/
---

Узнайте, как обновить ссылки в файле PDF с помощью Aspose.PDF для .NET, из этого пошагового руководства.

## Шаг 1. Настройка среды

Убедитесь, что вы настроили среду разработки с проектом C# и соответствующими ссылками на Aspose.PDF.

## Шаг 2: Загрузка файла PDF

Установите путь к каталогу ваших документов и загрузите файл PDF, используя следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Загрузите PDF-файл
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## Шаг 3: Редактирование ссылки

Получите аннотацию ссылки для изменения, используя следующий код:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Вы можете настроить`[1]` индексы для выбора конкретной страницы или аннотации.

Затем измените ссылку, изменив место назначения:

```csharp
GoToAction goToAction = (GoToAction)linkAnnot.Action;
goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
```

Первый параметр представляет тему документа, второй — номер целевой страницы. Пятый аргумент — коэффициент масштабирования при отображении соответствующей страницы. Если установлено значение 2, страница будет отображаться с увеличением 200%.

## Шаг 4: Сохраните документ с обновленной ссылкой

Сохраните документ с обновленной ссылкой с помощью кнопки`Save` метод:

```csharp
dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
doc.Save(dataDir);
```

## Шаг 5: Отображение результата

Вывести сообщение об успешном обновлении ссылок и указать расположение сохраненного файла:

```csharp
Console.WriteLine("\nLinks updated successfully.\nFile saved to location: " + dataDir);
```

### Пример исходного кода для ссылок на обновление с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите PDF-файл
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Получить аннотацию первой ссылки с первой страницы документа
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Ссылка модификации: изменить назначение ссылки
	GoToAction goToAction = (GoToAction)linkAnnot.Action;
	// Укажите место назначения для объекта ссылки
	// Первый параметр — объект документа, второй — номер целевой страницы.
	// Аргумент 5ht — это коэффициент масштабирования при отображении соответствующей страницы. При использовании 2 страница будет отображаться с увеличением 200%.
	goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
	dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
	// Сохраните документ с обновленной ссылкой
	doc.Save(dataDir);
	Console.WriteLine("\nLinks updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

Поздравляем! Теперь вы знаете, как обновлять ссылки в файле PDF с помощью Aspose.PDF для .NET. Используйте эти знания для настройки ссылок в документах PDF и создания интерактивных возможностей для пользователей.

Теперь, когда вы завершили это руководство, вы можете применить эти концепции к своим собственным проектам и дополнительно изучить функции, предлагаемые Aspose.PDF для .NET.