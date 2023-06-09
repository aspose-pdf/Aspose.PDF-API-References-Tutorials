---
title: Получить значения из всех полей
linktitle: Получить значения из всех полей
second_title: Aspose.PDF для справочника API .NET
description: С легкостью получайте значения всех полей форм в ваших документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 150
url: /ru/net/programming-with-forms/get-values-from-all-fields/
---

В этом руководстве мы покажем вам, как получить значения всех полей формы в документе PDF, используя Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Откройте документ

Откройте PDF-документ:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Шаг 3: Получите значения для всех полей

Прокрутите все поля формы в документе и получите их имена и значения:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Пример исходного кода для получения значений из всех полей с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Получить значения из всех полей
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Заключение

В этом руководстве мы узнали, как получить значения всех полей формы в документе PDF с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко извлечь значения всех полей формы из ваших PDF-документов с помощью Aspose.PDF.