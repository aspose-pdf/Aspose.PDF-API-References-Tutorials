---
title: Невидимая аннотация
linktitle: Невидимая аннотация
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как невидимо аннотировать PDF-файлы с помощью исходного кода C# с помощью Aspose.PDF для .NET. Пошаговое руководство.
type: docs
weight: 100
url: /ru/net/annotations/invisibleannotation/
---
## Понимание аннотаций в документах PDF

Аннотации в документах PDF — это мощная функция, позволяющая добавлять в документ дополнительную информацию или примечания без изменения фактического содержимого. Их можно использовать для выделения текста, привлечения внимания к определенным областям документа или добавления комментариев или отзывов.

Существует множество различных типов аннотаций, которые можно использовать в документах PDF, в том числе:

- Текстовые аннотации
- Аннотации ссылок
- Аннотации штампов
- Звуковые аннотации
- Аннотации вложенных файлов
- и многое другое

## Создание невидимой аннотации в документе PDF с использованием Aspose.PDF для .NET

 Чтобы создать невидимую аннотацию в документе PDF с помощью Aspose.PDF для .NET, нам сначала нужно создать`FreeTextAnnotation` объекта и указать расположение и размер аннотации.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 В приведенном выше коде мы создаем`FreeTextAnnotation`объекта и укажите расположение аннотации на странице 2 документа PDF. Мы также указываем тип, размер и цвет шрифта для текста, который будет отображаться в аннотации.

## Добавление характеристик к невидимой аннотации

Затем мы можем добавить к аннотации некоторые характеристики, такие как цвет границы, цвет фона или непрозрачность.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

В приведенном выше коде мы установили красный цвет границы аннотации.

## Установка флагов аннотаций

После того, как мы создали аннотацию и установили ее характеристики, мы можем указать флаги аннотации. В этом уроке мы хотим, чтобы аннотацию можно было распечатать, но нельзя было просмотреть.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
```

## Сохранение измененного PDF-документа

Наконец, мы можем сохранить измененный PDF-документ с новой невидимой аннотацией.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Пример исходного кода для невидимой аннотации с использованием Aspose.PDF для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1