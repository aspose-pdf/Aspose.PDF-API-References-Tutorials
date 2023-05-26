---
title: Редактировать страницу
linktitle: Редактировать страницу
second_title: Aspose.PDF для справочника API .NET
description: В этой статье объясняется, как редактировать страницу PDF с помощью Aspose.PDF для .NET, включая пошаговые инструкции и пример исходного кода.
type: docs
weight: 120
url: /ru/net/annotations/redactpage/
---
Если вы хотите отредактировать конфиденциальную информацию из документа PDF с помощью Aspose.PDF для .NET, вам повезло! Вот пошаговое руководство для начала:

## В коде укажите путь к каталогу, в котором находится ваш PDF-документ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Откройте PDF-документ:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Создайте экземпляр RedactionAnnotation для определенной области страницы:

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## Установите цвет заливки, цвет границы и цвет текста аннотации редактирования:

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## Установите текст, который будет напечатан на аннотации редактирования, и его выравнивание:

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Повторите наложенный текст поверх аннотации редактирования:

```csharp
annot.Repeat = true;
```

## Добавьте аннотацию в коллекцию аннотаций первой страницы:

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## Выровняйте аннотацию и отредактируйте содержимое страницы, т. е. удалите текст и изображения под отредактированной аннотацией:

```csharp
annot.Redact();
```

## Задайте путь и имя выходного PDF-файла:

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## Сохраните документ PDF с отредактированной страницей:

```csharp
doc.Save(dataDir);
```

Вот и все! Вы успешно отредактировали страницу своего PDF-документа с помощью Aspose.PDF для .NET.

### Пример исходного кода для Redact Page с использованием Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document doc = new Document(dataDir + "input.pdf");

// Создать экземпляр RedactionAnnotation для определенной области страницы
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// Текст для печати на редактируемой аннотации
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Редактировать Наложение текста поверх редактируемой аннотации
annot.Repeat = true;
// Добавить аннотацию в коллекцию аннотаций первой страницы
doc.Pages[1].Annotations.Add(annot);
// Сглаживает аннотации и редактирует содержимое страницы (т. е. удаляет текст и изображения).
// Под отредактированной аннотацией)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```