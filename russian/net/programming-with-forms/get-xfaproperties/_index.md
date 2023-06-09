---
title: Получить свойства XFA
linktitle: Получить свойства XFA
second_title: Aspose.PDF для справочника API .NET
description: Легко получайте свойства XFA полей форм в ваших документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 160
url: /ru/net/programming-with-forms/get-xfaproperties/
---

В этом руководстве мы покажем вам, как получить свойства XFA полей формы в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите форму XFA

Загрузите форму XFA из документа PDF:

```csharp
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
```

## Шаг 3: Получите имена полей

Получить имена полей XFA:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Шаг 4: Установите значения полей

Установите значения для полей XFA:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Шаг 5: Получить положение полей

Получить положение полей XFA:

```csharp
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
```

## Шаг 6: Сохраните обновленный документ

Сохраните обновленный PDF-документ:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Пример исходного кода для получения XFAProperties с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузить форму XFA
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
string[] names = doc.Form.XFA.FieldNames;
// Установить значения полей
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
// Получить позицию поля
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
// Получить позицию поля
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
dataDir = dataDir + "Filled_XFA_out.pdf";
// Сохраните обновленный документ
doc.Save(dataDir);
Console.WriteLine("\nXFA fields properties retrieved successfully.\nFile saved at " + dataDir);
```

## Заключение

В этом руководстве мы узнали, как получить свойства XFA полей формы в документе PDF с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко извлечь информацию о полях XFA, например позиции, из документов PDF с помощью Aspose.PDF.