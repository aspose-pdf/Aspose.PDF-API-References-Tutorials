---
title: PDF Dosyasında Zaman Damgasıyla Dijital İmza
linktitle: PDF Dosyasında Zaman Damgasıyla Dijital İmza
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF kullanarak bir PDF'yi zaman damgasıyla dijital olarak nasıl imzalayacağınızı öğrenin. Bu adım adım kılavuz ön koşulları, sertifika kurulumunu, zaman damgasını ve daha fazlasını kapsar.
type: docs
weight: 50
url: /tr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## giriiş

Daha fazla güvenlik için bir PDF'yi dijital olarak imzalamanız ve bir zaman damgası eklemeniz gerekti mi? İster yasal belgeler, sözleşmeler veya güvenli kimlik doğrulaması gerektiren herhangi bir şey üzerinde çalışıyor olun, zaman damgalı bir dijital imza fazladan bir güvenilirlik katmanı ekler. Bu eğitimde, PDF belgelerinize bir zaman damgasıyla birlikte dijital imza eklemek için Aspose.PDF for .NET'i nasıl kullanabileceğinizi açıklayacağız. Endişelenmeyin, adım adım ilerleyeceğiz!

## Ön koşullar

Koda dalmadan önce, takip etmek için ayarlamanız gereken birkaç şey var. Başlamanız için ön koşulların hızlı bir kontrol listesi şöyle:

