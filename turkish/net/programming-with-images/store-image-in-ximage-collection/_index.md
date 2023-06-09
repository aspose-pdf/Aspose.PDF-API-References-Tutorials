---
title: Görüntüyü XImage Koleksiyonunda Sakla
linktitle: Görüntüyü XImage Koleksiyonunda Sakla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir görüntüyü XImage koleksiyonunda depolamak için adım adım kılavuz.
type: docs
weight: 290
url: /tr/net/programming-with-images/store-image-in-ximage-collection/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak XImage koleksiyonunda bir görüntünün nasıl saklanacağını size göstereceğiz. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- Aspose.PDF kitaplığı for .NET kurulu. Aspose resmi sitesinden indirebilirsiniz.

## 1. Adım: PDF belgesi başlatma

Başlamak için, yeni bir PDF belgesi başlatmak üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Belgeyi başlat
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Adım 2: Görüntüyü XImage koleksiyonuna ekleme

Ardından, görüntüyü PDF belgesinin XImage koleksiyonuna ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Görüntü kaynak dosyasına doğru yolu sağladığınızdan emin olun.

## 3. Adım: Resmin sayfaya yerleştirilmesi

Şimdi görüntüyü PDF belgesinin sayfasına yerleştirelim. Aşağıdaki kodu kullanın:

```csharp
page. Contents. Add(new GSave());

// Koordinatları ayarla
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//ConcatenateMatrix operatörünü kullanarak: görüntünün nasıl yerleştirilmesi gerektiğini tanımlayın
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Bu, görüntüyü sayfada belirtilen koordinatlara yerleştirir.

## 4. Adım: PDF belgesini kaydetme

Son olarak, güncellenmiş PDF belgesini kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Nihai PDF belgesi için istenen yolu ve dosya adını sağladığınızdan emin olun.

### Aspose.PDF for .NET kullanan XImage Collection'da Store Image için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi Başlat
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Koordinatları ayarla
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//ConcatenateMatrix (concatenate matrix) operatörünü kullanma: görüntünün nasıl yerleştirilmesi gerektiğini tanımlar
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir görüntüyü XImage koleksiyonunda başarıyla depoladınız. Artık PDF dosyalarındaki görüntüleri değiştirmek ve kişiselleştirmek için bu yöntemi kendi projelerinize uygulayabilirsiniz.