---
title: PDF Dosyasının Altbilgisindeki Metin
linktitle: PDF Dosyasının Altbilgisindeki Metin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasının altbilgisine nasıl kolayca metin ekleyeceğinizi öğrenin. Sorunsuz entegrasyon için adım adım kılavuz dahildir.
type: docs
weight: 180
url: /tr/net/programming-with-stamps-and-watermarks/text-in-footer/
---
## giriiş

.NET için Aspose.PDF kullanarak bir PDF dosyasının alt bilgisine özel metin eklemek mi istiyorsunuz? Doğru yerdesiniz! Sayfa numaraları, tarihler veya başka herhangi bir özel metin eklemek isteyip istemediğinize bakılmaksızın, bu eğitim sizi tüm süreçte yönlendirecektir. Sağlam bir PDF düzenleme kütüphanesi olan Aspose.PDF ile alt bilgi eklemek inanılmaz derecede kolaydır. Bu makalede, PDF dosyanızdaki her sayfanın alt bilgisine metin eklemek için adım adım süreci inceleyeceğiz. Hızlı, basit ve .NET uygulamalarında PDF özelleştirmelerini otomatikleştirmek isteyenler için mükemmeldir.


## Ön koşullar

Kodlamaya başlamadan önce her şeyin hazır olduğundan emin olalım:

-  Aspose.PDF for .NET: Aspose.PDF for .NET'in yüklü olduğundan emin olun. Değilse,[buradan indirin](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio gibi bir geliştirme ortamına ihtiyacınız olacak.
- Temel C# Bilgisi: C# ve .NET hakkında temel bir anlayışa sahip olmak gerekir.
-  Lisans: Aspose.PDF'yi değerlendirme modunda kullanabilmenize rağmen, tam işlevsellik için bir tane edinmeyi düşünün[ücretsiz deneme](https://releases.aspose.com/) veya başvuruda bulunmak[geçici lisans](https://purchase.aspose.com/temporary-license/).

## Paketleri İçe Aktar

Kodlama kısmına başlamadan önce, gerekli ad alanlarını içe aktardığınızdan emin olun. Bu, Aspose.PDF kütüphanesindeki sınıfların ve yöntemlerin projenizde kullanılabilir olmasını sağlayacaktır.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Artık hazır olduğunuza göre, bir PDF dosyasının altbilgisine metin ekleme sürecini kolay takip edilebilir adımlara bölelim.

## Adım 1: Projenizi Başlatın ve Belge Dizinini Ayarlayın

PDF dosyalarınızla çalışabilmeniz için, belgelerinizin dizinine giden yolu belirtmeniz gerekir. PDF dosyanızın bulunduğu ve değiştirilen dosyanın kaydedileceği yer burasıdır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Burada, değiştirin`"YOUR DOCUMENT DIRECTORY"` klasörünüzün gerçek yolu ile. Bu klasör orijinal PDF dosyasını içerecek ve aynı zamanda değiştirilmiş dosya için çıktı konumu olarak hizmet edecektir.

## Adım 2: PDF Belgesini Yükleyin

 Bir sonraki adım PDF dosyasını projenize yüklemektir.`Document` Aspose.PDF'den gelen sınıf, mevcut PDF belgelerini açmanıza ve düzenlemenize olanak tanır.

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

 Burada,`TextinFooter.pdf` üzerinde çalıştığımız dosyadır. Bunu kendi dosya adınızla değiştirebilirsiniz.

## Adım 3: Altbilgi Metnini Oluşturun

Şimdi, her sayfaya damgalanacak olan altbilgi metnini oluşturalım. Bu, şunu kullanarak yapılır:`TextStamp` sınıf. Tanımladığınız metin tüm sayfaların alt bilgisi olarak kullanılacaktır.

```csharp
// Altbilgi oluştur
TextStamp textStamp = new TextStamp("Footer Text");
```

