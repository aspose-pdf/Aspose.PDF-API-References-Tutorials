---
title: Stil Tablo Elemanı
linktitle: Stil Tablo Elemanı
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te adım adım talimatlar, özel stil ve PDF/UA uyumluluğu ile bir tablo öğesinin nasıl oluşturulacağını ve biçimlendirileceğini öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-tagged-pdf/style-table-element/
---
## giriiş

Bu makalede, .NET için Aspose.PDF kullanarak bir tablo öğesinin nasıl oluşturulacağını ve biçimlendirileceğini inceleyeceğiz. Bir tablonun nasıl yapılandırılacağını, özel stiller nasıl uygulanacağını ve belgenizin PDF/UA uyumluluğunun nasıl doğrulanacağını öğreneceksiniz. Bu eğitimin sonunda, PDF'lerinizde kolayca profesyonel görünümlü tablolar oluşturabileceksiniz!

## Ön koşullar

Eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olmanız gerekir:

1. Bilgisayarınızda Visual Studio veya benzeri bir IDE yüklü olmalıdır.
2. Uygulamayı çalıştırmak için .NET Framework veya .NET Core SDK.
3.  Aspose.PDF for .NET kütüphanesi indirildi ve projenizde referans alındı. En son sürümü şuradan alabilirsiniz:[Burada](https://releases.aspose.com/pdf/net/).
4.  Geçerli bir Aspose lisansı veya[geçici lisans](https://purchase.aspose.com/temporary-license/) Kütüphanenin tüm işlevlerini açmak için.

## Paketleri İçe Aktar

Başlamak için gerekli ad alanlarını projenize aktarın:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu ad alanları temel PDF işlemlerini, etiketli içeriği, tabloları ve metin biçimlendirmesini kapsar.

Şimdi Aspose.PDF'de bir tablo oluşturma ve biçimlendirme sürecini parçalara ayıralım. Her bölümü ayrıntılı olarak ele alacağız, böylece takip edebilirsiniz.

## Adım 1: Yeni bir PDF Belgesi Oluşturun ve Etiketli İçeriği Ayarlayın

Bu ilk adımda boş bir PDF belgesi oluşturacağız ve etiketli içeriğini ayarlayacağız.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir PDF belgesi oluşturun
Document document = new Document();

// Etiketli içerik kurulumu
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Yeni bir şey yaratarak başlıyoruz`Document` nesne, PDF'imizi temsil ediyor.`TaggedContent`nesnesi, erişilebilirlik standartlarına uyumu sağlayarak belgenin yapısını yönetmek için kullanılır. Uygun etiketleme için belgenin başlığını ve dilini ayarlıyoruz.

## Adım 2: Kök Elemanı Tanımlayın

Daha sonra, PDF'mizdeki tüm içerik için bir kapsayıcı görevi gören kök yapı öğesini oluşturacağız.

```csharp
// Kök yapı öğesini alın
StructureElement rootElement = taggedContent.RootElement;
```

 The`RootElement` tablomuz dahil tüm yapılandırılmış öğeler için temel kapsayıcı görevi görür. Hem organizasyon hem de erişilebilirlik açısından önemli olan belgenin yapısal hiyerarşisini korumaya yardımcı olur.

## Adım 3: Tablo Elemanını Oluşturun ve Stilini Ayarlayın

 Artık kök öğe ayarlandığına göre, bir tane oluşturacağız`TableElement` ve arka plan rengi, kenarlıklar ve hizalama gibi stiller uygulayın.

```csharp
// Tablo yapı öğesini oluştur
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Masayı şekillendir
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Biz bir tane yaratıyoruz`TableElement` , tablo yapımızı tanımlayan`BackgroundColor`, `Border` , Ve`Alignment` özellikleri, tablonun görünümünü özelleştirmemize olanak tanır.`Broken` özellik, tablo sayfalar arasında bölünürse dikey olarak bölünmesini sağlar.

## Adım 4: Tablo Boyutlarını ve Hücre Stillerini Ayarlayın

Bu adımda sütun sayısını, hücre dolgusunu ve diğer önemli tablo özelliklerini tanımlayacağız.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Tablodaki her sütunun eşit aralıklı olmasını sağlamak için sütun genişliklerini belirtiyoruz.`DefaultCellBorder`, `DefaultCellPadding` , Ve`DefaultCellTextState` Hücreler için kenarlıklar, dolgu, metin rengi ve yazı tipi boyutu dahil olmak üzere varsayılan stilleri tanımlayın.

## Adım 5: Tekrarlayan Satırları ve Özel Stilleri Ekleyin

Ayrıca tekrarlayan satırlar ve başlıklar ve altbilgiler gibi diğer belirli tablo öğeleri için de stiller tanımlayabiliriz.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 The`RepeatingRowsCount` tablo birden fazla sayfaya yayılıyorsa ilk üç satırın tekrarlanmasını sağlar.`RepeatingRowsStyle` Bu satırlara özel bir arka plan rengi uygulamak için.

## Adım 6: Masa Başlığı, Gövdesi ve Ayak Elemanlarını Ekleyin

Şimdi tablo başlığı, gövde ve alt bilgi bölümlerini oluşturalım ve bunları içerikle dolduralım.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Başlık satırı oluştur
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Tablo gövdesini doldur
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Tablo üç bölüme ayrılmıştır: baş, gövde ve ayak. İlk olarak başlık satırını kullanarak oluşturuyoruz`TableTHElement`ve sütun başlıkları ekleyin. Ardından, tablonun gövdesini şu şekilde doldururuz:`TableTDElement`, her hücreyi konumunu içeren bir etiketle doldurur.

## Adım 7: Belgeyi Kaydedin

Son olarak PDF dokümanını belirtilen dizine kaydediyoruz.

```csharp
// Etiketli PDF belgesini kaydedin
document.Save(dataDir + "StyleTableElement.pdf");
```

Bu adım, biçimlendirilmiş tabloyla birlikte PDF dosyasını kaydederek belge oluşturma sürecini sonlandırır.

## Adım 8: PDF/UA Uyumluluğunu Doğrulayın

Belgeyi kaydettikten sonra PDF/UA (Evrensel Erişilebilirlik) standartlarına uygunluğundan emin olmak önemlidir.

```csharp
// PDF/UA uyumluluğunu kontrol edin
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Burada, belgeyi yeniden yükler ve PDF/UA standartlarına göre doğrularız. Uyumluluk, PDF'nizin erişilebilirlik gereksinimlerini karşılamasını ve onu çok çeşitli kullanıcılar için uygun hale getirmesini sağlar.

## Çözüm

Aspose.PDF for .NET ile PDF belgelerinizde tablolar oluşturmak ve biçimlendirmek basit ve sezgiseldir. Bu eğitimde özetlenen adımları izleyerek, özelleştirilmiş stillere sahip tablolar oluşturabilir ve PDF'lerinizin erişilebilirlik standartlarını karşıladığından emin olabilirsiniz. İster raporlar üretiyor ister yapılandırılmış belgeler oluşturuyor olun, tablolar verileri açık bir şekilde sunmak için güçlü bir araçtır.

## SSS

### Tablo hücrelerinin içine resim ekleyebilir miyim?
 Evet, tablo hücrelerine resim ekleyebilirsiniz.`Image` öğe.

### Sütun genişliklerini dinamik olarak nasıl ayarlarım?
 Ayarlayabilirsiniz`ColumnAdjustment` mülk`AutoFitToWindow` İçeriğe göre sütun genişliklerini otomatik olarak ayarlamak için.

### Tüm belgeler için PDF/UA uyumluluğu zorunlu mudur?
Zorunlu olmamakla birlikte, yüksek erişilebilirlik standartları gerektiren belgeler için önerilir.

### Belirli satırlara farklı stiller uygulayabilir miyim?
 Evet, tek tek satırları veya hücreleri, bunların özelliklerini ayarlayarak özelleştirebilirsiniz.`TextState` veya`BackgroundColor`.

### Etiketli içerik kullanmanın faydası nedir?
Etiketli içerik, belge erişilebilirliğini iyileştirir ve PDF/UA gibi standartlara uyumluluğun sağlanmasına yardımcı olur.