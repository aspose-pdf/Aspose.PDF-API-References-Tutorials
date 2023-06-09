---
title: Переместить поле формы
linktitle: Переместить поле формы
second_title: Aspose.PDF для справочника API .NET
description: Легко перемещайте поля форм в ваших документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 200
url: /ru/net/programming-with-forms/move-form-field/
---

В этом руководстве мы покажем вам, как переместить поле формы в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ

Загрузите существующий PDF-документ:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Шаг 3: Получите поле формы

Получите поле формы, которое вы хотите переместить:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Шаг 4: Изменить местоположение поля

Измените расположение поля формы, определив новую прямоугольную область:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Шаг 5: Сохраните отредактированный документ

Сохраните измененный PDF-документ:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Пример исходного кода для перемещения поля формы с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Получить поле
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Изменить местоположение поля
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Сохранить измененный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как переместить поле формы в документе PDF с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко перейти к определенному полю и изменить его местоположение по мере необходимости.