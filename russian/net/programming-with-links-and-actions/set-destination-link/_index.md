---
title: Установить целевую ссылку
linktitle: Установить целевую ссылку
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как установить целевую ссылку в файле PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-links-and-actions/set-destination-link/
---

Из этого пошагового руководства вы узнаете, как установить ссылку назначения в файле PDF с помощью Aspose.PDF для .NET.

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

## Шаг 3: Редактирование целевой ссылки

Получите аннотацию ссылки для изменения, используя следующий код:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Вы можете настроить`[1]` индексы для выбора конкретной страницы или аннотации.

Затем отредактируйте ссылку, изменив действие ссылки и установив цель в качестве веб-адреса:

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## Шаг 4: Сохраните документ с обновленной ссылкой

Сохраните документ с обновленной ссылкой с помощью кнопки`Save` метод:

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## Шаг 5: Отображение результата

Отобразите сообщение о том, что целевая ссылка была успешно настроена, и укажите расположение сохраненного файла:

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### Пример исходного кода для установки ссылки назначения с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите PDF-файл
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Получить аннотацию первой ссылки с первой страницы документа
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Ссылка на изменение: изменить действие ссылки и установить цель как веб-адрес
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	// Сохраните документ с обновленной ссылкой
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

Поздравляем! Теперь вы знаете, как установить ссылку назначения в файле PDF с помощью Aspose.PDF для .NET. Используйте эти знания для настройки ссылок в документах PDF и создания интерактивных возможностей для пользователей.

Теперь, когда вы завершили это руководство, вы можете применить эти концепции к своим собственным проектам и дополнительно изучить функции, предлагаемые Aspose.PDF для .NET.