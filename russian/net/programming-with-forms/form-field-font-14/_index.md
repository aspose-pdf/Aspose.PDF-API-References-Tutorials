---
title: Шрифт поля формы 14
linktitle: Шрифт поля формы 14
second_title: Aspose.PDF для справочника API .NET
description: Легко настраивайте шрифт полей форм в ваших документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 110
url: /ru/net/programming-with-forms/form-field-font-14/
---

В этом руководстве мы покажем вам, как настроить шрифт поля формы с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Во-первых, убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Откройте документ

Откройте существующий PDF-документ:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Шаг 3: Получите конкретное поле формы

Получите нужное поле формы (в этом примере мы используем поле «textbox1»):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Шаг 4: Создайте объект шрифта

Создайте объект шрифта для нового шрифта, который вы хотите использовать (например, «ComicSansMS»):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Шаг 5. Настройте информацию о шрифте для поля формы

Настройте информацию о шрифте для поля формы, используя созданный ранее шрифт:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Шаг 6: Сохраните обновленный документ

Сохраните обновленный PDF-документ:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Пример исходного кода для шрифта поля формы 14 с использованием Aspose.Words для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть документ
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
//Получить конкретное поле формы из документа
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Создать объект шрифта
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Установите информацию о шрифте для поля формы
// Field.DefaultAppearance = новый Aspose.Pdf.Forms.in.DefaultAppearance (шрифт, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Сохранить обновленный документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как настроить шрифт поля формы с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко указать шрифт и размер шрифта для полей форм в ваших PDF-документах с помощью Aspose.PDF.