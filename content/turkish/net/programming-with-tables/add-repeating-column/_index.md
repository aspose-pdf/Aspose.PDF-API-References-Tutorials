---
title: PDF Belgesine Tekrarlayan Sütun Ekle
linktitle: PDF Belgesine Tekrarlayan Sütun Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgelerine tekrarlayan sütunların nasıl ekleneceğini öğrenin. Örnekler ve kod içeren adım adım kılavuz. Geliştiriciler için mükemmel.
type: docs
weight: 20
url: /tr/net/programming-with-tables/add-repeating-column/
---
## giriiş

PDF belgeleriyle çalışıyorsanız ve tekrarlayan sütunlar eklemeniz gerekiyorsa, doğru yerdesiniz! .NET için Aspose.PDF'yi kullanarak, bir PDF içindeki tabloları ve içerikleri kolayca yönetebilirsiniz. Dinamik raporlar, faturalar veya başka yapılandırılmış belgeler oluşturuyor olun, tekrarlayan sütunlar verileri düzenlemede oyunun kurallarını değiştirebilir. PDF belgesine tekrarlayan sütunların nasıl ekleneceği konusunda adım adım bir kılavuza dalalım.

## Ön koşullar

Koda geçmeden önce her şeyin ayarlandığından emin olalım:

- Aspose.PDF for .NET: Projenizde Aspose.PDF for .NET kütüphanesinin yüklü olması gerekir.
- [.NET için Aspose.PDF'yi indirin](https://releases.aspose.com/pdf/net/)
- [Ücretsiz Deneme](https://releases.aspose.com/)
- Geliştirme Ortamı: Visual Studio gibi .NET uyumlu bir IDE'nin yüklü olduğundan emin olun.
- C# Hakkında Temel Bilgi: Her şeyi parçalara ayıracağız ancak C# hakkında temel bir bilgiye sahip olmak, konuyu akıcı bir şekilde takip etmenize yardımcı olacaktır.
  
 Eğer .NET için Aspose.PDF'niz henüz yoksa, bir tane edinebilirsiniz[geçici lisans](https://purchase.aspose.com/temporary-license/) Özelliklerini keşfetmeye başlamak için.

## Paketleri İçe Aktar

Başlamak için, .NET için Aspose.PDF'den gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Bu paketler PDF belgeleriyle çalışmak ve tabloları düzenlemek için gereken temel sınıfları ve yöntemleri sağlar.

Şimdi, PDF belgesine tekrarlayan sütunlar eklemek için süreci birden fazla adıma bölelim. Takip edin!

## Adım 1: Belgeler Dizininize Giden Yolu Ayarlayın

Herhangi bir dosyayı oluşturmadan veya düzenlemeden önce, oluşturulan PDF'in kaydedileceği yolu tanımlamamız gerekir. C# projenizde, dosyalarınızın bulunacağı dizin yolunu ayarlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Bu yol, çıktı PDF'sinin kaydedileceği dizini gösterir. Değiştir`"YOUR DOCUMENT DIRECTORY"` makinenizdeki gerçek yol ile.

## Adım 2: Yeni bir PDF Belgesi Oluşturun

 Başlamak için yeni bir örnek oluşturun`Document` nesne. Bu, PDF içindeki tüm sayfalar ve içerikler için kapsayıcı görevi görecektir.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Burada yeni bir PDF belgesi oluşturduk ve buna boş bir sayfa ekledik.`doc.Pages.Add()` metodu belgeye yeni bir sayfa ekler.

## Adım 3: Dış Tabloyu Örneklendirin

Sonra, dış bir tablo oluşturuyoruz. Bu tablo sayfanın tüm genişliğini kaplayacak ve tekrarlayan sütunları içerecek olan tablo da dahil olmak üzere diğer tablolar için bir kapsayıcı görevi görecek.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Biz ayarladık`ColumnWidths` Özelliği "%100" olarak ayarlayın, bu da tablonun tüm sayfa genişliğine yayılacağı anlamına gelir.

## Adım 4: İç Tabloyu Oluşturun

 Şimdi, tekrarlayan sütunlara sahip olacak iç tabloyu oluşturalım. Buradaki temel özellikler şunlardır:`Broken` , tablonun aynı sayfada devam etmesini sağlar ve`ColumnAdjustment`İçeriğe uyacak şekilde sütun genişliklerini otomatik olarak ayarlayan.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Bu iç tablo dış tablonun içine yerleştirilecektir.

## Adım 5: Sayfaya Tablolar Ekleyin

Artık hem dış hem de iç tablolarımız hazır olduğuna göre, bunları sayfaya ekleyelim. Bu adım, tabloların belgenin yapısına dahil edilmesini sağlar.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Burada, şunu ekledik:`outerTable` sayfaya ve ardından dış tablonun içine yerleştirdik`mytable` Ek olarak, şunu belirledik:`RepeatingColumnsCount`5'e kadar, veri eklendiğinde kaç sütunun tekrarlanacağını belirtir.

## Adım 6: Başlık Satırı Ekle

Şimdi tabloya başlıkları ekleme zamanı. Başlık satırı verilere bağlam sağlar ve sütunların yapılandırılmasına yardımcı olur. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Bu kod parçacığı ilk satırı (bunu başlık olarak kullanacağız) ekler ve "başlık 1", "başlık 2" gibi metin içeren hücrelerle doldurur.

## Adım 7: Veri Satırları Ekleyin

Son olarak, tabloya biraz veri ekleyebiliriz. Bu döngü dinamik olarak satırlar oluşturur ve hücreleri içerikle doldurur:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

Döngü altı kez yinelenir, satırlar eklenir ve her hücre karşılık gelen sütun verileriyle doldurulur (örneğin, "sütun 1, 1", "sütun 2, 2", vb.).

## Adım 8: Belgeyi Kaydedin

Tüm satırlar ve sütunlar eklendikten sonra, son adım belgeyi belirtilen dosya yoluna kaydetmektir.

```csharp
doc.Save(outFile);
```

Belgeniz artık tekrarlayan sütunlarla kaydedildi!

## Çözüm

İşte bu kadar! Bu basit adımlarla, Aspose.PDF for .NET kullanarak tekrarlayan sütunlara sahip bir PDF belgesi oluşturabilirsiniz. İç içe geçmiş tabloların esnekliğinden yararlanarak, PDF'lerinizi profesyonel ve düzenli gösteren karmaşık düzenler elde edebilirsiniz. Bunu bir sonraki projeniz için deneyin ve PDF oluşturma ihtiyaçlarınızı karşılamak için Aspose.PDF'nin tüm potansiyelini keşfedin.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve yönetmelerine olanak tanıyan güçlü bir kütüphanedir.

### Tekrarlanan sütun sayısını dinamik olarak ayarlayabilir miyim?
 Evet, tekrar eden sütunların sayısını,`RepeatingColumnsCount` mülk.

### Aspose.PDF for .NET'e nasıl lisans uygulayabilirim?
 Aşağıdaki adımları izleyerek bir dosyadan veya akıştan lisans uygulayabilirsiniz:[belgeleme](https://reference.aspose.com/pdf/net/).

### Tablo hücrelerine resim eklemek mümkün mü?
Evet, Aspose.PDF for .NET, tablo hücrelerine resim dahil olmak üzere çeşitli içerik türlerinin eklenmesini destekler.

### Tablo düzenini daha fazla özelleştirebilir miyim?
Kesinlikle! Aspose.PDF, kenarlıklar, dolgu, hizalama ve daha fazlası dahil olmak üzere tablo stillerini özelleştirmek için kapsamlı özellikler sunar.