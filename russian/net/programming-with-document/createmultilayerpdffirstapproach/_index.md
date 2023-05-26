---
title: Первый подход к созданию многослойного PDF
linktitle: Первый подход к созданию многослойного PDF
second_title: Aspose.PDF для справочника API .NET
description: Узнайте, как создавать многослойные PDF-документы, используя первый подход с Aspose.PDF для .NET. Добавьте текст, изображения и многое другое, чтобы улучшить ваши PDF-файлы.
type: docs
weight: 70
url: /ru/net/programming-with-document/createmultilayerpdffirstapproach/
---

В этом руководстве мы проведем вас через процесс создания многослойного PDF-файла, используя первый подход с Aspose.PDF для .NET. Этот подход позволяет добавлять несколько слоев в документ PDF. Следуйте пошаговой инструкции ниже:

## Шаг 1. Инициализируйте PDF-документ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## Шаг 2. Добавьте новую страницу в документ

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## Шаг 3: Добавьте фрагмент текста на страницу

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## Шаг 4: Настройте текстовый фрагмент

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## Шаг 5: Добавьте изображение на страницу

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## Шаг 6. Добавьте на страницу плавающее поле.

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## Шаг 7: Сохраните полученный PDF-документ

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Поздравляем! Вы успешно создали многослойный PDF-документ, используя первый подход с Aspose.PDF для .NET.

Пример исходного кода для первого подхода к созданию многослойного PDF с использованием Aspose.PDF для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Теперь вы можете создавать многослойные PDF-документы, используя первый подход с Aspose.PDF для .NET.
