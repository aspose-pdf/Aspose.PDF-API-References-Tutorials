---
title: Stil Tablo Satırı
linktitle: Stil Tablo Satırı
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF'yi kullanarak PDF'deki tablo satırlarını nasıl biçimlendireceğinizi adım adım anlatan bir kılavuzla öğrenin ve belge biçimlendirmenizi kolaylıkla geliştirin.
type: docs
weight: 180
url: /tr/net/programming-with-tagged-pdf/style-table-row/
---
## giriiş

İyi yapılandırılmış ve güzel biçimlendirilmiş PDF belgeleri oluşturmaya gelince, Aspose.PDF for .NET başvurulacak bir çözümdür. Raporları, faturaları otomatikleştiriyor veya dinamik tablolar oluşturuyor olun, tabloları çeşitli stillerle biçimlendirmek cilalı bir belgenin anahtarıdır. Bu eğitimde, Aspose.PDF for .NET kullanarak bir tablo satırını biçimlendirmeye derinlemesine dalacağız. Ve endişelenmeyin, tıpkı kahve içerken güzel bir sohbet gibi, adım adım size rehberlik edeceğim!

## Ön koşullar

Ayrıntılara girmeden önce, tüm işlerinizi yoluna koyduğunuzdan emin olalım. İhtiyacınız olacaklar:

