---
title: Добавить текстовый штамп
linktitle: Добавить текстовый штамп
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как легко добавлять текстовые штампы в документы PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 50
url: /ru/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
В этом руководстве мы шаг за шагом расскажем, как добавить текстовую метку в документ PDF с помощью Aspose.PDF для .NET. Мы покажем вам, как использовать предоставленный исходный код C# для добавления настраиваемого текстового штампа на определенную страницу документа PDF.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная среда разработки .NET.
- Библиотека Aspose.PDF для .NET загружена и указана в вашем проекте.

## Шаг 2: Загрузка документа PDF

Первым шагом является загрузка существующего документа PDF в ваш проект. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Откройте документ
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором находится ваш PDF-документ.

## Шаг 3: Создание текстового буфера

Теперь, когда вы загрузили PDF-документ, вы можете создать текстовый штамп для добавления. Вот как это сделать:

```csharp
// Создайте текстовый буфер
TextStamp textStamp = new TextStamp("Example Stamp");
```

Приведенный выше код создает новый текстовый буфер, содержащий указанный текст.

## Шаг 4. Настройка свойств текстового штампа

Прежде чем добавить текстовый штамп в документ PDF, вы можете настроить различные свойства штампа, такие как фон, положение, поворот, шрифт, размер и т. д. Вот как это сделать:

```csharp
// Настройка свойств текстового буфера
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Вы можете настроить эти свойства в соответствии с вашими потребностями.

## Шаг 5: Добавьте текстовую марку в PDF

Теперь, когда текстовый штамп готов, вы можете добавить его на определенную страницу документа PDF. Вот как:

```csharp
// Добавить текстовый буфер на определенную страницу
pdfDocument.Pages[1].AddStamp(textStamp);
```

Приведенный выше код добавляет текстовую метку на первую страницу документа PDF. При необходимости вы можете указать другую страницу.

## Шаг 6: Сохраните выходной документ

После того, как вы добавили текстовый штамп, вы можете сохранить отредактированный PDF-документ. Вот как:

```csharp
// Сохраните выходной документ
pdfDocument.Save(dataDir);
```

Приведенный выше код сохраняет измененный PDF-документ в указанном каталоге.

### Пример исходного кода для добавления текстовой отметки с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Создать текстовый штамп
TextStamp textStamp = new TextStamp("Sample Stamp");

// Установить, является ли штамп фоном
textStamp.Background = true;

// Установить происхождение
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Повернуть штамп
textStamp.Rotate = Rotation.on90;

// Установить свойства текста
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Добавить штамп на определенную страницу
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Сохранить выходной документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Заключение

Поздравляем! Вы узнали, как добавить текстовый штамп с помощью Aspose.PDF для .NET. Теперь вы можете применить эти знания в своих проектах, чтобы добавлять собственные текстовые штампы в документы PDF.
