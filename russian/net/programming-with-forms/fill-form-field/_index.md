---
title: Заполнить поле формы
linktitle: Заполнить поле формы
second_title: Aspose.PDF для справочника API .NET
description: С легкостью заполняйте поля форм в документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 80
url: /ru/net/programming-with-forms/fill-form-field/
---

В этом руководстве мы покажем вам, как заполнить поле формы с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Во-первых, убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

Откройте существующий PDF-документ:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Шаг 3: Получить поле

Получите нужное поле формы (в этом примере мы используем поле «textbox1»):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Шаг 4. Измените значение поля

Измените значение поля на желаемое значение:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Шаг 5: Сохраните обновленный документ

Сохраните обновленный PDF-документ:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для заполнения поля формы с использованием Aspose.Words для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// Получить поле
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Изменить значение поля
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как заполнить поле формы с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко изменить значения полей формы в своих PDF-документах с помощью Aspose.PDF.