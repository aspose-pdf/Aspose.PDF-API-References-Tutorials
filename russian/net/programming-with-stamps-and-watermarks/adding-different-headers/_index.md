---
title: Добавление разных заголовков
linktitle: Добавление разных заголовков
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как легко добавлять разные заголовки на каждую страницу ваших PDF-документов с помощью Aspose.PDF для .NET.
type: docs
weight: 30
url: /ru/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
В этом руководстве мы шаг за шагом покажем вам, как добавлять различные заголовки в документ PDF с помощью Aspose.PDF для .NET. Мы покажем вам, как использовать предоставленный исходный код C# для добавления настраиваемых заголовков на каждую страницу документа PDF.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная среда разработки .NET.
- Библиотека Aspose.PDF для .NET загружена и указана в вашем проекте.

## Шаг 2: Загрузка документа PDF

Первым шагом является загрузка существующего документа PDF в ваш проект. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Откройте исходный документ
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу, в котором находится ваш PDF-документ.

## Шаг 3: Создание буферов заголовков

Теперь, когда вы загрузили документ PDF, вы можете создать штампы в заголовке для добавления. Вот как:

```csharp
// Создайте три буфера заголовков
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Приведенный выше код создает три новых буфера заголовков, содержащих указанный текст.

## Шаг 4: Настройка свойств буфера заголовков

Прежде чем добавлять штампы заголовков в документ PDF, вы можете настроить различные свойства для каждого штампа, такие как выравнивание, размер, цвет и т. д. Вот как это сделать:

```csharp
// Настройте первый буфер заголовков
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// Конфигурация второго буфера заголовков
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Настроить третий буфер заголовков
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Вы можете настроить эти свойства по мере необходимости для каждого буфера заголовков.

## Шаг 5. Добавьте штампы заголовков в PDF

Теперь, когда штампы заголовка готовы, вы можете добавить их на каждую конкретную страницу PDF-документа. Вот как:

```csharp
// Добавить буферы заголовков на определенные страницы
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Приведенный выше код добавляет каждый штамп заголовка на соответствующую страницу документа PDF.

## Шаг 6: Сохраните выходной документ

После того, как вы добавили штампы заголовка, вы можете сохранить отредактированный PDF-документ. Вот как:

```csharp
// Сохраните обновленный документ
doc.Save(dataDir);
```

Приведенный выше код сохраняет отредактированный PDF-документ в указанный каталог.

### Пример исходного кода для добавления разных заголовков с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Документ с открытым исходным кодом
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Создайте три штампа
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//Установите выравнивание штампа (поместите штамп вверху страницы, по центру по горизонтали)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Укажите стиль шрифта как полужирный
stamp1.TextState.FontStyle = FontStyles.Bold;

// Установите текст перед информацией о цвете земли как красный
stamp1.TextState.ForegroundColor = Color.Red;

// Укажите размер шрифта 14
stamp1.TextState.FontSize = 14;

// Теперь нам нужно установить вертикальное выравнивание 2-го объекта штампа как Top
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Установите информацию о выравнивании по горизонтали для штампа как с выравниванием по центру
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Установите коэффициент масштабирования для объекта штампа
stamp2.Zoom = 10;

// Установите форматирование третьего объекта штампа
// Укажите информацию о выравнивании по вертикали для объекта штампа как TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Установите информацию о выравнивании по горизонтали для объекта штампа как Выровненный по центру.
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Установите угол поворота для объекта штампа
stamp3.RotateAngle = 35;

// Установите розовый цвет в качестве фона для штампа
stamp3.TextState.BackgroundColor = Color.Pink;

// Измените информацию о шрифте для печати на Verdana.
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// Первый штамп ставится на первой странице;
doc.Pages[1].AddStamp(stamp1);

// Второй штамп ставится на второй странице;
doc.Pages[2].AddStamp(stamp2);

// Третий штамп ставится на третьей странице.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Сохраните обновленный документ
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Заключение

Поздравляем! Вы узнали, как добавлять разные заголовки на каждую страницу PDF-документа, используя Aspose.PDF для .NET. Теперь вы можете применить эти знания к своим собственным проектам, чтобы настроить заголовки для ваших PDF-документов.
