---
title: Штампы с номерами страниц
linktitle: Штампы с номерами страниц
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как добавлять штампы с номерами страниц в документ PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 160
url: /ru/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
В этом руководстве мы шаг за шагом расскажем, как добавить штампы с номерами страниц в документ PDF с помощью Aspose.PDF для .NET. Мы будем использовать предоставленный исходный код C#, чтобы открыть существующий PDF-документ, создать штамп с номером страницы, задать его свойства и добавить его на определенную страницу в PDF-документе.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная среда разработки .NET.
- Библиотека Aspose.PDF для .NET загружена и указана в вашем проекте.

## Шаг 2: Загрузка существующего документа PDF

Первым шагом является загрузка существующего документа PDF в ваш проект. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Откройте существующий PDF-документ
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором находится ваш PDF-документ.

## Шаг 3: Создание и настройка штампа нумерации страниц

Теперь, когда документ PDF загружен, мы можем создать буфер нумерации страниц и настроить его в соответствии с нашими потребностями. Вот как:

```csharp
// Создать буфер номеров страниц
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Определите, находится ли буфер в фоновом режиме или нет
pageNumberStamp.Background = false;

// Формат буфера нумерации страниц
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Нижнее поле буфера нумерации страниц
pageNumberStamp.BottomMargin = 10;

// Горизонтальное выравнивание буфера нумерации страниц
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Начальный номер нумерации страниц
pageNumberStamp.StartingNumber = 1;

// Установить свойства текста буфера номера страницы
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Приведенный выше код создает штамп номера страницы с такими свойствами, как формат номера страницы, нижнее поле, горизонтальное выравнивание, начальный номер и свойства текста.

## Шаг 4. Добавление штампа номера страницы на определенную страницу

После настройки штампа номера страницы мы можем добавить его на определенную страницу документа PDF. Вот как:

```csharp
// Добавить буфер номеров страниц на определенную страницу
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Приведенный выше код добавляет штамп номера страницы на первую страницу документа PDF. При необходимости вы можете изменить номер страницы.

## Шаг 5: Сохранение измененного PDF-документа

После добавления штампа номера страницы в документ PDF мы можем сохранить измененный документ PDF. Вот как:

```csharp
// Сохраните измененный PDF-документ
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором вы хотите сохранить отредактированный PDF-документ.

### Пример исходного кода для штампов номеров страниц с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Открыть документ
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Создать штамп с номером страницы
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Является ли штамп фоном
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Установить свойства текста
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Добавить штамп на определенную страницу
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Сохранить выходной документ
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Заключение

Поздравляем! Вы узнали, как добавлять штампы с номерами страниц в документ PDF с помощью Aspose.PDF для .NET. Теперь вы можете персонализировать свои PDF-документы, добавляя четкие и информативные номера страниц.
