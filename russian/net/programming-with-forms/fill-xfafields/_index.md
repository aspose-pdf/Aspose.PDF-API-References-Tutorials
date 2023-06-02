---
title: Заполнить XFAFields
linktitle: Заполнить XFAFields
second_title: Aspose.PDF для справочника API .NET
description: Легко заполняйте поля XFA в документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-forms/fill-xfafields/
---

В этом руководстве мы покажем вам, как заполнять поля XFA с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Во-первых, убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите форму XFA

Загрузите форму XFA:

```csharp
Document doc = new Document(dataDir + "FillXFAFields.pdf");
```

## Шаг 3: Получите имена полей XFA

Получите имена полей XFA формы:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Шаг 4: Установите значения полей

Задайте значения поля XFA, используя имена, полученные ранее:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Шаг 5: Сохраните обновленный документ

Сохраните обновленный PDF-документ:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для заполнения XFAFields с использованием Aspose.Words для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузить форму XFA
Document doc = new Document(dataDir + "FillXFAFields.pdf");
//Получить имена полей формы XFA
string[] names = doc.Form.XFA.FieldNames;
// Установить значения полей
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
dataDir = dataDir + "Filled_XFA_out.pdf";
// Сохраните обновленный документ
doc.Save(dataDir);
Console.WriteLine("\nXFA fields filled successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как заполнять поля XFA с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко изменить значения полей XFA в своих PDF-документах с помощью Aspose.PDF.