1. .NET Kütüphanesi için Aspose.PDF  
    Eğer henüz sahip değilseniz, şuradan alabilirsiniz:[Burada](https://releases.aspose.com/pdf/net/) Ayrıca bir tane de alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) Başlamak için.
2. Geliştirme Ortamı  
   Visual Studio'yu veya istediğiniz herhangi bir C# IDE'yi kurun. Ayrıca .NET'in de yüklü olması gerekir, ancak buna zaten aşina olduğunuzu tahmin ediyorum.
3. C# ve .NET'in Temel Bilgileri  
   C#'ı iyi anlamak bu eğitimi çocuk oyuncağı yapacaktır. Ama endişelenmeyin, her adımı detaylı bir şekilde açıklayacağım!

## Paketleri İçe Aktar

Aspose.PDF ile çalışmaya başlamadan önce gerekli ad alanlarını içe aktarmamız gerekir. C# projenizde aşağıdakileri eklediğinizden emin olun:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bunlar tabloyu oluşturmak ve biçimlendirmek için ve tabii ki etiketli içerikle uyumluluk için çalışmak için gereklidir.

Şimdi görevi adım adım parçalara ayıralım, böylece tablo satırlarınızı bir profesyonel gibi biçimlendirebilirsiniz!

## Adım 1: Yeni bir PDF Belgesi Oluşturun

İlk önce ilk şeyler: yepyeni bir PDF belgesi oluşturalım. Bu belge tüm biçimlendirilmiş tablo satırlarını tutacak.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belge oluştur
Document document = new Document();
```

 Burada, yalnızca yeni bir tane başlatıyoruz`Document` PDF dosyamızı temsil edecek nesne. Çıktı dosyalarınızı kaydedeceğiniz dizin yolunu ayarladığınızdan emin olun.

## Adım 2: Etiketli İçerikle Çalışın

PDF'nizi erişilebilirlik için yapılandırmak için etiketli içerikle çalışacağız. Bu, tablolar gibi yapılandırılmış öğeler oluşturmaya yardımcı olur ve bunların PDF/UA gibi erişilebilirlik standartlarıyla uyumlu olmasını sağlar.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Burada, PDF'in etiketli içeriği için başlığı ve dili ayarlıyoruz. Bu, PDF'nize bir isim verip hangi dili konuşması gerektiğini söylemek gibidir!

## Adım 3: Tablo Yapısını Tanımlayın

Şimdi, oluşturmak üzere olduğumuz tablonun yapısını tanımlayalım. Her tablonun bir başlığa, gövdeye ve alt bilgiye ihtiyacı vardır - tıpkı iyi düzenlenmiş bir blog yazısı gibi!

```csharp
// Kök yapı elemanını al
StructureElement rootElement = taggedContent.RootElement;

// Tablo yapı öğesini oluştur
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Burada yaptığımız şey, bir başlık ( ile bir tablo oluşturmaktır`THead`), vücut (`TBody`), ve altbilgi (`TFoot`). Bu elemanlar satırlarımızı tutacak.

## Adım 4: Tablo Başlığı Satırını Ekleyin

Başlıksız tablolar, başlıksız kitaplar gibidir. Verilere bağlam sağlamak için önce başlık satırını oluşturalım.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Burada, döngüye girip üç başlık hücresi ekliyoruz (`TableTHElement`), her birine açıklayıcı bir metin vererek. Basit, değil mi?

## Adım 5: Şekillendirilmiş Gövde Sıraları Ekleyin

Şimdi eğlenceli kısma geliyoruz – satırları biçimlendirme! Özel stiller ile yedi satır oluşturalım. Arka plan renklerini, kenarlıkları, dolguyu ve metin hizalamasını ayarlayacağız.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Arka Plan Rengi: Profesyonel ama sıcak bir dokunuş için açık altın sarısı kullandık.
- Kenarlıklar: Her satıra keskin bir görünüm için koyu gri dış kenarlık ve mavi hücre kenarlıkları uygulanır.
- Yükseklik ve Dolgu: Satır yükseklikleri ayarlanır ve temiz bir görünüm için dolgu eklenir.
- Sayfa Sonları: Tabloyu daha okunabilir hale getirmek için her ikinci satır yeni bir sayfada başlar.

## Adım 6: Altbilgi Satırını Ekleyin

Başlık gibi, alt bilgi de tabloyu sabitler. Hadi bir tane oluşturalım.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Sadece üç altbilgi hücresinde dolaşıp biraz metin ekliyoruz. Altbilgi için alternatif metin, erişilebilir hale getirmek için "Ayak Satırı"dır.

## Adım 7: PDF Belgesini Kaydedin

Artık masa hazır olduğuna göre, şaheserinizi kurtarmanın zamanı geldi!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

İşte böyle, PDF'niz az önce biçimlendirdiğimiz tüm güzel tablo satırlarıyla birlikte kaydedildi.

## Adım 8: PDF/UA Uyumluluğunu Doğrulayın

PDF'imizin erişilebilirlik standartlarına uygun olduğundan emin olmak için PDF/UA uyumluluğunu doğrulayacağız.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Bu, PDF'nizin PDF/UA standardını karşılamasını ve herkes tarafından erişilebilir olmasını sağlar. Erişilebilirlik oyunun adıdır!

## Çözüm

İşte karşınızda! Sadece birkaç satır kodla, .NET için Aspose.PDF kullanarak PDF'de tamamen biçimlendirilmiş bir tablo oluşturdunuz. Başlıklardan altbilgilere kadar her satırı biçimlendirdik, erişilebilirlik öğeleri ekledik ve hatta belgeyi uyumluluk açısından doğruladık. İster kurumsal raporlar, sunumlar üzerinde çalışıyor olun, ister sadece PDF'lerle eğleniyor olun, bu kılavuz sizi kapsıyor. Şimdi devam edin ve tablolarınızı bir profesyonel gibi biçimlendirmeye başlayın!

## SSS

### Tablonun yazı tipini de değiştirebilir miyim?  
 Evet! Yazı tipi stilini şu şekilde değiştirebilirsiniz:`TextState` Her hücre için nesne, tam özelleştirmeye olanak tanır.

### Tabloma nasıl daha fazla sütun eklerim?  
 Sadece ayarlayın`colCount`değişkenini ayarlayın ve döngülere başlıklar, gövde ve altbilgiler için daha fazla hücre ekleyin.

### Satır yüksekliğini ayarlamazsam ne olur?  
Satır yüksekliğini ayarlamazsanız tablo içeriğe göre otomatik olarak ayarlanır.

### Bunu dinamik satır sayısı için kullanabilir miyim?  
Kesinlikle! Bir veritabanından veya başka bir kaynaktan veri alabilir ve satır ve sütun sayılarını dinamik olarak ayarlayabilirsiniz.

### Aspose.PDF for .NET'i kullanmak ücretsiz mi?  
 Aspose.PDF for .NET lisanslı bir üründür, ancak bunu bir[ücretsiz deneme](https://releases.aspose.com/) veya bir tane al[geçici lisans](https://purchase.aspose.com/temporary-license/).