---
title: PDF Dosyasında Görüntü Boyutunu Ayarla
linktitle: PDF Dosyasında Görüntü Boyutunu Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF kullanarak bir PDF'deki görüntü boyutunu nasıl ayarlayacağınızı öğrenin. Bu adım adım kılavuz, görüntüleri yeniden boyutlandırmanıza, sayfa özelliklerini ayarlamanıza ve PDF'leri kaydetmenize yardımcı olacaktır.
type: docs
weight: 270
url: /tr/net/programming-with-images/set-image-size/
---
## giriiş

PDF'lerle çalışmak birçok uygulama için ortak bir gerekliliktir ve bir PDF dosyasındaki öğeleri düzenleme yeteneği hayati önem taşıyabilir. İster bir rapor oluşturucu oluşturun ister PDF'nize dinamik içerik ekleyin, belgenizdeki resimlerin boyutunu kontrol etmek önemli bir özelliktir. Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF dosyasındaki resim boyutunu nasıl ayarlayacağınızı adım adım anlatacağız. Bu güçlü kitaplık, PDF içeriği üzerinde kapsamlı bir kontrol sunar ve bunu ne kadar kolay olabileceğini göstermek için adım adım açıklayacağız. Sonunda, resimleri güvenle yeniden boyutlandıracak ve bu işlevselliğin PDF iş akışlarınızı nasıl geliştirebileceğini anlayacaksınız.


## Ön koşullar

Koda dalmadan önce, bu eğitimi takip edebilmeniz için birkaç şeye ihtiyacınız olacak.

