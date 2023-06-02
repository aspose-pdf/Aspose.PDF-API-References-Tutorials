---
title: Изменить поле формы
linktitle: Изменить поле формы
second_title: Aspose.PDF для справочника API .NET
description: С легкостью редактируйте поля форм в своих документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 190
url: /ru/net/programming-with-forms/modify-form-field/
---

В этом руководстве мы покажем вам, как редактировать поле формы в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ

Загрузите существующий PDF-документ:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Шаг 3: Получите поле формы

Получите поле формы, которое вы хотите отредактировать:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Шаг 4. Измените значение поля

Измените значение поля формы:

```csharp
textBoxField.Value = "New Value";
```

## Шаг 5: Изменить свойства поля

При необходимости измените дополнительные свойства поля формы. Например, вы можете сделать его доступным только для чтения:

```csharp
textBoxField.ReadOnly = true;
```

## Шаг 6: Сохраните отредактированный документ

Сохраните измененный PDF-документ:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для изменения поля формы с использованием Aspose.Words для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Получить поле
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Изменить значение поля
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как редактировать поле формы в документе PDF с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко перейти к определенному полю, изменить его значение и настроить его свойства по мере необходимости.