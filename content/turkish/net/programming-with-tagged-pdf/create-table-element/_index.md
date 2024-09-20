---
title: Tablo Elemanı Oluştur
linktitle: Tablo Elemanı Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF ile dizi öğesi oluşturmaya yönelik adım adım kılavuz. Tablolar içeren dinamik PDF'leri kolayca oluşturun.
type: docs
weight: 80
url: /tr/net/programming-with-tagged-pdf/create-table-element/
---
## giriiş

.NET kullanarak bir PDF'de tablo öğelerini zahmetsizce nasıl oluşturabileceğinizi ve özelleştirebileceğinizi hiç merak ettiniz mi? Aspose.PDF for .NET sizin için ideal çözüm! İster rapor oluşturmayı otomatikleştirin ister çeşitli belgeler için tabloları dinamik olarak oluşturun, Aspose.PDF tablo öğeleriyle çalışmak için zengin bir API sunar. Bu kılavuz, bir tablonun nasıl oluşturulacağı, nasıl biçimlendirileceği ve hatta PDF/UA uyumluluk standartlarını nasıl karşılayacağı konusunda adım adım yol gösterecektir. Heyecan verici geliyor, değil mi? Hemen başlayalım!

## Ön koşullar

Başlamadan önce birkaç şeyin hazır olması gerekir:
1.  Aspose.PDF for .NET: En son sürümü şu adresten indirin:[Aspose.PDF for .NET İndir](https://releases.aspose.com/pdf/net/).
2. Geliştirme Ortamı: Herhangi bir .NET destekli IDE (örneğin, Visual Studio).
3. Temel C# Bilgisi: C# programlamaya aşinalık tavsiye edilir.

 Son olarak, Aspose.PDF lisansınızı unutmayın. Eğer yoksa, şunu kullanabilirsiniz:[ücretsiz deneme](https://releases.aspose.com/) veya bir talepte bulunun[geçici lisans](https://purchase.aspose.com/temporary-license/) her şeyi denemek için.

## Paketleri İçe Aktar

İlk önce ilk şeyler—gerekli paketleri içe aktaralım. Bu, PDF belgelerinde tablolar oluşturmak için ilgili tüm sınıflarla çalışmamızı sağlayacaktır.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu bölümde, bir tablo oluşturma sürecini birden fazla adıma ayıracağız. Her adım, tablo oluşturma ve özelleştirme sürecinin farklı bölümlerine odaklanır.

## Adım 1: Yeni bir PDF Belgesi Oluşturun

Yapmamız gereken ilk şey yeni bir PDF belgesi oluşturmaktır. Bu, tablomuz için kapsayıcı görevi görecektir.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir PDF belgesi oluşturun
Document document = new Document();
```

 Burada, yeni bir örneğini başlatıyoruz`Document` sınıfımız, boş PDF dosyamız olacak. Dosya yolunuzu tanımlamayı unutmayın!

## Adım 2: Etiketli İçeriği Ayarlayın

Sonra, tablonun erişilebilirliğini garanti altına alan etiketli içeriği etkinleştirmemiz gerekir. Etiketli PDF'ler, PDF/UA (Evrensel Erişilebilirlik) ile uyumluluk için gereklidir.

```csharp
// Etiketli içeriği etkinleştir
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

Bu adım, tablonun erişilebilirlik standartlarına uymasını sağlayarak belge başlığını ve dilini belirler. Erişilebilir belgelere sahip olmak, bazı sektörlerde kullanıcı deneyimi ve yasal gereklilikler açısından çok önemlidir.

## Adım 3: Tablo Öğesini Oluşturun

Şimdi en eğlenceli kısma geldik: Masayı hazırlamak!

```csharp
// Kök yapı öğesini alın
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 Burada şunu kullanıyoruz:`RootElement` Tablomuza eklemek için etiketli içeriğin. Bu, esasen bir tabloyu belgenin yapısına bir alt düğüm olarak eklemektir.

## Adım 4: Tablo Kenarlıklarını ve Başlıklarını Özelleştirin

Masanızın sıradan görünmesini istemezsiniz, değil mi? Biraz stil katalım!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 Sınırları tanımlıyoruz ve tabloya başlıklar, gövde ve altbilgiler ekliyoruz. Kullanımını fark edin`BorderInfo` Masa kenarlarını koyu mavi renkle şekillendirmek.

## Adım 5: Tabloya Satır ve Hücreler Ekleyin

Şimdi tablomuzu satırlar ve hücrelerle dolduralım. İşlemin bu kısmı tablomuzun düzenini tanımladığımız yerdir.

### Adım 5.1: Başlık Satırı Oluşturun

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 4 sütunlu bir başlık satırı oluşturuyoruz ve her başlık hücresinin arka plan rengi şu şekilde olacak:`GreenYellow`Ayrıca başlıklar için bir kenarlık ve hizalama belirledik.

### Adım 5.2: Gövde Satırlarını Ekle

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

Burada, dinamik olarak 50 satır ve 4 sütun oluşturuyoruz, bunları metinle dolduruyoruz ve hücreleri biçimlendiriyoruz. Arka plan rengi sarıya ayarlandı ve metin ortalandı.

### Adım 5.3: Altbilgi Satırı Ekle

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 Tabloyu tamamlamak için, ortalanmış metin ve bir altbilgi ekliyoruz`LightSeaGreen` arka plan.

## Adım 6: PDF/UA Uyumluluğunu Doğrulayın

Tablo oluşturulduktan sonra PDF'in PDF/UA uyumlu olduğundan emin olmak çok önemlidir.

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA uyumluluğunu doğrulayın
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Bu kod parçası PDF dosyasını kaydeder ve PDF/UA uyumluluk standartlarını karşılayıp karşılamadığını kontrol eder. Belge uyumluysa, engelli kullanıcılar tarafından erişilebilir.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF'de tamamen özelleştirilmiş bir tabloyu başarıyla oluşturdunuz. Tabloyu biçimlendirmekten PDF/UA uyumluluğunu sağlamaya kadar, artık PDF belgelerinizde dinamik tablolar oluşturmak için sağlam bir temele sahipsiniz. Belgelerinizi daha da geliştirmek için Aspose.PDF'nin kapsamlı özelliklerini keşfetmeyi unutmayın!

## SSS

### Tablonun yazı tipini ve metin stilini özelleştirebilir miyim?
Evet, Aspose.PDF, yazı tiplerini, metin stillerini ve hizalamayı tamamen özelleştirmenize olanak tanır.`TextState` sınıf.

### Dinamik olarak daha fazla sütun veya satır nasıl eklerim?
 Sütun veya satır sayısını değiştirerek ayarlayabilirsiniz.`rowIndex` Ve`colIndex` döngülerde.

### Tablodaki hücreleri birleştirmek mümkün müdür?
 Evet, kullanabilirsiniz`ColSpan` Ve`RowSpan` Sütunlar veya satırlar arasında hücreleri birleştirme özellikleri.

### PDF/UA uyumluluğu nedir?
PDF/UA uyumluluğu, belgenin uluslararası erişilebilirlik standartlarına uygun olarak engelli kullanıcılar tarafından da erişilebilir olmasını sağlar.

### Aspose.PDF'de PDF/UA uyumluluğunu nasıl test edebilirim?
 Kullanabilirsiniz`Validate` Belgenin PDF/UA standartlarına uygun olup olmadığını kontrol etme yöntemi.