1.  .NET için Aspose.PDF: Aspose.PDF kitaplığının en son sürümünün yüklü olduğundan emin olun.[buradan indirin](https://releases.aspose.com/pdf/net/).
2. .NET Framework veya .NET Core: .NET Framework veya .NET Core kurulumuyla çalışan bir ortamınız olduğundan emin olun.
3. Temel C# Bilgisi: Programlama dilimiz olarak C# kullanacağımız için, bu dile aşina olmanız önemlidir.
4. Örnek Resim: PDF'e yerleştirmek için bir örnek resme ihtiyacınız olacak. İstediğiniz herhangi bir resmi kullanabilirsiniz ancak proje dizininizde erişilebilir olduğundan emin olun.

## Paketleri İçe Aktar

Aspose.PDF for .NET'i kullanmak için öncelikle gerekli ad alanlarını içe aktarmanız gerekir. İşte basit bir kurulum:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Artık temelleri ele aldığımıza göre, PDF belgesi oluşturmaya ve düzenlemeye geçelim.

## Adım 1: PDF Belgenizi Başlatın

 Yapmamız gereken ilk şey yeni bir PDF belgesi oluşturmaktır.`Document` Bunu başarmak için Aspose.PDF'den bir sınıf kullanabilirsiniz.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini örnekle
Document doc = new Document();
```
 
 Burada bir örnek oluşturuyoruz`Document` nesnesi, PDF dosyamızı temsil edecektir. Ayrıca dosyalarımızın bulunduğu dizini de şunu kullanarak belirtiyoruz:`dataDir` değişken. Bu, Aspose.PDF ile herhangi bir PDF oluşturmanın başlangıç noktasıdır.

## Adım 2: PDF'nize Yeni Bir Sayfa Ekleyin

Belgemiz hazır olduğunda, ona bir sayfa eklememiz gerekir. Her PDF'in en az bir sayfası olmalı, o yüzden bir tane ekleyelim.

```csharp
// PDF dosyasının sayfa sayfa koleksiyonunu ekle
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
 Belgeye yeni bir sayfa eklemek için şunu kullanıyoruz:`Pages.Add()` yöntem. Bu sayfa, görselimizi yerleştireceğimiz tuval görevi görecektir. PDF'deki her sayfa, metin, görsel veya diğer içerikleri ekleyebileceğiniz temelde boş bir levhadır.

## Adım 3: Bir Görüntü Örneği Oluşturun

 Şimdi PDF'e eklemek istediğimiz resmi hazırlamanın zamanı geldi. Aspose.PDF bir`Image` Görüntüleri işlemek için kullanılan sınıf.

```csharp
// Bir görüntü örneği oluşturun
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
 Yeni bir örnek oluşturuyoruz`Image` sınıf. Bu nesne, PDF'ye eklemek istediğimiz görüntünün özelliklerini tutacaktır. Görüntünün boyutunu ve türünü bir sonraki adımlarda yapılandıracağız.

## Adım 4: Görüntü Boyutunu Ayarlayın (Genişlik ve Yükseklik)

İşte eğitimimizin özüne geldiğimiz nokta: resmin boyutunu ayarlama. Aspose.PDF resmin genişliğini ve yüksekliğini noktalarla belirtmenize olanak tanır.

```csharp
// Görüntü Genişliğini ve Yüksekliğini Noktalar Cinsinden Ayarla
img.FixWidth = 100;
img.FixHeight = 100;
```
 
 The`FixWidth` Ve`FixHeight`özellikler, görüntünün tam boyutlarını noktalar halinde ayarlamanıza olanak tanır. Bu örnekte, görüntüyü 100x100 noktalara yeniden boyutlandırıyoruz. Bu değerleri ihtiyaçlarınıza uyacak şekilde ayarlayabilirsiniz.

## Adım 5: Görüntü Türünü Belirleyin

Çalıştığınız görüntü biçimine bağlı olarak görüntü türünü ayarlamanız gerekebilir. Aspose.PDF çeşitli görüntü biçimlerini destekler ve burada dosya türünü tanımlıyoruz.

```csharp
// Resim türünü SVG olarak ayarla
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
 Bu durumda dosya türünü şu şekilde bırakıyoruz:`Unknown` , kütüphanenin görüntü türünü otomatik olarak algılamasını sağlar. Belirli dosya türünü biliyorsanız, bunu ayarlayabilirsiniz (örneğin,`ImageFileType.Jpeg` JPEG görüntüleri için). Bu adım, Aspose'un görüntüyü düzgün bir şekilde nasıl işleyeceğini bilmesini sağlar.

## Adım 6: Görüntü Dosyanızın Yolunu Ayarlayın

Şimdi Aspose'a görüntü dosyasının nerede bulunacağını söylememiz gerekiyor. Görüntünüzün belirtilen dizinde erişilebilir olduğundan emin olun.

```csharp
// Kaynak dosya yolu
img.File = dataDir + "aspose-logo.jpg";
```
 
 Burada, görüntüye giden dosya yolunu ayarlıyoruz. Görüntü, bu durumda, şu konumda bulunur:`dataDir` klasör ve adlandırılmış`aspose-logo.jpg`Bunu, görüntü dosyanızın gerçek adı ve konumuyla değiştirdiğinizden emin olun.

## Adım 7: Sayfaya Görseli Ekleyin

Resim yapılandırılıp dosya yolu ayarlandıktan sonra artık resmi sayfamıza ekleyebiliriz.

```csharp
// Resmi paragraf koleksiyonuna ekle
page.Paragraphs.Add(img);
```
 
 The`Paragraphs.Add()` yöntem, resmi sayfaya eklememize olanak tanır. Şunu düşünün`Paragraphs` PDF sayfasında işlenecek öğelerin bir listesi olarak koleksiyon. Bu koleksiyona resim, metin ve şekiller gibi birden fazla öğe ekleyebiliriz.

## Adım 8: Sayfa Özelliklerini Ayarlayın

Resmimizin iyi uyduğundan emin olmak için sayfa boyutunu ayarlayacağız. Bu, sayfa boyutlarının eklediğimiz içerikle eşleşmesini sağlayacaktır.

```csharp
// Sayfa özelliklerini ayarla
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Burada, sayfa genişliğini ve yüksekliğini 800 puana ayarlıyoruz. Bu adım isteğe bağlıdır ancak sayfanın yeniden boyutlandırılmış görüntüyü barındırmasını sağlar. Bu değerleri özel gereksinimlerinize göre ayarlayabilirsiniz.

## Adım 9: PDF'yi kaydedin

Son olarak resim ve sayfa özelliklerini yapılandırdıktan sonra PDF'i kaydedebiliriz.

```csharp
//Ortaya çıkan PDF dosyasını kaydedin
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
 Değiştirilen belgeyi şu şekilde kaydediyoruz:`SetImageSize_out.pdf` aynı dizinde. Bu dosya artık eklediğiniz yeniden boyutlandırılmış resmi içerecektir.

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF'deki görüntü boyutunun nasıl ayarlanacağını ele aldık. Bir belge oluşturma, bir sayfa ekleme, bir görüntü yapılandırma ve sonucu kaydetme adımlarını ele aldık. Bu adım adım kılavuz, .NET için Aspose.PDF ile yapabileceklerinizin yalnızca başlangıcıdır. Artık görüntüleri nasıl yeniden boyutlandıracağınızı öğrendiğinize göre, metin biçimlendirme, tablo oluşturma ve hatta PDF'nize açıklamalar ekleme gibi diğer özellikleri keşfetmekten çekinmeyin.

## SSS

### Aspose.PDF for .NET ile farklı resim formatlarını kullanabilir miyim?  
Evet, Aspose.PDF JPEG, PNG, BMP ve SVG gibi çeşitli resim formatlarını destekler.

### Görüntünün en boy oranını nasıl koruyabilirim?  
 En boy oranını, aşağıdakilerden birini ayarlayarak koruyabilirsiniz:`FixWidth` veya`FixHeight` diğer boyutu ise olduğu gibi bırakıyoruz.

### Tek bir PDF sayfasına birden fazla resim ekleyebilir miyim?  
Kesinlikle! Sadece bir resim örneği ekleme sürecini tekrarlayın ve her birini ekleyin`Paragraphs` koleksiyon.

### Görüntü boyutunu nokta dışındaki birimlerle ayarlamak mümkün müdür?  
Aspose.PDF öncelikle noktalarla çalışır, ancak inç veya milimetre gibi diğer birimleri de noktalara dönüştürebilirsiniz (1 inç = 72 nokta).

### Sayfada belirli bir yere bir görseli nasıl yerleştirebilirim?  
 Ayarlayabilirsiniz`Image.LowerLeftX` Ve`Image.LowerLeftY` Resmin sayfada konumlandırılması için özellikler.