-  Aspose.PDF for .NET Kütüphanesi: Projenizde Aspose.PDF for .NET kütüphanesinin yüklü olması gerekir.[en son sürümü buradan indirin](https://releases.aspose.com/pdf/net/) veya NuGet aracılığıyla projenize ekleyin.
- PDF belgesi: Çalışmak için örnek bir PDF dosyasına ihtiyacınız olacak. İmzalamak istediğiniz projenizin dizininde bir dosya olduğundan emin olun.
-  Dijital Sertifika (PFX dosyası): Dijital bir sertifikanız olduğundan emin olun (bir`.pfx` (dosya) belgeyi dijital olarak imzalamak.
- Zaman Damgası URL'si: Bu, dijital imzaya zaman damgası eklemek için kullanılacak çevrimiçi bir zaman damgası hizmetidir. 
- Temel C# bilgisi: Uzman olmanıza gerek yok, ancak C#'ın temellerini bilmek, kodu anlamanıza ve özelleştirmenize yardımcı olacaktır.

Tüm bu kutuları işaretlediğinizde kodlamaya başlamaya hazırsınız!

## Paketleri İçe Aktar

Başlamak için, aşağıdaki ad alanlarını C# projenize aktarmanız gerekir. Bu, ilgili Aspose.PDF sınıflarına ve işlevlerine erişiminizin olmasını sağlar.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Adım 1: PDF Belgesini Yükleyin

Yapmamız gereken ilk şey imzalamak istediğimiz PDF belgesini yüklemektir. Bunu şu şekilde yapabilirsiniz:

```csharp
// Belge dizininize giden yolu tanımlayın
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini yükleyin
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Bu adım oldukça basittir. Sadece imzalamak istediğimiz belgenin yolunu tanımlıyoruz.`Document` Aspose.PDF'deki sınıf dosyanın yüklenmesini yönetir.

## Adım 2: Dijital İmzayı Ayarlayın

Sonra, PKCS7 sınıfını kullanarak dijital imzayı oluşturacağız ve PFX dosyasını yükleyeceğiz. Bu PFX dosyası, belgeyi imzalamak için gerekli olan sertifikanızı ve özel anahtarınızı içerir.

```csharp
// .pfx dosyanızın yolu
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// İmza nesnesini başlat
PdfFileSignature signature = new PdfFileSignature(document);

// PFX dosyasını bir parola ile yükleyin
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 Bu noktada, Aspose'a belgeyi imzalamak için dijital sertifikanızı kullanmasını söylüyorsunuz.`PKCS7`nesnesi tüm kriptografik işi sizin yerinize halleder, böylece siz ince ayrıntılarla uğraşmak zorunda kalmazsınız.

## Adım 3: Zaman Damgası Ayarlarını Ekleyin

Sağlam bir dijital imzanın temel bileşenlerinden biri zaman damgasıdır. Bu, sertifikanın süresi dolduktan sonra bile belgenin imzasının doğrulanabilmesini sağlar. Çevrimiçi bir zaman damgası otoritesi kullanarak zaman damgasını ayarlayalım.

```csharp
// Zaman damgası ayarlarını tanımlayın
TimestampSettings timestampSettings = new TimestampSettings("https://zaman_damganız_url", "kullanıcı:şifre");

// PKCS7 nesnesine zaman damgası ayarları ekleyin
pkcs.TimestampSettings = timestampSettings;
```

Burada, imzanıza otomatik olarak bir saat ve tarih sağlayacak olan zaman damgası hizmeti için URL'yi belirtiyorsunuz. Bu, kimlik doğrulamasıyla veya kimlik doğrulaması olmadan yapılabilir.

## Adım 4: İmzanın Yerini ve Görünümünü Tanımlayın

Şimdi, imzanın PDF'de nerede görüneceğini ve boyutlarını tanımlayacağız. İmza kutusunun sayfadaki konumunu ve boyutunu özelleştirebilirsiniz.

```csharp
//İmzanın görünümünü ve yerini tanımlayın (sayfa 1, belirtilen dikdörtgenle)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Burada, imzayı PDF'in ilk sayfasında (100, 100) koordinatlarına yerleştiren, genişliği 200 ve yüksekliği 100 olan bir dikdörtgen tanımlıyoruz. Bu değerleri tasarımınıza uyacak şekilde değiştirebilirsiniz.

## Adım 5: PDF Belgesini İmzalayın

Her şey ayarlandıktan sonra, dijital imzayı PDF'ye uygulama zamanı geldi. Bu adım, sertifikayı, zaman damgasını ve konumlandırmayı tek bir basit komutta birleştirir.

```csharp
// Belgenin ilk sayfasını imzalayın
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

İşte olanlar:
- 1: İmzanın ilk sayfaya uygulanması gerektiğini belirtir.
- "İmza Nedeni": Belgeyi neden imzaladığınızı burada belirtebilirsiniz.
- "İletişim": İmzalayanın iletişim bilgilerini girin.
- "Konum": İmzalayanın konumunu belirtin.
- true: Bu boolean değeri imzanın belgede görünür olup olmadığını belirtir.
- rect: Daha önce tanımladığımız dikdörtgen imzanın boyutunu ve konumunu belirtir.
- pkcs: PKCS7 nesnesi dijital sertifika ve zaman damgası ayarlarını içerir.

## Adım 6: İmzalanmış PDF'yi Kaydedin

Belge imzalandıktan sonra geriye sadece kaydetmek kalır. Hem orijinal hem de imzalanmış sürümleri saklamak için yeni bir dosya adı seçebilirsiniz.

```csharp
// İmzalanmış PDF belgesini kaydedin
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Yeni imzaladığınız ve zaman damgası eklediğiniz PDF artık belirtilen dizine kaydedildi!

## Çözüm

Ve işte karşınızda! Aspose.PDF for .NET kullanarak bir PDF'yi zaman damgasıyla başarıyla dijital olarak imzaladınız. Bu süreç belgelerinizin gerçekliğini ve bütünlüğünü garanti altına alarak hem size hem de alıcıya gönül rahatlığı sağlar. Dijital imzalar günümüzün dijital dünyasında giderek daha da önemli hale geliyor, bu nedenle bu süreçte ustalaşmak kesinlikle sahip olunmaya değer bir beceridir.

## SSS

### Sertifika için farklı bir dosya formatı kullanabilir miyim?  
Evet, ancak eğitim, dijital sertifikalar için en yaygın format olan PFX dosyasının kullanımına odaklanıyor.

### Zaman damgasını uygulamak için internet bağlantısına ihtiyacım var mı?  
Evet, zaman damgası çevrimiçi bir zaman damgası yetkilisinden alındığı için internet erişimine ihtiyacınız olacak.

### PDF'de birden fazla sayfayı imzalayabilir miyim?  
 Kesinlikle! Değiştirebilirsiniz`signature.Sign()` birden fazla sayfayı hedeflemek veya tüm sayfalarda döngü oluşturmak için bir yöntem.

### PFX dosya şifresi yanlışsa ne olur?  
Şifreniz yanlışsa istisna alırsınız, bu yüzden şifrenizi doğru girdiğinizden emin olun.

### İmzayı görünmez yapabilir miyim?  
 Evet, geçebilirsin`false` için`Sign` İmzayı görünmez yapmak için metodun görünürlük parametresi.