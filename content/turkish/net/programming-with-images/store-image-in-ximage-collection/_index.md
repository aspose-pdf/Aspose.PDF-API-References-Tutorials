---
title: Resmi XImage Koleksiyonunda Sakla
linktitle: Resmi XImage Koleksiyonunda Sakla
second_title: Aspose.PDF for .NET API Referansı
description: Bu kapsamlı adım adım kılavuzda, Aspose.PDF for .NET kullanarak XImage koleksiyonunda görüntülerin nasıl saklanacağını öğrenin.
type: docs
weight: 290
url: /tr/net/programming-with-images/store-image-in-ximage-collection/
---
## giriiş

Günümüzün dijital çağında, belgeleri programatik olarak işlemek ve düzenlemek birçok uygulama için olmazsa olmazdır. Aspose.PDF for .NET, geliştiricilerin PDF dosyalarıyla zahmetsizce çalışmasını sağlayarak iş akışlarını iyileştirir ve dinamik içerik oluşturulmasını sağlar. Bu kılavuzda, görselleri doğrudan PDF'lerinize yerleştirmenize olanak tanıyan hayati bir özellik olan XImage koleksiyonunda bir görüntüyü depolama sürecini inceleyeceğiz. Çarpıcı içerik oluşturma yolculuğuna çıkmaya hazır olun.

## Ön koşullar

Koda ve süreçlere dalmadan önce, birkaç şeyin yerinde olduğundan emin olmanız gerekir:

