---
title: Eksik Yazı Tiplerini Değiştir
linktitle: Eksik Yazı Tiplerini Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET'i kullanarak PDF belgelerindeki eksik yazı tiplerini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 260
url: /tr/net/document-conversion/replace-missing-fonts/
---
## giriiş

Hiç bir PDF belgesini açıp bazı yazı tiplerinin eksik olduğunu gördünüz mü? Sinir bozucu olabilir, değil mi? Eksik yazı tipleri, oluşturucunun amaçladığından tamamen farklı görünen bir belgeye yol açabilir. Neyse ki, .NET için Aspose.PDF ile eksik yazı tiplerini kolayca değiştirebilir ve PDF belgelerinizin amaçlanan görünümünü korumasını sağlayabilirsiniz. Bu eğitimde, sizi adım adım bu süreçte yönlendirerek basit ve anlaşılır hale getireceğiz.

## Ön koşullar

Başlamadan önce, yerinde olması gereken birkaç şey var:

1.  .NET için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Buradan indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Kodunuzu yazıp test edebileceğiniz bir geliştirme ortamı.
3. Temel C# Bilgisi: C# programlamaya aşina olmak, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Adım 1: Belge Dizininizi Ayarlayın

Öncelikle, belgeler dizininize giden yolu belirtmeniz gerekir. Giriş PDF dosyanızın bulunduğu ve çıktı dosyasının kaydedileceği yer burasıdır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Orijinal Yazı Tipini Başlatın

Sonra, eksik olabilecek orijinal yazı tipini bulmaya çalışacaksınız. Bu durumda, "AgencyFB"yi arıyoruz.

```csharp
Aspose.Pdf.Text.Font originalFont = null;
try
{
    originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
    //Hedef bilgisayarda yazı tipi eksik
    FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

Burada, yazı tipini bulmaya çalışıyoruz. Bulunamazsa, istisnayı yakalayıp daha yaygın bir yazı tipi olan "Arial" ile değiştiriyoruz. Bu, orijinal yazı tipi mevcut olmasa bile belgenizin hala iyi görünmesini sağlar.

## Adım 3: PDF Belgesini Yükleyin

Şimdi, işlemek istediğiniz PDF belgesini yükleyelim. Giriş dosya yolunu belirtmeniz gerekecek.

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
```

 Bu adımda yeni bir tane oluşturuyoruz`FileInfo` çıktı dosyası için nesne ve giriş PDF belgesini yeni bir dosyaya yükleyin`Document` nesne.

## Adım 4: PDF Belgesini Dönüştürün

Belgeyi kaydetmeden önce, onu belirli bir PDF biçimine dönüştürmek iyi bir fikirdir. Bu durumda, onu elektronik belgelerin uzun süreli arşivlenmesi için bir standart olan PDF/A-1B biçimine dönüştüreceğiz.

```csharp
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

Bu satır PDF'yi dönüştürür ve hataları belirtilen bir XML dosyasına kaydeder. Dönüştürme sırasında herhangi bir sorun varsa, bunlar "log.xml" dosyasına kaydedilir.

## Adım 5: Güncellenen PDF Belgesini Kaydedin

Son olarak güncellenen PDF belgesini değiştirilen yazı tipleriyle kaydetmenin zamanı geldi.

```csharp
pdf.Save(fileNew.FullName);
```

Bu satır, değiştirilen PDF'yi belirtilen çıktı dosyası yoluna kaydeder. Ve böylece, PDF belgenizdeki eksik yazı tiplerini başarıyla değiştirmiş oldunuz!

## Çözüm

PDF belgelerindeki eksik fontları değiştirmek göz korkutucu bir görev olmak zorunda değil. Aspose.PDF for .NET ile font değişimlerini kolayca yönetebilir ve belgelerinizin olması gerektiği gibi görünmesini sağlayabilirsiniz. Bu eğitimde özetlenen adımları izleyerek, belirli fontlar kullanılamadığında bile PDF dosyalarınızın bütünlüğünü koruyabilirsiniz. Böylece, bir dahaki sefere eksik font sorunuyla karşılaştığınızda, tam olarak ne yapmanız gerektiğini bileceksiniz!

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan güçlü bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose kütüphaneyi değerlendirmek için kullanabileceğiniz ücretsiz bir deneme sürümü sunuyor. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### İhtiyacım olan yazı tipi mevcut değilse ne yapmalıyım?
Eksik fontu Aspose.PDF'deki font değiştirme özelliğini kullanarak daha yaygın bir fontla değiştirebilirsiniz.

### PDF'leri diğer formatlara dönüştürmek mümkün müdür?
Kesinlikle! Aspose.PDF, PDF/A, DOCX ve daha fazlası dahil olmak üzere çeşitli formatlara dönüştürmeyi destekler.

### Aspose.PDF için desteği nerede bulabilirim?
 Aspose forumunda destek bulabilir ve soru sorabilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).