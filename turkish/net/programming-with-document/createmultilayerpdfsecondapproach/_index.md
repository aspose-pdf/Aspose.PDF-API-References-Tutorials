---
title: Çok Katmanlı PDF İkinci Yaklaşımı Oluşturun
linktitle: Çok Katmanlı PDF İkinci Yaklaşımı Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak çok katmanlı bir PDF oluşturmayı öğrenin. Metin ve resimlerle dinamik PDF'ler oluşturmak için kaynak kodlu adım adım kılavuz.
type: docs
weight: 80
url: /tr/net/programming-with-document/createmultilayerpdfsecondapproach/
---

Bu öğreticide, Aspose.PDF for .NET'te ikinci yaklaşımı kullanarak çok katmanlı bir PDF oluşturmayı keşfedeceğiz. Ayrıntılı açıklamalar içeren ve tam kaynak kodunu içeren adım adım bir kılavuz sağlayacağız. Bu öğreticiyi izleyerek, .NET uygulamalarınızda Aspose.PDF kitaplığını kullanarak çok katmanlı PDF belgeleri oluşturabileceksiniz.

Şimdi adım adım kılavuza başlayalım.

## 1. Adım: Ortamı Kurun

Başlamak için Visual Studio'yu açın ve yeni bir C# projesi oluşturun. Projenizde Aspose.PDF kitaplığına başvurduğunuzdan emin olun. Ortamı kurduktan sonra, bir sonraki adıma geçmeye hazırsınız.

## 2. Adım: Değişkenleri Başlatın

Bu adımda, gerekli değişkenleri başlatacağız. Belge dizinine giden yolu ayarlamamız ve PDF katmanları için renk değişkenlerini tanımlamamız gerekiyor. İşte kod parçacığı:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## 3. Adım: Bir PDF Belgesi Oluşturun

Ardından, bir PDF belgesini temsil eden Aspose.Pdf.Document sınıfının yeni bir örneğini oluşturacağız. İşte kod parçacığı:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Adım 4: Belgeye Sayfa Ekleyin

Bu adımda, PDF belgesine yeni bir sayfa ekleyeceğiz. İşte kod parçacığı:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 5. Adım: Sayfaya Metin Ekleyin

Şimdi sayfaya bir metin parçası ekleyeceğiz. Metin, kırmızı renkli paragraf 3 segmenti olarak görüntülenecektir. İşte kod parçacığı:

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## Adım 6: Sayfaya Resim Ekleyin

Bu adımda sayfaya bir resim ekleyeceğiz. Görüntü, belirli bir boyutta kayan bir kutu olarak konumlandırılacaktır. İşte kod parçacığı:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## 7. Adım: PDF'yi kaydedin

Bu adımda, PDF'yi bir dosyaya kaydedeceğiz.

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### Aspose.PDF for .NET kullanarak çok katmanlı PDF ikinci yaklaşımı oluşturmak için örnek kaynak kodu.

```csharp

            
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
            
        
```

## Çözüm

Bu makalede, Aspose.PDF for .NET'in ikinci yaklaşımını kullanarak çok katmanlı bir PDF oluşturmayı öğrendik. Çok katmanlı bir PDF oluşturmak için gereken tüm kaynak kodu ve adım adım talimatları sağladık.