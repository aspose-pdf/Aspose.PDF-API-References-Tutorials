---
title: Görüntüden PDF'ye
linktitle: Görüntüden PDF'ye
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak görüntüyü kolaylıkla PDF'e dönüştürün.
type: docs
weight: 180
url: /tr/net/programming-with-images/image-to-pdf/
---

Aspose.PDF for .NET, geliştiricilerin C# veya herhangi bir .NET dili kullanarak PDF belgeleri oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Bu eğitimde, Aspose.PDF for .NET kullanarak bir görüntüyü PDF'ye dönüştürme sürecinde size rehberlik edeceğiz.

## 1. Adım: Ortamı Kurma

Başlamadan önce, sisteminizde Aspose.PDF for .NET'in kurulu olduğundan emin olun. Resmi Aspose web sitesinden indirip kurabilirsiniz. Kurulduktan sonra, tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.

## 2. Adım: Gerekli Kitaplıkları İçe Aktarma

Aspose.PDF for .NET'i projenizde kullanmak için gerekli kütüphaneleri içe aktarmanız gerekir. Aşağıdaki using deyimlerini C# dosyanızın başına ekleyin:

```csharp
using Aspose.Pdf;
using System.IO;
using System.Drawing;
```

## 3. Adım: Belge Nesnesini Başlatma

 C# kodunda ilk adım,`Document` nesne. Bu nesne, oluşturacağımız PDF belgesini temsil eder. Aşağıdaki kodu projenize ekleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyasını kaydetmek istediğiniz gerçek yolla.

## 4. Adım: Belgeye Sayfa Ekleme

 Ardından, belgeye bir sayfa eklememiz gerekiyor. Bir sayfa şununla temsil edilir:`Page` sınıf. Belgeye sayfa eklemek için aşağıdaki kodu kullanın:

```csharp
Page page = doc.Pages.Add();
```

 Bu kod yeni bir sayfa oluşturur ve onu sayfaya ekler.`Pages` belgenin toplanması.

## Adım 5: Görüntü Dosyasını Yükleme

 Bir görüntüyü PDF'ye dönüştürmek için önce kaynak görüntü dosyasını yüklememiz gerekir. Bu örnekte, resim dosyasının adlandırılmış olduğunu varsayıyoruz.`aspose-logo.jpg` ve C# dosyanızla aynı dizinde bulunur. Resim dosyasını yüklemek için aşağıdaki kodu kullanın:

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` görüntü dosyasının gerçek yolu ile.

## 6. Adım: Kenar Boşluklarını ve Kırpma Kutusunu Ayarlama

Görüntüyü PDF sayfasına eklemeden önce sayfa düzenini özelleştirebiliriz. Örneğin, kenar boşluklarını ve kırpma kutusunu görüntü boyutlarına uyacak şekilde ayarlayabiliriz. Sayfa ayarlarını yapmak için aşağıdaki kodu kullanın:

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

Bu ayarlar, görüntünün herhangi bir ek kenar boşluğu olmadan sayfaya sığmasını sağlar.

## 7. Adım: Bir Görüntü Nesnesi Oluşturma

 Şimdi bir tane oluşturalım`Aspose.Pdf.Image` görüntü verilerini tutmak için nesne. Aşağıdaki kodu projenize ekleyin:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Bu nesne, PDF sayfasına eklemek istediğimiz görüntüyü temsil edecektir.

## 8. Adım: Resmi Sayfaya Ekleme

 Görüntüyü PDF sayfasına eklemek için görüntü verilerini sayfaya atamamız gerekir.`ImageStream` mülkiyeti`Aspose.Pdf.Image`nesne. Resmi eklemek için aşağıdaki kodu kullanın:

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

 Burada, görüntü akışını şuna atarız:`ImageStream` özelliğine ve ardından görüntü nesnesini şuna ekleyin:`Paragraphs` sayfanın toplanması.

## 9. Adım: PDF Dosyasını Kaydetme

Görüntüyü PDF sayfasına ekledikten sonra, ortaya çıkan PDF dosyasını kaydedebiliriz. Dosyayı kaydetmek için aşağıdaki kodu kullanın:

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` istenen çıktı dizini ve dosya adı ile.

## Adım 10: Bellek Akışını Kapatma

PDF dosyasını kaydettikten sonra, sistem kaynaklarını serbest bırakmak için bellek akışını kapatmak önemlidir. Bellek akışını kapatmak için aşağıdaki kodu ekleyin:

```csharp
mystream. Close();
```

## Kodu Çalıştırma ve Çıktıyı Doğrulama

Artık kod uygulamasını tamamladınız. Kodu çalıştırın ve görüntünün başarıyla PDF'ye dönüştürüldüğünü doğrulayın. Çıktı dosyası belirtilen dizine kaydedilmelidir.


### Aspose.PDF for .NET kullanarak Image to PDF için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge Nesnesini Başlat
Document doc = new Document();
// Belge koleksiyonuna sayfa ekleme
Page page = doc.Pages.Add();
//Kaynak görüntü dosyasını Akış nesnesine yükleyin
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
// Yüklenen görüntü akışıyla BitMap nesnesinin örneğini oluşturun
Bitmap b = new Bitmap(mystream);
// Kenar boşluklarını görüntünün sığacağı şekilde ayarlayın, vb.
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
// Bir görüntü nesnesi oluşturun
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Görüntüyü bölümün paragraflar koleksiyonuna ekleyin
page.Paragraphs.Add(image1);
// Görüntü dosyası akışını ayarla
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
// Ortaya çıkan PDF dosyasını kaydet
doc.Save(dataDir);
// memoryStream nesnesini kapat
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir görüntüyü PDF'ye nasıl dönüştüreceğimizi öğrendik. Ortamın ayarlanması, kitaplıkların içe aktarılması, belge nesnesinin başlatılması, görüntü dosyasının yüklenmesi, kenar boşluklarının ve kırpma kutusunun ayarlanması, görüntünün sayfaya eklenmesi, PDF dosyasının kaydedilmesi ve kapatılması dahil olmak üzere adım adım süreci ele aldık. bellek akışı. Bu adımları izleyerek, .NET uygulamalarınızdaki görüntüleri kolayca PDF'ye dönüştürebilirsiniz.