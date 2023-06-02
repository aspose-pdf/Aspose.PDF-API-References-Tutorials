---
title: Сгладить формы
linktitle: Сгладить формы
second_title: Aspose.PDF для справочника API .NET
description: С легкостью сглаживайте формы в документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 100
url: /ru/net/programming-with-forms/flatten-forms/
---

В этом руководстве мы покажем вам, как выравнивать формы с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Во-первых, убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходную PDF-форму

Загрузите исходную PDF-форму:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Шаг 3: Сгладьте формы

Сначала проверьте, есть ли в документе поля формы. Если это так, выполните итерацию по каждому полю и примените сглаживание:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Шаг 4: Сохраните обновленный документ

Сохраните обновленный PDF-документ:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для Flatten Forms с использованием Aspose.Words для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузить исходную PDF-форму
Document doc = new Document(dataDir + "input.pdf");
// Сгладить формы
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Сохраните обновленный документ
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как выравнивать формы с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко свести формы в документах PDF, сделав поля недоступными для редактирования и объединив аннотации с содержимым документа.