---
title: PDF Dosyasındaki Sayfa Bölgesinden Metni Çıkar
linktitle: PDF Dosyasındaki Sayfa Bölgesinden Metni Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla .NET için Aspose.PDF kullanarak PDF'deki belirli bir bölgeden metni nasıl çıkaracağınızı öğrenin. Belgelerinizden metni verimli bir şekilde toplayın ve kaydedin.
type: docs
weight: 190
url: /tr/net/programming-with-text/extract-text-from-page-region/
---
## giriiş

PDF'lerle çalışmak, ister formlardan, tablolardan veya bir belgenin belirli bölümlerinden veri çekmek olsun, genellikle belirli içerikleri çıkarmayı gerektirir. Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF'nin belirli bir bölgesinden metnin nasıl çıkarılacağını ele alacağız. Tüm bir belgeyi elemek yerine, metnin tam olarak nerede bulunduğunu belirleyip verimli bir şekilde çıkaracağız.

## Ön koşullar

Koda geçmeden önce aşağıdaki öğelerin yerinde olduğundan emin olun:

1.  Aspose.PDF for .NET: Eğer henüz yapmadıysanız, Aspose.PDF for .NET kütüphanesini indirip kurun.[.NET için Aspose.PDF'yi indirin](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio gibi herhangi bir .NET geliştirme ortamı.
3. .NET Framework: Projenizin uygun .NET Framework ile kurulduğundan emin olun.
4. PDF Belgesi: Metni çıkaracağımız örnek PDF.

 Bunu yapabileceğini unutma[ücretsiz deneme alın](https://releases.aspose.com/) Aspose.PDF'yi kullanın veya[geçici lisans](https://purchase.aspose.com/temporary-license/) tam işlevsellik için.

## Gerekli Paketleri İçe Aktarma

Aspose.PDF for .NET ile çalışmaya başlamak için, gerekli ad alanlarını projenize aktarmanız gerekir. Bu paketler, PDF belgelerini işlemek için gerekli sınıfları ve yöntemleri sağlar.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Adım 1: Belge Dizinini Ayarlama ve PDF'yi Yükleme

İlk adım PDF dosyanızın nerede bulunduğunu belirtmek ve onu projenize yüklemektir. Çalışmak istediğiniz PDF dosyasına yerel bir dizin yolu kullanabilirsiniz.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini açın
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Bu adım, PDF dosyasının düzgün bir şekilde yüklendiğinden ve üzerinde çalışılmaya hazır olduğundan emin olmanızı sağlar.`Document` Aspose.PDF kütüphanesinden gelen sınıf, PDF dosyasını düzenlemenize olanak tanır.

## Adım 2: Çıkarım için Metin Emiciyi Başlatın

 Bu adımda bir tane oluşturuyoruz`TextAbsorber` PDF belgesinden metin çıkarmak için tasarlanmış nesne.`TextAbsorber` esnektir ve belirli bölgelere veya sayfalara odaklanacak şekilde özelleştirilebilir.

```csharp
// Metni çıkarmak için bir TextAbsorber nesnesi oluşturun
TextAbsorber absorber = new TextAbsorber();
```

 The`TextAbsorber`class, belirttiğiniz sınırlar içerisindeki tüm metni yakalayan güçlü bir araçtır.

## Adım 3: Metnin Çıkarılacağı Bölgeyi Tanımlayın

İşte sihir burada gerçekleşir. Metni tüm sayfadan çekmek yerine, çıkarmayı sayfanın belirli bir dikdörtgen bölgesiyle sınırlayabiliriz. İçeriğinizin tam olarak nerede bulunduğunu bildiğinizde bu mükemmeldir.

```csharp
// Metin çıkarmayı belirli bir bölgeyle sınırla
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

 The`Rectangle` nesne, metnin çıkarılacağı alanın koordinatlarını (nokta cinsinden) tanımlamanıza olanak tanır.`TextSearchOptions.LimitToPageBounds` yalnızca belirtilen dikdörtgenin içindeki metnin çıkarılmasını sağlar.

## Adım 4: İstenilen Sayfada Absorber'ı Kabul Edin

 Bölgeyi kurduktan sonraki adım, kabul etmektir.`TextAbsorber` Metni çıkarmak istediğiniz belirli sayfa için. Burada, PDF'nin ilk sayfasına odaklanacağız.

```csharp
// İlk sayfa için emiciyi kabul edin
pdfDocument.Pages[1].Accept(absorber);
```

 Arayarak`Accept` Sayfadaki yöntemi kullanarak, Aspose.PDF'e emiciyi çalıştırmasını ve tanımlanan bölgeden metni toplamasını talimat veriyoruz.

## Adım 5: Çıkarılan Metni Alın ve Saklayın

 Emici işini yaptıktan sonra, çıkarılan metni toplama ve kaydetme zamanı gelir. Bu adım, metni alıp bir`.txt` dosya.

```csharp
// Çıkarılan metni alın
string extractedText = absorber.Text;

// Çıkarılan metni kaydetmek için bir yazar oluşturun
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

// Metni dosyaya yaz
tw.WriteLine(extractedText);

// Akışı kapat
tw.Close();
```

 Burada,`TextWriter` sınıf, çıkarılan metni bir metin dosyasına yazmak için kullanılır. Bu, çıkarılan içeriğinizin daha sonraki kullanım için güvenli bir şekilde saklanmasını sağlar.

## Çözüm

 PDF belgesindeki belirli bir bölgeden metin çıkarmak, özellikle formlar veya tablolar gibi yapılandırılmış içeriklerle uğraşırken inanılmaz derecede yararlı olabilir. .NET için Aspose.PDF'yi kullanarak, bu görevi yalnızca birkaç satır kodla gerçekleştirebilirsiniz. Bir bölge tanımlayarak, bir`TextAbsorber`ve çıkarılan metni kaydederek, PDF'inizden neyin çıkarılacağı konusunda tam kontrole sahip olursunuz.

İster küçük bir proje üzerinde çalışın ister büyük belgeleri yönetin, bu yöntem tüm belgeyi taramadan PDF'lerinizden ilgili verileri çıkarmanın etkili bir yolunu sunar.

## SSS

### Birden fazla sayfadan aynı anda metin çıkarabilir miyim?
 Evet, yineleme yoluyla`Pages` koleksiyonu`pdfDocument` , uygulayabilirsiniz`TextAbsorber` birden fazla sayfaya.

### Peki ya metin PDF'in farklı bir bölgesindeyse?
 Kolayca ayarlayabilirsiniz`Rectangle` Metninizin bulunduğu bölgeye uyacak şekilde koordinatlar.

### Bu taranmış PDF'lerde de işe yarıyor mu?
Hayır, taranmış PDF'lerin görüntüleri metne dönüştürmek için OCR'ye (Optik Karakter Tanıma) ihtiyacı vardır. Aspose.PDF ayrıca OCR özellikleri de sunar.

### Belirli anahtar kelimelere dayalı metin çıkarmanın bir yolu var mı?
 Evet, kullanabilirsiniz`TextFragmentAbsorber` Anahtar kelime tabanlı metin çıkarımı için.

### Şifrelenmiş bir PDF'den metni nasıl çıkarabilirim?
Öncelikle doğru şifreyi girerek PDF'i şifresini çözmeniz, ardından metin çıkarma işlemine geçmeniz gerekecektir.