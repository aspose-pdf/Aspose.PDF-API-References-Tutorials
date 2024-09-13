---
title: Üstbilgi Altbilgide Yüzen Kutu Kullanarak Sayfa Numarası
linktitle: Üstbilgi Altbilgide Yüzen Kutu Kullanarak Sayfa Numarası
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimde Aspose.PDF for .NET ile Yüzen Kutu kullanarak PDF üst bilgi ve alt bilginize kolayca sayfa numaraları ekleyin.
type: docs
weight: 150
url: /tr/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## giriiş

PDF belgelerini programatik olarak yönetmeye gelince, Aspose.PDF for .NET olağanüstü bir araç olarak öne çıkıyor. .NET uygulamalarında PDF dosyalarını oluşturma, düzenleme ve yönetme şeklimizi basitleştiriyor. İster fatura, ister rapor veya herhangi bir belge türü oluşturuyor olun, sayfa numaralarını zarif bir şekilde eklemek PDF'lerinizin profesyonelliğini ve organizasyonunu iyileştirebilir. Bu eğitimde, bir Kayan Kutu kullanarak PDF'nizin üst bilgisine ve alt bilgisine sayfa numaralarının nasıl ekleneceğini derinlemesine inceliyoruz. Başlamaya hazır mısınız? Hadi başlayalım!

## Ön koşullar

PDF düzenleme dünyasına doğru bu heyecan verici yolculuğa başlamadan önce, sahip olmanız gereken birkaç şey var:

### .NET Ortam Kurulumu
.NET geliştirme ortamınız olduğundan emin olun. .NET uygulamaları için geliştiriciler arasında popüler bir tercih olan Visual Studio'yu kullanabilirsiniz.

### Aspose.PDF Kütüphanesi
Aspose.PDF kütüphanesini yükleyin. Bunu web sitesinden kolayca indirebilirsiniz:

