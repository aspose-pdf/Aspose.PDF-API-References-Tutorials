---
title: Удалить поле формы
linktitle: Удалить поле формы
second_title: Aspose.PDF для справочника API .NET
description: Легко удаляйте ненужные поля форм из ваших PDF-документов с помощью Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-forms/delete-form-field/
---

В этом руководстве мы покажем вам, как удалить поле формы с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Во-первых, убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

Откройте существующий PDF-документ:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Шаг 3. Удалить конкретное поле

Удалить конкретное поле формы, используя его имя:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Шаг 4: Сохраните отредактированный документ

Сохраните измененный PDF-документ:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для удаления поля формы с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Удалить конкретное поле по имени
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Сохранить измененный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как удалить поле формы с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко удалить ненужные поля формы из ваших PDF-документов с помощью Aspose.PDF.