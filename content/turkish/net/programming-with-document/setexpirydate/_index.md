---
title: PDF Dosyasında Son Kullanma Tarihini Ayarla
linktitle: PDF Dosyasında Son Kullanma Tarihini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarında son kullanma tarihi ayarlamayı öğrenin. Bu adım adım kılavuzla belge güvenliğini artırın.
type: docs
weight: 300
url: /tr/net/programming-with-document/setexpirydate/
---
## giriiş

Günümüzün dijital çağında, belgeleri yönetmek ve güvence altına almak her zamankinden daha önemli. Belirli bir tarihten sonra otomatik olarak erişilemez hale gelen bir PDF gönderdiğinizi düşünün. Kulağa sihir gibi geliyor, değil mi? Aspose.PDF for .NET ile PDF dosyalarınız için kolayca bir son kullanma tarihi belirleyebilirsiniz. Bu özellik, belirli bir süreden sonra kısıtlanması gereken hassas belgeler için özellikle yararlıdır. Bu eğitimde, bir PDF dosyasında son kullanma tarihi belirleme sürecini adım adım anlatacağız. O halde, kodlama şapkanızı alın ve başlayalım!

## Ön koşullar

Başlamadan önce, yerinde olması gereken birkaç şey var:

1. Geliştirme Ortamı: .NET geliştirme ortamınızın kurulu olduğundan emin olun. Bu, Visual Studio veya .NET'i destekleyen herhangi bir IDE olabilir.
2.  .NET için Aspose.PDF: Aspose.PDF kütüphanesinin kurulu olması gerekir. Bunu henüz yapmadıysanız, şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/pdf/net/).
3. C# Temel Bilgisi: Bu eğitim, C# programlama konusunda temel bir anlayışa sahip olduğunuzu varsayar. C#'a yeniyseniz endişelenmeyin! Bunu basit ve anlaşılır tutacağız.

## Paketleri İçe Aktar

Aspose.PDF'ye başlamak için, C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Bunu şu şekilde yapabilirsiniz:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Bu ad alanları, Aspose.PDF'de PDF belgeleriyle çalışmak için gereken temel işlevlere erişmenizi sağlar.

## Adım 1: Belge Dizininizi Ayarlayın

İlk önce, belgeler dizininize giden yolu belirtmeniz gerekir. Çıktı PDF'niz buraya kaydedilecektir. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızı kaydetmek istediğiniz gerçek yol ile. Programınıza "Hey, dosyalarımı burada saklıyorum!" demeye benzer.

## Adım 2: Belge Nesnesini Örneklendirin

 Daha sonra, yeni bir örnek oluşturmanız gerekir`Document` sınıf. Bu, PDF'nizi oluşturacağınız tuvalinizdir.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Şunu düşünün:`Document` nesneyi boş bir kağıt parçası olarak düşünün. İstediğiniz gibi içerik ekleyebilirsiniz!

## Adım 3: PDF'ye bir Sayfa Ekleyin

Artık belgeniz ayarlandığına göre, ona bir sayfa ekleme zamanı geldi. İçeriğiniz buraya gidecek.

```csharp
doc.Pages.Add();
```

PDF'inizde yeni bir sayfa oluşturdunuz. Bu, düşüncelerinizi not edebileceğiniz defterinize yeni bir sayfa eklemek gibidir.

## Adım 4: Sayfaya Metin Ekleyin

Biraz metin ekleyerek bu sayfayı biraz daha ilgi çekici hale getirelim. Basit bir "Merhaba Dünya" mesajı ekleyelim.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Bu kod satırı PDF'nizin ilk sayfasına bir metin parçası ekler. Sayfanızın en üstüne bir başlık yazmak gibidir!

## Adım 5: Son Kullanma Tarihi için JavaScript Oluşturun

Şimdi eğlenceli kısma geliyoruz! PDF'nin son kullanma tarihini kontrol edecek bir JavaScript eylemi oluşturacaksınız. Mevcut tarih son kullanma tarihini aşarsa, kullanıcıyı uyaran bir mesaj gönderilecektir.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

İşte olanlar:
- Son kullanma yılını ve ayını siz belirlersiniz.
- Bugünün tarihini aldın.
- Bugünün tarihini son kullanma tarihiyle karşılaştırıyorsunuz.
- Eğer bugünün tarihi son kullanma tarihini geçtiyse bir mesaj belirir!

## Adım 6: JavaScript'i PDF Açma Eylemi Olarak Ayarla

Şimdi, JavaScript eylemini PDF belgeniz için açma eylemi olarak ayarlamanız gerekiyor. Bu, JavaScript'in PDF açılır açılmaz çalışacağı anlamına gelir.

```csharp
doc.OpenAction = javaScript;
```

Bu satır, PDF'e birisi açtığında JavaScript'i çalıştırmasını söyler. Takviminizi açtığınız anda çalan bir hatırlatıcı ayarlamak gibidir!

## Adım 7: PDF Belgesini Kaydedin

Son olarak PDF belgenizi son kullanma tarihi özelliğiyle kaydetmenin zamanı geldi. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Bu satır PDF'nizi "SetExpiryDate_out.pdf" adıyla belirtilen dizine kaydeder. Bu, bitmiş sanat eserinizi bir çerçeveye koymak gibidir!

## Çözüm

İşte karşınızda! Aspose.PDF for .NET kullanarak son kullanma tarihi olan bir PDF dosyasını başarıyla oluşturdunuz. Bu özellik yalnızca güvenliği artırmakla kalmaz, aynı zamanda hassas bilgilerin kontrol altında tutulmasını da sağlar. İster sözleşmeler, raporlar veya başka önemli belgeler gönderiyor olun, bir son kullanma tarihi belirlemek oyunun kurallarını değiştirebilir.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF belgeleri oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan güçlü bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose.PDF'in ücretsiz deneme sürümünü kullanabilirsiniz. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.PDF'i nasıl satın alabilirim?
Aspose.PDF'yi şuraya tıklayarak satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).

### Desteğe ihtiyacım olursa ne olur?
Herhangi bir sorunuz varsa veya yardıma ihtiyacınız varsa, şu adresi ziyaret edebilirsiniz:[Aspose destek forumu](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF için geçici lisans alabilir miyim?
 Evet, geçici lisans talebinde bulunabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).