- [.NET için Aspose.PDF'yi indirin](https://releases.aspose.com/pdf/net/)

### C# Programlamanın Temel Bilgileri
C# hakkında temel bir anlayışa sahip olmak, bu eğitimde sunulan kavramları ve kod parçacıklarını kavramanıza yardımcı olacaktır.

### Belgelere Erişim
 Her zaman sahip olmak faydalıdır[Aspose.PDF Belgeleri](https://reference.aspose.com/pdf/net/) referans olması ve ek işlevlerin daha derinlemesine incelenmesi için kullanışlıdır.

## Paketleri İçe Aktar

Başlamak için, projenize gerekli paketleri içe aktarmanız gerekir. Bu, Aspose.PDF derlemesinin kodunuzda kullanıma erişilebilir olmasını sağlar. İşte nasıl yapılacağı:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Şimdi, Yüzen Kutu kullanarak sayfa numaraları ekleme sürecini yönetilebilir adımlara bölelim. Biz ilerlerken takip edin.

## Adım 1: Belge Ortamınızı Ayarlayın

PDF belgenizin saklanacağı dizini belirterek başlayalım. Bu önemlidir çünkü çıktı dosyanızın nereye kaydedileceğini belirler.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`YOUR DOCUMENT DIRECTORY` Çıktı PDF dosyasını kaydetmek istediğiniz seçtiğiniz yol ile.

## Adım 2: Belgeyi Örneklendirin

 Yeni bir PDF belgesi oluşturmak bir sonraki adımdır. Bu,`Document` Aspose.PDF kütüphanesinden sınıf.

```csharp
// Belge örneğini örneklendir
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Burada, yeni bir örnek oluşturuyoruz`Document` Manipülasyon tuvalimiz olarak hizmet eden sınıf.

## Adım 3: Yeni Bir Sayfa Ekleyin

Şimdi PDF belgemize bir sayfa ekleyelim. Her PDF'in en az bir sayfaya ihtiyacı vardır, değil mi?

```csharp
// PDF belgesine bir Sayfa ekleyin
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Bu kod parçacığı, belgemize yeni bir sayfa ekleyerek, sayfa numaralarının bulunduğu yüzen kutumuz da dahil olmak üzere içerik almaya hazır hale getirir.

## Adım 4: Yüzen Kutu Oluşturun

 Sırada sayfa numarasını tutacak Yüzen Kutumuzu oluşturma zamanı.`FloatingBox`class, içeriği sayfada serbestçe konumlandırmamızı sağlar.

```csharp
// FloatingBox sınıfının yeni bir örneğini başlatır
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Burada parametreler`(140, 80)` Yüzen Kutunun genişliğini ve yüksekliğini belirtin. Bu değerleri düzen tercihinize göre ayarlayabilirsiniz.

## Adım 5: Yüzen Kutunun Konumlandırılması

 Konumlandırma anahtardır! Sayfa numarasının sayfada nerede görüneceğini belirlemek istersiniz.`Left` Ve`Top` pozisyonu belirtmek için özellikler.

```csharp
// Paragrafın sol konumunu gösteren kayan nokta değeri
box1.Left = 2;
// Paragrafın en üst konumunu gösteren kayan nokta değeri
box1.Top = 10;
```
Bu değerler, Yüzen Kutunun sayfadaki yerleşimini belirler. Belgeniz için en iyi görüneni görmek için bunları denemekten çekinmeyin.

## Adım 6: Sayfa Numarası Makrosuyla Metin Ekleme

Şimdi sayfa numarasını dinamik olarak gösteren bir dize ekleyeceğiz. İşte sihir burada gerçekleşiyor!

```csharp
// Makroları FloatingBox'ın paragraf koleksiyonuna ekleyin
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 Bu durumda,`($p/ $P)`geçerli sayfa numarasını görüntüleyecek bir makrodur (`$p`) ve toplam sayfa sayısı (`$P`). Sonuç olarak metni "Sayfa: 1/5" gibi bir şekilde okunacak şekilde biçimlendirir.

## Adım 7: Sayfaya Yüzen Kutuyu Ekleyin

Yeni oluşturduğumuz sayfaya, sayfa numarası metniyle birlikte Yüzen Kutu'yu eklemenin zamanı geldi.

```csharp
// Sayfaya bir floatingBox ekleyin
page.Paragraphs.Add(box1);
```
Bu satır, esasen Yüzen Kutunuzu sayfaya gömer ve onu belgenin düzeninin bir parçası haline getirir. 

## Adım 8: Belgenizi Kaydedin

Son olarak, çalışmanızı kaydetmeyi unutmayın! Son adım, PDF belgenizi uygun bir dosya adıyla kaydetmektir.

```csharp
// Belgeyi kaydet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Belirtilen yolun istediğiniz dosya adını içerdiğinden emin olun. Şimdi, sayfa numaralarıyla muhteşem PDF'niz oluşturuldu! 

## Çözüm

İşte karşınızda, arkadaşlar! Aspose.PDF for .NET kullanarak PDF'nizin üst bilgisine ve alt bilgisine sayfa numaraları eklemek bu kadar basit. Sadece birkaç satır kodla, uygulamalarınızda belge işleme konusunda ustalaşma yolculuğuna çıktınız. Farklı düzenler ve biçimlendirmelerle denemeler yapmaktan çekinmeyin; sonuçta yaratıcılığın sınırı yoktur! O profesyonel belgeyi oluşturmaya hazır mısınız? Kodlama şapkanızı alın ve denemeler yapmaya başlayın.

## SSS

### Sayfa numarası metninin görünümünü özelleştirebilir miyim?  
 Evet, yazı tipi boyutu, rengi ve stili gibi metin özelliklerini ayarlayarak özelleştirebilirsiniz.`TextFragment` özellikler.

### Aspose.PDF'i kullanmak ücretsiz mi?  
 Aspose.PDF ücretsiz deneme sunsa da, üretim kullanımı için ücretli bir üründür.[buradan satın al](https://purchase.aspose.com/buy).

### Daha detaylı dokümanları nerede bulabilirim?  
 Kapsamlı belgeleri şurada bulabilirsiniz:[Aspose.PDF Belgeleri sitesi](https://reference.aspose.com/pdf/net/).

### Birden fazla sayfaya üstbilgi ve altbilgi nasıl uygularım?  
Belgenizdeki tüm sayfalar arasında dolaşabilir ve her birine benzer şekilde Kayan Kutu uygulayabilirsiniz.

### Ek özellikler için desteğe ihtiyacım olursa ne olur?  
Herhangi bir ek soru veya destek için şu adresi ziyaret edebilirsiniz:[Aspose Forum](https://forum.aspose.com/c/pdf/10).