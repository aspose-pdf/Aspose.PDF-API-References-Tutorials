---
title: Başlık Altbilgisindeki Değiştirilebilir Semboller
linktitle: Başlık Altbilgisindeki Değiştirilebilir Semboller
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanarak bir PDF belgesinin üst bilgi ve alt bilgisinde değiştirilebilir sembollerin nasıl kullanılacağını öğrenin.
type: docs
weight: 320
url: /tr/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## giriiş

PDF dosyalarıyla çalışırken, sayfa numaraları, rapor adları veya oluşturulan tarihler gibi dinamik içeriklerle başlıkları ve altbilgileri özelleştirmeniz gereken zamanlar olur. Neyse ki, Aspose.PDF for .NET bu süreci basitleştirir ve sayfa numaraları veya rapor oluşturma ayrıntıları gibi başlıklarda ve altbilgilerde otomatik olarak güncellenen sembollerle PDF'ler oluşturmanıza olanak tanır. Bu makale, yalnızca basit değil aynı zamanda inanılmaz derecede etkili bir şekilde, Aspose.PDF for .NET kullanarak başlıklarda ve altbilgilerde sembolleri değiştirmenin adım adım sürecini size gösterecektir.

## Ön koşullar

Adım adım kılavuza dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  .NET Kütüphanesi için Aspose.PDF –[İndirmek](https://releases.aspose.com/pdf/net/) veya bir tane al[ücretsiz deneme](https://releases.aspose.com/).
- Sisteminizde yüklü Visual Studio veya herhangi bir C# IDE.
- C# ve .NET geliştirme konusunda temel bilgi.
-  Geçerli bir[lisans](https://purchase.aspose.com/temporary-license/) Aspose.PDF için, veya deneme sürümünü kullanabilirsiniz.

## Paketleri İçe Aktar

Başlamak için, .NET için Aspose.PDF işlevselliğini etkinleştirecek gerekli ad alanlarını içe aktarmanız gerekir. Gerekli içe aktarma aşağıdadır:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Bunlar PDF oluşturma, metin düzenleme ve üstbilgi/altbilgi yönetimi için olmazsa olmazdır.

Örnek kodu anlaşılması kolay adımlara bölelim.

## Adım 1: Belgeyi ve Sayfayı Ayarlayın

İlk olarak, belgeyi başlatmamız ve ona bir sayfa eklememiz gerekir. Bu, başlıklar ve altbilgiler eklemek için temel oluşturur.

```csharp
// Belge dizinini ayarla
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge nesnesini başlat
Document doc = new Document();

// Belgeye bir sayfa ekle
Page page = doc.Pages.Add();
```

 Burada, PDF belgesini kullanarak bir PDF belgesi oluşturuyoruz`Document` sınıf ve bir sayfa ekleme`doc.Pages.Add()`Bu sayfa üstbilgi, altbilgi ve diğer içerikleri barındıracaktır.

## Adım 2: Sayfa Kenar Boşluklarını Yapılandırın

Daha sonra, içeriğimizin kenara kadar ulaşmamasını sağlamak için sayfa için kenar boşlukları tanımlayacağız.

```csharp
// Kenar boşluklarını yapılandırın
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 Burada, üst, alt, sol ve sağ kenar boşluklarını kullanarak tanımladık`MarginInfo` sınıfını kullanarak sayfaya uyguladım`page.PageInfo.Margin`.

## Adım 3: Başlığı Oluşturun ve Yapılandırın

Şimdi bir başlık oluşturalım ve sayfaya ekleyelim. Başlık rapor başlığını ve adını içerecektir.

```csharp
// Başlık oluştur
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// Başlık kenar boşluklarını ayarlayın
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// Başlığa başlık ekle
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// Rapor adını başlığa ekle
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 İki tane ekledik`TextFragment` başlığa nesneler: biri rapor başlığı için ve diğeri rapor adı için. Metin, kullanılarak biçimlendirilir`TextState` yazı tipi, boyutu ve hizalama gibi özellikler.

## Adım 4: Altbilgiyi Oluşturun ve Yapılandırın

Şimdi sayfa numaraları ve oluşturulma tarihi gibi dinamik içerikleri tutacak olan altbilgiyi ayarlamanın zamanı geldi.

```csharp
// Altbilgi oluştur
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// Altbilgi kenar boşluklarını ayarlayın
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// Altbilgi içeriği ekle
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

Altbilgide, oluşturma tarihi, rapor adı ve dinamik sayfa numaraları için parçalar ekliyoruz (`$p` Ve`$P` (sırasıyla geçerli sayfa numarasını ve toplam sayfa sayısını temsil eder).

## Adım 5: Altbilgide Bir Tablo Oluşturun

Ayrıca verilerinizi daha iyi organize etmek için alt bilgiye tablolar gibi daha karmaşık öğeler de ekleyebilirsiniz.

```csharp
// Altbilgi için tablo oluştur
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// Tablo için satırlar ve hücreler oluşturun
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// Her hücre için hizalamayı ayarlayın
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// Tablo hücrelerine içerik ekle
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

Bu kod bloğu, alt bilgide her sütununda oluşturma tarihi, rapor adı ve sayfa numaraları gibi farklı bilgi parçalarının bulunduğu 3 sütunlu bir tablo oluşturur.

## Adım 6: Sayfaya İçerik Ekleyin

Başlıklar ve altbilgilere ek olarak, PDF sayfasının gövdesine içerik ekleyebilirsiniz. Burada, bazı yer tutucu metinler içeren bir tablo ekliyoruz.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// Tablo içeriği ekle
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

Bu kod sayfaya üç sütunlu basit bir tablo ekler. Bunu özel ihtiyaçlarınıza uyacak şekilde değiştirebilirsiniz.

## Adım 7: PDF'yi kaydedin

Her şey ayarlandıktan sonra son adım PDF belgesini istediğiniz yere kaydetmektir.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 Dosya yolunu belirtin ve belgeyi kullanarak kaydedin`doc.Save()`İşte bu kadar! Özelleştirilmiş üstbilgi ve altbilgilere sahip bir PDF'i başarıyla oluşturdunuz.

## Çözüm

Aspose.PDF for .NET kullanarak başlık ve altbilgilerdeki sembolleri değiştirmek yalnızca basit değil aynı zamanda güçlüdür. Yukarıdaki adım adım kılavuzu izleyerek PDF'lerinizi sayfa numaraları, rapor adları ve tarihler gibi dinamik içeriklerle kolayca özelleştirebilirsiniz. Bu yöntem oldukça esnektir ve tablolar eklemenize, biçimlendirmeyi ayarlamanıza ve düzeni belirli gereksinimlerinize uyacak şekilde kontrol etmenize olanak tanır.

## SSS

### Üstbilgi ve altbilgi için yazı tiplerini özelleştirebilir miyim?  
Evet, üstbilgi ve altbilgilerdeki metinlerin yazı tiplerini, boyutlarını, renklerini ve stillerini tamamen özelleştirebilirsiniz.

### Başlık ve altbilgilere nasıl resim eklerim?  
 Kullanabilirsiniz`ImageStamp` Başlık ve altbilgilerinize resim eklemek için.

### Başlıklara veya altbilgilere köprü eklemek mümkün müdür?  
 Evet, kullanabilirsiniz`TextFragment` bir köprü metni ile ayarlayarak`Hyperlink` mülk.

### Tek ve çift sayfalar için farklı başlıklar kullanabilir miyim?  
Evet, Aspose.PDF tek ve çift sayfalar için farklı üstbilgi ve altbilgi belirtmenize olanak tanır.

### Üstbilgi ve altbilgi konumlarını nasıl ayarlarım?  
Üstbilgilerinizin ve altbilgilerinizin konumunu kontrol etmek için kenar boşluklarını ve hizalama özelliklerini ayarlayabilirsiniz.