---
title: Получить текст гиперссылки
linktitle: Получить текст гиперссылки
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как извлечь текст гиперссылки из файла PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-links-and-actions/get-hyperlink-text/
---

Из этого пошагового руководства вы узнаете, как извлечь текст из гиперссылок в файле PDF с помощью Aspose.PDF для .NET.

## Шаг 1. Настройка среды

Убедитесь, что вы настроили среду разработки с проектом C# и соответствующими ссылками на Aspose.PDF.

## Шаг 2: Загрузка файла PDF

Установите путь к каталогу ваших документов и загрузите файл PDF, используя следующий код:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Загрузите PDF-файл
Document document = new Document(dataDir + "input.pdf");
```

## Шаг 3. Навигация по страницам документа

 Пролистайте каждую страницу документа, используя`foreach` петля:

```csharp
foreach(Page page in document.Pages)
{
     // Показать аннотации к ссылкам
     ShowLinkAnnotations(page);
}
```

## Шаг 4: Обработка ошибок

Добавьте обработку ошибок, чтобы поймать любое исключение и отобразить соответствующее сообщение об ошибке:

```csharp
catch (Exception ex)
{
     Console.WriteLine(ex.Message);
}
```

### Пример исходного кода для получения текста гиперссылки с использованием Aspose.PDF для .NET 
```csharp
try
{
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите PDF-файл
	Document document = new Document(dataDir + "input.pdf");
	// Итерация по каждой странице PDF
	foreach (Page page in document.Pages)
	{
		// Показать аннотацию к ссылке
		ShowLinkAnnotations(page);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Заключение

Поздравляем! Теперь вы знаете, как извлечь текст гиперссылки из файла PDF с помощью Aspose.PDF для .NET. Вы можете использовать эти знания для работы с гиперссылками в своих проектах и автоматизации задач, связанных с файлами PDF.

Теперь, когда вы завершили это руководство, вы можете применить эти концепции к своим собственным проектам и дополнительно изучить функции, предлагаемые Aspose.PDF для .NET.