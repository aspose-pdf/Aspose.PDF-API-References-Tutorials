---
title: PDF Dosyasına İçindekiler Ekle
linktitle: PDF Dosyasına İçindekiler Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF'ye İçindekiler Tablosu eklemeyi öğrenin. Bu adım adım kılavuz süreci basitleştirir ve belgeleriniz içinde kolay gezinmeyi sağlar.
type: docs
weight: 40
url: /tr/net/programming-with-document/addtoc/
---
## giriiş

Uzun bir PDF'te sonsuza kadar kaydırıp, iyi düzenlenmiş bir İçindekiler Tablosu olmasını istediğiniz oldu mu? İşte, bugün şanslı gününüz! Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyanıza bir İçindekiler Tablosu eklemeyi öğreneceksiniz. Karmaşık bir rapor, bir e-Kitap veya bir iş teklifi üzerinde çalışıyor olun, İçindekiler Tablosu belgenizi profesyonel, gezilebilir bir şahesere dönüştürebilir.

## Ön koşullar

Koda geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1. .NET için Aspose.PDF: Aspose.PDF kütüphanesini indirip kurduğunuzdan emin olun. Buradan indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
   
2. Geliştirme Ortamı: Makinenizde Visual Studio gibi bir .NET geliştirme ortamının kurulu olduğundan emin olun.

3.  Lisans: Lisansınız yoksa ücretsiz deneme alabilir veya geçici lisans talebinde bulunabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

## Paketleri İçe Aktar

Başlamak için, kod dosyanızın başına gerekli ad alanlarını içe aktardığınızdan emin olun. İşte nasıl:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Bu ad alanları, PDF'ye özgü işlevlere erişmenizi ve belgenizdeki metin öğelerini düzenlemenizi sağlar.

Bu görevi küçük parçalara bölelim. Her adım, PDF belgenize bir TOC oluşturma ve ekleme sürecinde size rehberlik edecektir.

## Adım 1: PDF Belgesini Yükleyin

Yapmamız gereken ilk şey, İçindekiler bölümünü eklemek istediğimiz mevcut PDF dosyasını yüklemek.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 Bu adımda, belge dizinine giden yolu belirtiyoruz ve PDF'yi şu şekilde yüklüyoruz:`Document` nesne. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` dosyanızın gerçek yolu ile.

## Adım 2: İçindekiler için Yeni Bir Sayfa Ekleyin

Sonra, PDF belgesinin başına yeni bir sayfa ekliyoruz. Bu sayfa İçindekiler Tablosunu barındıracaktır.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

İçindekiler sayfasını başa ekleyerek, okuyucuların PDF'de ilk gördükleri şeyin bu sayfa olmasını sağlıyoruz.

## Adım 3: İçindekiler Bilgi Nesnesi Oluşturun

Şimdi, TOC bilgisini temsil edecek bir nesne oluşturalım. Ayrıca, TOC'yi öne çıkarmak için bir başlık da ekleyeceğiz.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Burada, İçindekiler tablosunun başlığını "İçindekiler" olarak ayarladık, yazı tipini büyüttük ve vurgu için kalınlaştırdık.

## Adım 4: İçindekiler Öğelerini Tanımlayın

Bu adımda, TOC'de görüntülenecek öğeleri (veya başlıkları) tanımlarız. Bu öğeler, okuyucuların belgenin belirli bölümlerine gitmesine yardımcı olur.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

PDF'deki farklı sayfalara karşılık gelen İçindekiler öğelerimiz olarak hizmet edecek bir dizi dize oluşturduk.

## Adım 5: İçindekiler Başlıklarını Oluşturun

Şimdi en önemli kısma geliyoruz: İçindekiler tablosuna başlıklar eklemek ve bunları ilgili sayfalara bağlamak.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

İşte olanlar:
- Başlık: Bir tane yaratıyoruz`Heading` nesne ve ekle`TextSegment` ona.
- Hedef Sayfa: Her başlığın bağlantı vereceği sayfayı ayarlıyoruz.
- En Üst Konum: Başlığın sayfada hangi konuma işaret edeceğini belirtiyoruz.
- Metin: Her başlık, daha önce oluşturduğumuz diziden kendi başlığını alır.

Bu döngü, İçindekiler tablosundaki ilk iki öğe için başlıklar oluşturur ve bunları ilgili sayfalara bağlar.

## Adım 6: PDF'yi İçindekiler tablosuyla birlikte kaydedin

Son olarak, tüm İçindekiler öğelerini ekledikten sonra, güncellenmiş PDF'yi kaydetme zamanı geldi.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

Dosya artık PDF'e eklenen TOC ile kaydedildi. Tebrikler—İçindekiler Tablosunu başarıyla eklediniz!

## Adım 7: Onay Mesajı

Kullanıcıya işlemin tamamlandığını bildirmek için konsolda basit bir mesaj göstereceğiz.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Çözüm

Ve işte karşınızda! .NET için Aspose.PDF ile bir PDF'e İçindekiler Tablosu eklemek yalnızca kolay değil, aynı zamanda özelleştirilebilir. Basit gezinme bağlantıları veya karmaşık yapılar oluşturmanız gerekip gerekmediğine bakılmaksızın, bu araç sizin için her şeyi yapar. Bu yüzden, bir dahaki sefere uzun bir PDF üzerinde çalıştığınızda, profesyonel bir dokunuş için İçindekiler Tablosu eklemeyi unutmayın!

## SSS

### Aspose.PDF'deki İçindekiler bölümünün görünümünü özelleştirebilir miyim?  
Evet, yazı tipi, boyutu ve hizalama dahil olmak üzere İçindekiler tablosunun görünümünü tamamen özelleştirebilirsiniz.

### İçindekiler tablosuna alt başlıklar nasıl eklenir?  
 Alt başlıkları ayarlayarak ekleyebilirsiniz.`Heading` seviye (örneğin,`Heading(2)`) hiyerarşik bir İçindekiler tablosu oluşturmak için.

### Belge değiştiğinde İçindekiler tablosunun otomatik olarak güncellenmesi mümkün müdür?  
Hayır, İçindekiler tablosu otomatik olarak güncellenmeyecek. Belge yapısı değişirse yeniden oluşturmanız gerekecek.

### İçindekiler girişlerini harici belgelere bağlayabilir miyim?  
Evet, İçindekiler girişlerini harici PDF'lere veya URL'lere bağlamak için köprü metinleri kullanabilirsiniz.

### Aspose.PDF çok seviyeli İçindekiler tablosunu destekliyor mu?  
Evet, Aspose.PDF alt bölümlere sahip karmaşık belgeler için çok seviyeli İçindekiler tablosunu destekler.