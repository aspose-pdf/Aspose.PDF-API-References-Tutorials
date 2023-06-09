---
title: PDF Operatörleri
linktitle: PDF Operatörleri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF operatörlerini kullanmak için adım adım kılavuz. PDF sayfasına bir görüntü ekleyin ve konumunu belirtin.
type: docs
weight: 20
url: /tr/net/programming-with-operators/pdf-operators/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF operatörlerinin nasıl kullanılacağına dair adım adım bir kılavuz sağlayacağız. PDF operatörleri, PDF belgelerini hassas ve kontrollü bir şekilde değiştirmenize ve içerik eklemenize olanak tanır. Aspose.PDF tarafından sağlanan operatörleri kullanarak bir PDF sayfasına görüntü ekleyebilir ve konumunu tam olarak belirleyebilirsiniz.

## Önkoşullar

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. .NET çerçevesiyle yüklenen Visual Studio.
2. .NET için Aspose.PDF kitaplığı.

## Adım 1: Proje Kurulumu

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Kütüphaneyi Aspose resmi sitesinden indirebilir ve makinenize kurabilirsiniz.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını C# kod dosyanıza aktarın:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## 3. Adım: PDF belgesini yükleme

PDF belgesini yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document pdfDocument = new Document(dataDir + "PDFOperators.pdf");
```

Makinenizde PDF dosyasının gerçek yolunu belirttiğinizden emin olun.

## 4. Adım: Resmin yüklenmesi ve sayfaya eklenmesi

Bir dosyadan görüntü yüklemek ve onu PDF sayfasına eklemek için aşağıdaki kodu kullanın:

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;

Page page = pdfDocument.Pages[1];

FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream);

page. Contents. Add(new GSave());

Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });

page.Contents.Add(new ConcatenateMatrix(matrix));

XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Do(ximage.Name));

page. Contents. Add(new GRestore());
```

 Makinenizde PDF ve görüntü dosyalarının gerçek yollarını belirttiğinizden emin olun. Ayrıca ayarlayabilirsiniz`lowerLeftX`, `lowerLeftY`, `upperRightX` Ve`upperRightY` görüntüyü gerektiği gibi konumlandırmak için koordinatlar.

### Aspose.PDF for .NET kullanan PDF Operatörleri için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir+ "PDFOperators.pdf");
// Koordinatları ayarla
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Resmin eklenmesi gereken sayfayı alın
Page page = pdfDocument.Pages[1];
// Görüntüyü akışa yükle
FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
// Sayfa Kaynaklarının Görseller koleksiyonuna resim ekleyin
page.Resources.Images.Add(imageStream);
// GSave operatörünü kullanma: bu operatör mevcut grafik durumunu kaydeder
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Dikdörtgen ve Matris nesneleri oluşturma
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//ConcatenateMatrix (concatenate matrix) operatörünü kullanma: görüntünün nasıl yerleştirilmesi gerektiğini tanımlar
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Do işlecini kullanma: bu işleç görüntüyü çizer
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// GRestore operatörünü kullanma: bu operatör grafik durumunu geri yükler
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "PDFOperators_out.pdf";
// Güncellenen belgeyi kaydet
pdfDocument.Save(dataDir);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kullanarak PDF operatörlerini nasıl kullanacağınızı öğrendiniz. Açıklanan adımları izleyerek, bir PDF sayfasına görüntü ekleyebilir ve konumunu tam olarak belirleyebilirsiniz. PDF Operatörleri, içeriğinizi özelleştirmenize izin vererek, PDF belgelerinin işlenmesi üzerinde ayrıntılı kontrol sağlar.
