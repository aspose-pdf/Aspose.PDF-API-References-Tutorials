---
title: Динамическая форма XFA в Acro
linktitle: Динамическая форма XFA в Acro
second_title: Aspose.PDF для справочника API .NET
description: Легко конвертируйте динамические формы XFA To в стандартные формы AcroForm с помощью Aspose.PDF для .NET.
type: docs
weight: 70
url: /ru/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

В этом руководстве мы покажем вам, как преобразовать динамическую форму XFA To в AcroForm с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Во-первых, убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите динамическую форму XFA

Загрузите динамическую форму XFA:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Шаг 3: Установите тип формы как стандартный AcroForm

Установите тип формы как стандартный AcroForm:

```csharp
document.Form.Type = FormType.Standard;
```

## Шаг 4: Сохраните полученный PDF-файл

Сохраните полученный PDF:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Пример исходного кода для Dynamic XFA To Acro Form с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузить динамическую форму XFA
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Установить тип полей формы как стандартный AcroForm
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Сохраните полученный PDF-файл
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как преобразовать динамическую форму XFA в стандартную форму AcroForm с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко преобразовать свои динамические формы XFATo в AcroForms для более общего использования.