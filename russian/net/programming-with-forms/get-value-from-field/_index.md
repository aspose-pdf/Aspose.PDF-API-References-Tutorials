---
title: Получить значение из поля
linktitle: Получить значение из поля
second_title: Aspose.PDF для справочника API .NET
description: Легко получайте значение поля формы в ваших документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 140
url: /ru/net/programming-with-forms/get-value-from-field/
---

В этом руководстве мы покажем вам, как получить значение поля формы, используя Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Откройте документ

Откройте PDF-документ:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Шаг 3: Получить поле

Получите нужное поле формы (в этом примере мы используем поле «textbox1»):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Шаг 4: Получите значение поля

 Получить значение поля с помощью`Value` свойство:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Пример исходного кода для получения значения из поля с использованием Aspose.Words для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Получить поле
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Получить значение поля
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Заключение

В этом руководстве мы узнали, как получить значение поля формы, используя Aspose.PDF для .NET. Следуя этим шагам, вы можете легко извлечь значение определенного поля формы в своих документах PDF с помощью Aspose.PDF.