Bu durumda, "Footer Text" diyen basit bir footer metni oluşturduk. Bunu kendi mesajınızla özelleştirmekten çekinmeyin. İsterseniz "Confidential" veya bir sayfa numarası gibi bir şey olabilir.

## Adım 4: Altbilgi Özelliklerini Ayarlayın

 Altbilgiyi doğru şekilde konumlandırmak için kenar boşlukları, hizalama ve konumlandırma gibi bazı özellikleri ayarlamamız gerekir.`TextStamp` sınıfı, altbilgi metninin nerede ve nasıl görüntüleneceği üzerinde tam kontrol sağlar.

```csharp
// Damganın özelliklerini ayarla
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Burada, alt kenar boşluğunu 10 birime ayarladık, metni yatay olarak ortaya hizaladık ve dikey olarak sayfanın altına yerleştirdik. Bu değerleri, belirli düzen ihtiyaçlarınıza göre ayarlayabilirsiniz.

## Adım 5: Tüm Sayfalara Alt Bilgi Uygula

Şimdi eğlenceli kısma geliyoruz: PDF'deki her sayfaya altbilgiyi uygulamak. Belgedeki tüm sayfalarda yineleme yaparak, her birine altbilgi metni ekleyebiliriz.

```csharp
// Tüm sayfalara altbilgi ekle
foreach (Page page in pdfDocument.Pages)
{
    page.AddStamp(textStamp);
}
```

Bu döngü, PDF'in kaç sayfası olursa olsun, altbilginin belgenin tüm sayfalarına damgalanmasını sağlar.

## Adım 6: Güncellenen PDF Dosyasını Kaydedin

Altbilgi tüm sayfalara eklendikten sonra, son adım değiştirilen PDF dosyasını belirtilen dizine kaydetmektir.

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
// Güncellenen PDF dosyasını kaydet
pdfDocument.Save(dataDir);
```

 Dosyayı yeni bir adla kaydediyoruz.`TextinFooter_out.pdf`, aynı dizinde. Gerektiğinde adını değiştirmekten çekinmeyin.

## Adım 7: Başarıyı Onaylayın

Son olarak, konsola bir başarı mesajı yazdırabilir ve kullanıcıya PDF'nin başarıyla güncellendiğini bildirebilirsiniz.

```csharp
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);
```

Ve işte bu kadar! PDF'inizdeki her sayfanın alt bilgisine başarıyla metin eklediniz.

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF belgesine alt bilgi eklemek, PDF dosyalarınızı özelleştirmenin basit ve güçlü bir yoludur. Sadece birkaç satır kodla, belgedeki her sayfaya tarihler, başlıklar veya sayfa numaraları gibi kişiselleştirilmiş metinler ekleyebilirsiniz. Bu kılavuzu izleyerek, artık bu işlevselliği .NET uygulamalarınızda uygulamak için gereken bilgiye sahipsiniz.

## SSS

### PDF'deki her sayfaya farklı altbilgiler ekleyebilir miyim?  
 Evet, farklı altbilgiler belirterek her sayfaya benzersiz altbilgiler ekleyebilirsiniz.`TextStamp` her sayfa için nesneler.

### Altbilgi metninin yazı tipini nasıl değiştirebilirim?  
 Metni, kullanarak özelleştirebilirsiniz.`TextStamp.TextState` yazı tipini, boyutunu ve rengini ayarlama özelliği.

### Alt bilgiye metin yerine resim ekleyebilir miyim?  
 Evet, kullanabilirsiniz`ImageStamp` PDF dosyasının altbilgisine resim eklemek için.

### Sadece belirli sayfalara altbilgi eklemek mümkün müdür?  
 Kesinlikle! Altbilginin olmasını istediğiniz sayfa numaralarını belirli bir hedefi hedefleyerek belirtebilirsiniz.`Page` nesneler.

### Mevcut bir alt bilgiyi PDF'den nasıl kaldırabilirim?  
 Mevcut damgaları kullanarak temizleyebilirsiniz.`Page.DeleteStampById` yöntem veya kullanarak`RemoveStamp` tüm pulları kaldırmak.