- .NET Ortamı: Makinenizde .NET Framework yüklü olmalıdır. Projenizin gereksinimlerine göre uygun sürümü seçin.
- .NET için Aspose.PDF: Aspose.PDF kütüphanesine sahip olduğunuzdan emin olun. Bunu şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/pdf/net/) veya ücretsiz denemeyle başlayın[Burada](https://releases.aspose.com/).
- Resim Dosyası: Ayrıca PDF'de saklamak istediğiniz bir resim dosyasına (JPG veya PNG gibi) ihtiyacınız var. Bu örnek için "aspose-logo.jpg" adlı bir dosya kullanacağız.
- C# Temel Anlayışı: C# programlamaya aşinalık, akıcı bir şekilde takip etmenize yardımcı olacaktır.

## Paketleri İçe Aktar

Aspose.PDF for .NET'i kullanmaya başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bu adım, kütüphanenin sunduğu tüm işlevleri kullanmak için temel oluşturur.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Operators;
```

Bu ad alanlarını içe aktararak Aspose.PDF'de belge oluşturma, görüntü işleme ve daha fazlası dahil olmak üzere çeşitli özellikleri etkinleştirirsiniz.

Bunu sizin için daha kolay takip edilebilir adımlara bölelim.

## Adım 1: Belge Dizininizi Ayarlayın

Yapmanız gereken ilk şey nedir? Belgelerinizin nerede bulunacağını tanımlayın. Belge dizininize giden yolu tutan bir değişken ayarlamak isteyeceksiniz. PDF'niz buraya kaydedilecektir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Gerçek belge dizininizle değiştirin.
```

## Adım 2: Belgeyi Başlatın

Şimdi yeni bir PDF belgesi oluşturma zamanı. Bu adım, PDF'inizin canlandığı adımdır. 

```csharp
Aspose.Pdf.Document document = new Document();
```

Burada, tuvalimiz olarak hizmet edecek yeni bir Belge nesnesi oluşturuyoruz.

## Adım 3: Yeni Bir Sayfa Ekleyin

Her şaheserin bir tuvale ihtiyacı vardır, değil mi? Bizim durumumuzda, belge içinde üzerinde çalışacağımız bir sayfaya ihtiyacımız var.

```csharp
document.Pages.Add();
Page page = document.Pages[1]; // İlk sayfayı alın.
```

Belgemize yeni bir sayfa ekliyoruz. Şimdi bu sayfa üzerinde işlem yapacağız.

## Adım 4: Görüntü Dosyasını Yükleyin

Sonra, görüntüyü programınıza yüklemeniz gerekecek. Bu adım, okumak için bir kitap açmaya oldukça benzer; kullanmadan önce içeriğe erişmeniz gerekir.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open))
{
```

Bu satır, resim dosyasını bir akış olarak açar ve bu da onu düzenlememize ve PDF'e yerleştirmemize olanak tanır.

## Adım 5: Görseli Sayfa Kaynaklarına Ekleyin

Artık görseliniz hazır olduğuna göre, onu sayfa kaynaklarına eklemenin zamanı geldi. Yani PDF'e, "Hey, hatırlamanı istediğim harika bir görselim var!" demelisiniz.

```csharp
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

 Bu kod, PDF'ye resim ekleme ve onu bir kullanıcıya atama gibi ağır işleri yapar.`XImage` Daha sonra başvurabileceğimiz değişken.

## Adım 6: Resmi Çizmeye Hazırlanın

İşte eğlenceli kısım geliyor: Resmi sayfaya yerleştirmek. Resmin tam olarak istediğiniz yere yerleştirilmesi için koordinatları ayarlamak isteyeceksiniz.

```csharp
page.Contents.Add(new GSave());
```

Bu satır, grafik durumunu daha sonraki geri yükleme için kaydeder. Herhangi bir şeyi değiştirmeden önce her şeyin nasıl ayarlandığının bir anlık görüntüsünü almak gibidir.

## Adım 7: Görüntü Pozisyonunu ve Boyutunu Tanımlayın

Şimdi, resminizi ne kadar büyük ve nereye yerleştirmek istediğinizi tanımlayın:

```csharp
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
```

Bu kod bloğu, resminizin sığacağı dikdörtgenin boyutlarını belirler ve esasen ona sayfanızda bir yuva verir.

## Adım 8: Bir Dönüşüm Matrisi Oluşturun 

Görüntünün nasıl yerleştirileceğini kontrol etmek için bir dönüşüm matrisi tanımlayacağız. Bu, görüntünün hedef koordinatlarda nasıl görüneceğini yönetir.

```csharp
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

Bunu yolculuğunuza çıkmadan önce bir harita çizmek gibi düşünün. Görüntünün sayfada nasıl görüneceğini belirlemeye yardımcı olur.

## Adım 9: Görseli Sayfaya Yerleştirin

Şimdi, PDF'e o görseli nereye koyacağını söylemenin zamanı geldi.

```csharp
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
```

Burada, PDF'in içerik akışına, az önce kurduğumuz matrise göre görüntüyü çizecek komutlar ekliyoruz.

## Adım 10: Belgeyi Kaydedin

Sonunda, şaheserimizi kurtarabiliriz! Bu, tüm sıkı çalışmanızın somut bir çıktıya dönüştüğü andır.

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Aspose.PDF'e belgeyi verilen dosya adıyla kaydetmesini söylediniz. Bu kodu çalıştırdığınızda, yeni oluşturduğunuz PDF dosyanızı, gömülü görüntünüzle birlikte belirtilen dizinde bulacaksınız.

## Çözüm

Ve işte karşınızda! XImage koleksiyonunda nokta nokta bir görüntü depolamak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrendiniz. Kodunuzun şekil alıp yararlı bir şey ürettiğini görmek memnuniyet verici değil mi? İster uygulamalar geliştiriyor olun ister sadece raporları otomatikleştirmek istiyor olun, bu kılavuz harika bir temel parça görevi görür. Unutmayın, Aspose.PDF'nin gücü sadece bunun ötesinde birçok görevde size yardımcı olabilir, bu yüzden keşfetmeye devam edin!

## SSS

### Aspose.PDF'de hangi dosya formatları destekleniyor?
Aspose.PDF, JPG, PNG, BMP ve GIF gibi çeşitli resim formatlarını destekler.

### PDF'e eklerken görselin boyutunu değiştirebilir miyim?
Evet, dikdörtgende tanımlanan koordinatları ayarlayarak PDF'de görüntülenen görüntünün boyutunu değiştirebilirsiniz.

### Aspose.PDF'i kullanmak için lisansa ihtiyacım var mı?
 Aspose ücretsiz deneme ve çeşitli satın alma seçenekleri sunar. Bunları bulabilirsiniz[Burada](https://purchase.aspose.com/buy).

### Sorun yaşarsam nasıl destek alabilirim?
 Aspose topluluğundan yardım isteyebilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).

### PDF'e eklenen görsellere sıkıştırma uygulamanın bir yolu var mı?
Evet, PDF'e resim eklerken Flate gibi sıkıştırma yöntemlerini kullanmak için resim filtresi türünü belirtebilirsiniz.