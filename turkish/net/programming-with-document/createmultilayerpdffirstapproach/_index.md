---
title: İlk Yaklaşım Çok Katmanlı PDF Oluşturun
linktitle: İlk Yaklaşım Çok Katmanlı PDF Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile İlk Yaklaşımı kullanarak çok katmanlı PDF belgeleri oluşturmayı öğrenin. PDF'lerinizi geliştirmek için metin, resim ve daha fazlasını ekleyin.
type: docs
weight: 70
url: /tr/net/programming-with-document/createmultilayerpdffirstapproach/
---

Bu eğitimde, Aspose.PDF for .NET ile ilk yaklaşımı kullanarak çok katmanlı bir PDF oluşturma sürecinde size rehberlik edeceğiz. Bu yaklaşım, PDF belgenize birden çok katman eklemenizi sağlar. Aşağıdaki adım adım kılavuzu izleyin:

## 1. Adım: PDF belgesini başlatın

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## 2. Adım: Belgeye yeni bir sayfa ekleyin

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## 3. Adım: Sayfaya bir metin parçası ekleyin

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## 4. Adım: Metin parçasını özelleştirin

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## 5. Adım: Sayfaya bir resim ekleyin

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## 6. Adım: Sayfaya kayan bir kutu ekleyin

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## 7. Adım: Ortaya çıkan PDF belgesini kaydedin

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Tebrikler! Aspose.PDF for .NET ile ilk yaklaşımı kullanarak başarılı bir şekilde çok katmanlı bir PDF belgesi oluşturdunuz.

Aspose.PDF for .NET kullanarak Create Multilayer PDF First Approach için örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
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

Artık Aspose.PDF for .NET ile ilk yaklaşımı kullanarak çok katmanlı PDF belgeleri oluşturabilirsiniz.
