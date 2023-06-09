---
title: Получить поля из региона
linktitle: Получить поля из региона
second_title: Aspose.PDF для справочника API .NET
description: С легкостью добавляйте поля из определенного региона в свои PDF-документы с помощью Aspose.PDF для .NET.
type: docs
weight: 130
url: /ru/net/programming-with-forms/get-fields-from-region/
---

В этом руководстве мы покажем вам, как получить поля определенного региона в документе PDF с помощью Aspose.PDF для .NET. Мы объясним исходный код C# шаг за шагом, чтобы помочь вам в этом процессе.

## Шаг 1: Подготовка

Убедитесь, что вы импортировали необходимые библиотеки и указали путь к каталогу ваших документов:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Откройте файл PDF

Откройте PDF-файл:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Шаг 3: Создайте прямоугольный объект, чтобы ограничить область

Создайте прямоугольный объект, чтобы ограничить область, в которой вы хотите получить поля:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Шаг 4: Получите форму PDF

Получить PDF-форму документа:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Шаг 5: Получите поля в прямоугольной области

Получить поля, расположенные в указанной прямоугольной области:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Шаг 6. Отображение имен и значений полей

Переберите полученные поля и отобразите их имена и значения:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Пример исходного кода для получения полей из региона с использованием Aspose.PDF для .NET 
```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Открыть PDF-файл
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Создайте прямоугольный объект, чтобы получить поля в этой области
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Получить PDF-форму
Aspose.Pdf.Forms.Form form = doc.Form;
//Получить поля в прямоугольной области
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Отображение имен и значений полей
foreach (Field field in fields)
{
	// Показать свойства размещения изображения для всех мест размещения
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Заключение

В этом руководстве мы узнали, как получить поля определенного региона в документе PDF с помощью Aspose.PDF для .NET. Следуя этим шагам, вы можете легко извлечь поля, расположенные в заданной прямоугольной области вашего документа PDF, с помощью Aspose.PDF.