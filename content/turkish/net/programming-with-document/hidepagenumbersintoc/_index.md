---
title: İçindekiler Tablosunda Sayfa Numaralarını Gizle
linktitle: İçindekiler Tablosunda Sayfa Numaralarını Gizle
second_title: Aspose.PDF for .NET API Referansı
description: İçindekiler Tablosunda sayfa numaralarını Aspose.PDF for .NET kullanarak nasıl gizleyeceğinizi öğrenin. Profesyonel PDF'ler oluşturmak için bu ayrıntılı kılavuzu kod örnekleriyle takip edin.
type: docs
weight: 220
url: /tr/net/programming-with-document/hidepagenumbersintoc/
---
## giriiş

PDF'lerle çalışırken, bazen bir İçindekiler Tablosu (TOC) oluşturmak isteyebilirsiniz ancak sayfa numaralarını gizleyerek işleri düzgün tutmak isteyebilirsiniz. Belki de belge onlarsız daha iyi akıyor veya belki de estetik bir tercih. Nedeniniz ne olursa olsun, .NET için Aspose.PDF ile çalışıyorsanız, bu eğitim size TOC'nizdeki sayfa numaralarını tam olarak nasıl gizleyeceğinizi gösterecektir.

## Ön koşullar

Başlamadan önce, yerinde olması gereken birkaç şey var. İşte hızlı bir kontrol listesi:

- Visual Studio Kurulu: Kodlama yapabilmek için çalışan bir Visual Studio sürümüne ihtiyacınız olacak.
- Aspose.PDF for .NET Kütüphanesi: Aspose.PDF for .NET kütüphanesini yüklediğinizden emin olun.
  -  İndirme bağlantısı:[.NET için Aspose.PDF](https://releases.aspose.com/pdf/net/)
- Geçici Lisans: Özellikleri test ediyorsanız, geçici bir lisansa sahip olmak faydalı olacaktır.
  -  Geçici lisans:[Buradan edinin](https://purchase.aspose.com/temporary-license/)

## Paketleri İçe Aktar

Koda atlamadan önce, C# projenize aşağıdaki ad alanlarını içe aktardığınızdan emin olun. Bunlar, PDF belgeleriyle çalışmak ve İçindekiler Tablonuzu (TOC) oluşturmak için gerekli sınıfları ve yöntemleri sağlayacaktır.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Artık ortamınız hazır ve paketler içe aktarılmış olduğuna göre, sürecin her adımını parçalara ayıralım. Kolayca takip edebilmeniz için kodun her bölümünü açıklığa kavuşturacağız.

## Adım 1: PDF Belgenizi Başlatın

İlk yapmamız gereken yeni bir PDF belgesi oluşturmak ve İçindekiler (TOC) sayfası eklemek.


```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: Bu, çıktı dosyanızın kaydedileceği dizindir.
- Document(): Yeni bir PDF belgesi başlatır.
- Pages.Add(): Belgeye daha sonra İçindekiler bölümünüzü tutacak yeni bir boş sayfa ekler.

## Adım 2: İçindekiler Bilgilerini ve Başlığını Ayarlayın

Daha sonra, İçindekiler tablosunun en üstünde görünecek başlığı ayarlamak da dahil olmak üzere İçindekiler tablosu bilgilerini tanımlayacağız.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Bu nesne TOC hakkındaki tüm bilgileri tutar.
- TextFragment: İçindekiler başlığının metnini temsil eder, burada bunu "İçindekiler Tablosu" olarak ayarladık.
- FontStyle: İçindekiler başlığının stilini, boyutunu 20 olarak ayarlayıp kalınlaştırarak belirliyoruz.
- tocPage.TocInfo: İçindekiler bilgisini, İçindekiler'in görüntüleneceği sayfaya atıyoruz.

## Adım 3: İçindekiler Tablosunda Sayfa Numaralarını Gizle

Şimdi eğlenceli kısma geçelim! İşte TOC'yi sayfa numaralarını gizleyecek şekilde yapılandıracağımız yer.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Bu, sayfa numaralarını gizleyen sihirli anahtardır. Bunu şu şekilde ayarlayın:`false`ve sayfa numaraları İçindekiler'de görünmeyecektir.
- FormatArrayLength: Bunu 4 olarak ayarlıyoruz; bu, İçindekiler başlıklarının dört düzeyi için biçimlendirme tanımlamak istediğimizi gösteriyor.

## Adım 4: İçindekiler Biçimlendirmesini Özelleştirin

İçindekiler tablonuza daha fazla stil katmak için, artık farklı düzeylerdeki başlıklar için biçimlendirme tanımlayacağız.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Bu dizi TOC girdilerinin biçimlendirmesini kontrol eder. Her dizin farklı bir başlık düzeyini temsil eder.
- Kenar Boşluğu ve Metin Stili: Her başlık düzeyi için kenar boşluklarını ayarlıyoruz ve kalın, italik, altı çizili gibi yazı tipleri uyguluyoruz.

## Adım 5: Belgeye Başlıklar Ekleyin

Son olarak İçindekiler bölümünün parçası olacak gerçek başlıkları ekleyelim.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Başlık ve TextSegment: Bunlar TOC'nizde görünecek başlıkları temsil eder. Her seviye kendi başlığını alır.
- IsAutoSequence: Başlıkları otomatik olarak numaralandırır.
- IsInList: Her başlığın İçindekiler tablosunda görünmesini sağlar.

## Adım 6: Belgeyi Kaydedin

Her şey ayarlandıktan sonra PDF belgesini belirttiğiniz çıktı dosyasına kaydedin.

```csharp
doc.Save(outFile);
```

Ve işte bu kadar! İçindekiler Tablosu olan bir PDF'i başarıyla oluşturdunuz ve sayfa numaraları gizlendi!

## Çözüm

PDF'de İçindekiler Tablosu oluşturmak ve sayfa numaralarını gizlemek zor görünebilir, ancak .NET için Aspose.PDF ile bu çok kolaydır. Bu adım adım kılavuzu izleyerek, İçindekiler formatını nasıl özelleştireceğinizi, sayfa numaralarını nasıl gizleyeceğinizi ve başlıklarınıza farklı stiller nasıl uygulayacağınızı öğrendiniz. Artık tam ihtiyaçlarınıza göre uyarlanmış profesyonel PDF'ler oluşturabilirsiniz.

## SSS

### İçindekiler tablosunda belirli başlıklar için sayfa numaraları gösterebilir miyim?
Hayır, Aspose.PDF tüm TOC için sayfa numaralarını gizler veya gösterir. Belirli girdiler için bunları seçici olarak gizleyemezsiniz.

### İçindekiler tablosuna daha fazla seviye eklemek mümkün mü?
 Evet, artırabilirsiniz`FormatArrayLength` İçindekiler başlıklarının daha fazla düzeyini tanımlamak için.

### Tüm İçindekiler girişlerinin yazı tipini nasıl değiştirebilirim?
 Yazı tipini değiştirerek değiştirebilirsiniz.`TextState.Font` her seviyedeki mülk`FormatArray`.

### İçindekiler bölümüne köprü metni ekleyebilir miyim?
 Evet, her İçindekiler girişini belgedeki belirli bir bölüme bağlamak için`Heading.TocPage` mülk.

### Aspose.PDF için lisansa ihtiyacım var mı?
Evet, üretim kullanımı için geçerli bir lisans gereklidir. Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) Özellikleri test etmek için.