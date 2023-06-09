---
title: Farklı Başlıklar Ekleme
linktitle: Farklı Başlıklar Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizin her sayfasına farklı başlıkları kolayca nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl farklı başlıklar ekleyeceğinizi adım adım anlatacağız. PDF belgesinin her sayfasına özel başlıklar eklemek için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Kaynak belgeyi aç
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Başlık Arabellekleri Oluşturma

Artık PDF belgesini yüklediğinize göre, eklenecek başlık damgalarını oluşturabilirsiniz. İşte nasıl:

```csharp
// Üç başlık arabelleği oluştur
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Yukarıdaki kod, belirtilen metni içeren üç yeni başlık arabelleği oluşturur.

## 4. Adım: Başlık arabelleği özelliklerini yapılandırma

Başlık damgalarını PDF belgesine eklemeden önce, her bir damga için hizalama, boyut, renk vb. gibi farklı özellikler yapılandırabilirsiniz. Bunu şu şekilde yapabilirsiniz:

```csharp
// İlk başlık arabelleğini yapılandırın
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// İkinci başlık arabelleğinin konfigürasyonu
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Üçüncü başlık arabelleğini yapılandırın
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Bu özellikleri her başlık arabelleği için gerektiği gibi ayarlayabilirsiniz.

## 5. Adım: PDF'ye Başlık Damgaları Ekleyin

Artık başlık damgaları hazır olduğuna göre, bunları PDF belgesinin belirli her sayfasına ekleyebilirsiniz. İşte nasıl:

```csharp
// Belirli sayfalara başlık arabellekleri ekleyin
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Yukarıdaki kod, her başlık damgasını PDF belgesinin ilgili sayfasına ekler.

## 6. Adım: Çıktı belgesini kaydedin

Başlık damgalarını ekledikten sonra düzenlenen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Güncellenen belgeyi kaydedin
doc.Save(dataDir);
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Farklı Başlıklar Eklemek için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Açık kaynak belgesi
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Üç pul oluştur
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//Damga hizalamasını ayarlayın (damgayı sayfanın üstüne yerleştirin, yatay olarak ortalayın)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Yazı tipi stilini Kalın olarak belirtin
stamp1.TextState.FontStyle = FontStyles.Bold;

// Metin ön zemin rengi bilgisini kırmızı olarak ayarlayın
stamp1.TextState.ForegroundColor = Color.Red;

// Yazı tipi boyutunu 14 olarak belirtin
stamp1.TextState.FontSize = 14;

// Şimdi 2. damga nesnesinin dikey hizalamasını Üst olarak ayarlamamız gerekiyor.
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Damga için yatay hizalama bilgilerini Ortaya hizalanmış olarak ayarlayın
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Damga nesnesi için yakınlaştırma faktörünü ayarlayın
stamp2.Zoom = 10;

// 3. damga nesnesinin biçimlendirmesini ayarlayın
// Damga nesnesi için Dikey hizalama bilgisini TOP olarak belirtin
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Damga nesnesi için Yatay hizalama bilgisini Ortaya hizalanmış olarak ayarlayın
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Damga nesnesi için dönüş açısını ayarlayın
stamp3.RotateAngle = 35;

// Damga için arka plan rengi olarak pembeyi ayarla
stamp3.TextState.BackgroundColor = Color.Pink;

// Damga için yazı tipi yüzü bilgisini Verdana olarak değiştirin
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// İlk kaşe ilk sayfaya eklenir;
doc.Pages[1].AddStamp(stamp1);

// İkinci sayfaya ikinci kaşe eklenir;
doc.Pages[2].AddStamp(stamp2);

// Üçüncü sayfaya üçüncü kaşe eklenmiştir.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Güncellenen belgeyi kaydedin
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin her sayfasına nasıl farklı başlıklar ekleyeceğinizi öğrendiniz. Artık bu bilgiyi, PDF belgelerinizin başlıklarını özelleştirmek için kendi projelerinize uygulayabilirsiniz.
