---
title: Добавить отметку даты и времени
linktitle: Добавить отметку даты и времени
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как легко добавлять отметку даты и времени в документы PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
В этой статье мы шаг за шагом расскажем, как добавить отметку даты и времени с помощью Aspose.PDF для .NET. Мы покажем вам, как использовать предоставленный исходный код C# для добавления отметки даты и времени в существующий документ PDF.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная среда разработки .NET.
- Библиотека Aspose.PDF для .NET загружена и указана в вашем проекте.

## Шаг 1. Настройка среды

Прежде чем вы сможете добавить отметку даты и времени в документ PDF, вам необходимо настроить среду разработки. Вот шаги, которые необходимо выполнить:

1. Откройте свою любимую IDE (интегрированную среду разработки).
2. Создайте новый проект C#.
3. Убедитесь, что вы добавили ссылку на библиотеку Aspose.PDF для .NET.

## Шаг 2: Добавление библиотеки Aspose.PDF

Библиотека Aspose.PDF для .NET необходима для работы с PDF-документами в вашем проекте.

## Шаг 3: Загрузка PDF-документа

Первым шагом к добавлению отметки даты и времени является загрузка существующего документа PDF в ваш проект. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Откройте документ
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором находится ваш PDF-документ.

## Шаг 4: Создание отметки даты и времени

Теперь, когда вы загрузили документ

  PDF, вы можете создать отметку даты и времени для добавления. Вот как это сделать:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Создать текстовый буфер
TextStamp textStamp = new TextStamp(annotationText);
```

Приведенный выше код создает новый текстовый буфер, содержащий текущую дату и время.

## Шаг 5: Настройка свойств штампа

Перед добавлением штампа в документ PDF вы можете настроить различные свойства штампа, такие как поля, выравнивание по горизонтали и вертикали и т. д. Вот как это сделать:

```csharp
// Установить свойства буфера
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Вы можете настроить эти свойства в соответствии с вашими потребностями.

## Шаг 6: Добавьте штамп в PDF

Теперь, когда отметка даты и времени готова, вы можете добавить ее на определенную страницу документа PDF. Вот как:

```csharp
// Добавьте марку в коллекцию марок страницы
pdfDocument.Pages[1].AddStamp(textStamp);
```

Приведенный выше код добавляет штамп на первую страницу PDF-документа. При необходимости вы можете указать другую страницу.

## Шаг 7: Сохраните выходной документ

После того, как вы добавили отметку даты и времени, вы можете сохранить измененный PDF-документ. Вот как:

```csharp
// Сохраните выходной документ
pdfDocument.Save(dataDir);
```

Приведенный выше код сохраняет отредактированный PDF-документ в указанный каталог.

### Пример исходного кода для добавления штампа даты и времени с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Создать текстовый штамп
TextStamp textStamp = new TextStamp(annotationText);

// Установить свойства штампа
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Добавление марки в коллекцию марок
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Сохранить выходной документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Заключение

Поздравляем! Вы узнали, как добавить отметку даты и времени с помощью Aspose.PDF для .NET. Теперь вы можете применить эти знания в своих собственных проектах, чтобы добавлять метки даты и времени в документы PDF.
