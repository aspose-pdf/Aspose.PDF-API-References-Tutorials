---
title: Установить целевую ссылку
linktitle: Установить целевую ссылку
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как установить целевую ссылку в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-links-and-actions/set-target-link/
---

Из этого пошагового руководства вы узнаете, как установить целевую ссылку в файле PDF с помощью Aspose.PDF для .NET.

## Шаг 1. Настройка среды

Убедитесь, что вы настроили среду разработки с проектом C# и соответствующими ссылками на Aspose.PDF.

## Шаг 2: Загрузка файла PDF

Установите путь к каталогу ваших документов и загрузите файл PDF, используя следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Загрузите PDF-файл
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Шаг 3: Редактирование целевой ссылки

Получите аннотацию ссылки для изменения, используя следующий код:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Вы можете настроить`[1]` индексы для выбора конкретной страницы или аннотации.

Затем обновите место назначения, не обновляя файл:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

И если вы также хотите обновить файл:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Шаг 4: Сохраните документ с обновленной ссылкой

Сохраните документ с обновленной ссылкой с помощью кнопки`Save` метод:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Шаг 5: Отображение результата

Вывести сообщение о том, что целевая ссылка была успешно настроена, и указать расположение сохраненного файла:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Пример исходного кода для установки целевой ссылки с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите PDF-файл
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Пункт назначения обновления следующей строки, не обновлять файл
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Файл обновления следующей строки
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Сохраните документ с обновленной ссылкой
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

Поздравляем! Теперь вы знаете, как установить целевую ссылку в файле PDF с помощью Aspose.PDF для .NET. Используйте эти знания для настройки ссылок в документах PDF и создания интерактивных возможностей для пользователей.

Теперь, когда вы завершили это руководство, вы можете применить эти концепции к своим собственным проектам и дополнительно изучить функции, предлагаемые Aspose.PDF для .NET.