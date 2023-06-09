---
title: Заполнить обводку текста
linktitle: Заполнить обводку текста
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как легко заполнять и выделять текст в документах PDF с помощью Aspose.PDF для .NET.
type: docs
weight: 90
url: /ru/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
В этом руководстве мы шаг за шагом покажем вам, как заполнить и обвести текст в документе PDF с помощью Aspose.PDF для .NET. Мы покажем вам, как использовать предоставленный исходный код C# для применения цветов заливки и контура к тексту в документе PDF.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установленная среда разработки .NET.
- Библиотека Aspose.PDF для .NET загружена и указана в вашем проекте.

## Шаг 2: Создание объекта TextState

Первым шагом является создание объекта TextState для передачи расширенных свойств. Вот как:

```csharp
// Создайте объект TextState для передачи расширенных свойств
TextState ts = new TextState();

// Установить цвет контура
ts.StrokingColor = Color.Gray;

// Определить режим рендеринга текста
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Приведенный выше код создает новый объект TextState и устанавливает цвет контура, а также то, как текст отображается.

## Шаг 3: Загрузка PDF-документа

Теперь, когда объект TextState готов, мы можем загрузить PDF-документ, к которому мы хотим применить заливку и контур текста. Вот как:

```csharp
// Загрузите документ PDF в качестве входных данных
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Приведенный выше код загружает существующий документ PDF с помощью класса PdfFileStamp из библиотеки Aspose.PDF.Facades.

## Шаг 4: добавьте заливку и обводку к тексту

Теперь, когда документ PDF загружен, мы можем добавить к тексту заливку и контур. Вот как:

```csharp
// Создать штамп (Штамп) с заданным текстом и свойствами
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Привязать объект TextState
stamp.BindTextState(ts);

// Установить исходную точку X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Добавьте штамп в документ
fileStamp.AddStamp(stamp);
```

Приведенный выше код создает штамп с указанным текстом и определенными свойствами Fill и Stroke.

## Шаг 5: Сохраните выходной документ

После добавления текстовой метки мы можем сохранить измененный PDF-документ. Вот как:

```csharp
// Сохраните измененный документ
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Приведенный выше код сохраняет отредактированный PDF-документ в указанный каталог.

### Пример исходного кода для заливки обводки текста с использованием Aspose.PDF для .NET 
```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Создайте объект TextState для передачи расширенных свойств
TextState ts = new TextState();

// Установить цвет обводки
ts.StrokingColor = Color.Gray;

// Установить режим рендеринга текста
ts.RenderingMode = TextRenderingMode.StrokeText;

//Загрузите входной PDF-документ
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Привязать текстовое состояние
stamp.BindTextState(ts);

// Установить начало координат X, Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Добавить штамп
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Заключение

Поздравляем! Вы узнали, как заполнить и обвести текст в документе PDF с помощью Aspose.PDF для .NET. Теперь вы можете применить эти знания для настройки цветов заливки и контура в документах PDF.
