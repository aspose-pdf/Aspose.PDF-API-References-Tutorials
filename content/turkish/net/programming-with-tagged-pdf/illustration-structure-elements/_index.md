---
title: İllüstrasyon Yapı Elemanları
linktitle: İllüstrasyon Yapı Elemanları
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te adım adım eğitimimizi izleyerek çizim öğeleri içeren yapılandırılmış PDF'ler oluşturun.
type: docs
weight: 100
url: /tr/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## giriiş

.NET uygulamalarınızda çarpıcı, yapılandırılmış PDF'ler oluşturmaya hazır mısınız? İçeriği etiketlemeyi gerektiren bir proje üzerinde çalışıyor olun veya PDF'lerinizi bir üst seviyeye taşımak istiyor olun, Aspose.PDF for .NET, çizim yapı öğeleriyle çalışmak için ihtiyaç duyduğunuz tüm araçlara sahiptir. Bu eğitimde, sizi adım adım süreç boyunca yönlendirerek en karmaşık parçaların bile kristal netliğinde olmasını sağlayacağım.

## Ön koşullar

Detaylara dalmadan önce, süreci sorunsuz bir şekilde takip edebilmeniz için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım.

1.  .NET için Aspose.PDF – Aspose.PDF kütüphanesinin kurulu olması gerekir. Henüz yok mu?[buradan indirin](https://releases.aspose.com/pdf/net/) . Önce denemek isterseniz, bir tane alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/).
2. Visual Studio – C# ile kodlama yapacağız, bu nedenle Visual Studio veya uyumlu herhangi bir IDE'nin yüklü olduğundan emin olun.
3. .NET Framework – Aspose.PDF for .NET ile uyumlu bir sürümünüz olduğundan emin olun.
4.  Geçici Lisans – Aspose.PDF deneme modunda bazı sınırlamalarla gelir, bu nedenle bir tane edinin[geçici lisans](https://purchase.aspose.com/temporary-license/) Tüm özelliklerin kilidini açmak için.

Hepsi bu kadar! Şimdi gerekli namespace'leri import edelim ve kodlamaya geçelim.

## Ad Alanlarını İçe Aktar

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu temeldir—bu ad alanlarını içe aktarmadan Aspose.PDF özellikleriyle etkileşime giremeyiz veya etiketli PDF içeriğini işleyemeyiz. Şimdi adımları ayrıntılı olarak inceleyelim.

## Adım 1: Belge Dizininizi Ayarlama

PDF'nizi oluşturmaya başlamadan önce, dosyanın kaydedileceği belge dizininize giden yolu belirtmeniz gerekir. Bu, sisteminizdeki görüntülerinizin veya diğer varlıklarınızın depolandığı klasördür.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Bu adım basit ama önemlidir. Programa, üzerinde çalışacağınız dosyaları nerede bulacağını ve depolayacağını söylüyorsunuz. PDF'leriniz için bir ana üs sahibi olmak gibi. Değiştir`"YOUR DOCUMENT DIRECTORY"` makinenizdeki gerçek yol ile.

## Adım 2: Yeni bir PDF Belgesi Oluşturma

Şimdi, PDF belgesini oluşturma zamanı. Bu adımda, sonraki adımlarda değiştireceğimiz ve geliştireceğimiz boş bir PDF belgesi başlatacağız.
 Belgeyi Oluştur

```csharp
Document document = new Document();
```

Bu satır tüm sihri yapar. Tamamen boş olan ve sizin ona içerik eklemenizi bekleyen yeni bir PDF dosyası oluşturur. Bunu yeni bir tuval açmak olarak düşünün.

## Adım 3: Etiketli PDF İçeriğine Erişim

İllüstrasyon yapı öğeleriyle çalışmak için belgenin Etiketli İçeriğine erişmemiz gerekir. Bu, belirli etiketleri tanımlamamızı ve PDF'yi daha yapılandırılmış ve erişilebilir hale getirmemizi sağlar.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 İşte sihir burada gerçekleşiyor!`TaggedContent` nesne, PDF'deki öğelerin nasıl yorumlanacağını tanımlamamızı sağlar. Erişilebilirlik veya yapı ile çalışıyorsanız, bu adım çok önemlidir.

## Adım 4: Belgenin Başlığını ve Dilini Ayarlama

Yapılandırılmış bir PDF oluşturuyoruz, bu nedenle bir başlık ve dil tanımlamak önemlidir. Bu yalnızca erişilebilirliğe yardımcı olmakla kalmaz, aynı zamanda belgeyi daha profesyonel ve aranabilir hale getirir.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

Bir başlık ve dil belirleyerek, PDF'nize esasen biraz kişilik kazandırıyorsunuz. Başlık, belge özelliklerinde görünecek ve dili ayarlamak, ekran okuyucular ve diğer erişilebilirlik araçlarıyla uyumluluğu garanti altına alacaktır.

## Adım 5: Bir İllüstrasyon (Şekil) Elemanı Oluşturma

Şimdi heyecan verici kısma geliyoruz: Bir çizim eklemek! Bu durumda, bir resim, alternatif bir metin açıklaması ve bir başlık içeren bir şekil öğesi oluşturacağız.

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

Bu kod yeni bir şekil öğesi oluşturur ve bunu belgenin kök öğesine ekler. Bunu belgenize bir resim yer tutucusu eklemek olarak düşünün.

## Adım 6: Alternatif Metin, Başlık ve Resim Ekleme

PDF'nizin erişilebilir olduğundan emin olmak için, alternatif metin ve çiziminiz için bir başlık eklemek isteyeceksiniz. Ayrıca bir resim de ekleyeceğiz.

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

 Bu son dokunuş. Resmimize açıklayıcı bir alt metin (ekran okuyucular için yararlıdır), bir başlık veriyoruz ve gerçek resim dosyasını ayarlıyoruz.`SetTag`method, şekli etiketler ve daha sonra referans almayı kolaylaştırır.

 Önemli Not: Resim yolunun doğru olduğundan emin olun.`SetImage` makinenizde geçerli bir görüntü dosyasına işaret ediyor.

## Adım 7: Etiketli PDF Belgesini Kaydetme

Tüm içerik eklenip yapılandırıldıktan sonra, PDF'yi kaydetme zamanı gelir. Bu adım her şeyi sonlandırır ve gerçek dosyayı oluşturur.

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

Basit, değil mi? Bu komut yaptığınız tüm işi alır ve daha önce belirttiğiniz dizinde yeni bir PDF dosyası oluşturur. Şimdi klasörünüzü kontrol edin ve işte karşınızda çizim öğeleri içeren yapılandırılmış bir PDF!

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak resimli yapı öğeleriyle etiketli bir PDF oluşturmayı öğrendiniz. Bu yaklaşım, PDF'lerinizin yalnızca görsel olarak çekici değil, aynı zamanda yapılandırılmış ve erişilebilir olmasını sağlar. İçeriği etiketleyerek ve alternatif metin ekleyerek, yardımcı teknolojileri kullananlar da dahil olmak üzere herkesin belgelerinizin keyfini çıkarmasını sağlarsınız.

## SSS

### Etiketli PDF içeriği nedir?
Etiketli PDF, başlıklar, paragraflar ve şekiller gibi farklı öğeleri tanımlayan etiketler veya etiketler içeren ve belgeyi daha erişilebilir hale getiren bir PDF'dir.

### Alternatif metin ayarlamanın faydası nedir?
Alternatif metin, ekran okuyucular tarafından okunabilen resimler için açıklamalar sağlar ve görme engelli kullanıcılar için erişilebilirliği artırır.

### Etiketli bir PDF'e birden fazla resim ekleyebilir miyim?
 Evet! Birden fazla oluşturabilirsiniz`FigureElement` nesneleri seçip her birini tıpkı tek bir görselde yaptığımız gibi belgenize ekleyin.

### Aspose.PDF for .NET'i kullanmak için lisansa ihtiyacım var mı?
 Evet, Aspose.PDF ücretli bir kütüphanedir, ancak bir tane alabilirsiniz.[geçici lisans](https://purchase.aspose.com/temporary-license/) veya bir ile başla[ücretsiz deneme](https://releases.aspose.com/).

### PDF oluşturulduktan sonra şekil öğesini değiştirmek mümkün müdür?
PDF kaydedildikten sonra doğrudan üzerinde değişiklik yapamazsınız; ancak Aspose.PDF'i kullanarak belgeyi yeniden açabilir, değişiklikler yapabilir ve tekrar kaydedebilirsiniz.