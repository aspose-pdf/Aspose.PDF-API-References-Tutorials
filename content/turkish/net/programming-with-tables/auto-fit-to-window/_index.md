---
title: Pencereye Otomatik Uyum
linktitle: Pencereye Otomatik Uyum
second_title: Aspose.PDF for .NET API Referansı
description: Bu ayrıntılı, adım adım kılavuzda .NET için Aspose.PDF'yi kullanarak bir tablonun pencereye otomatik olarak nasıl sığdırılacağını öğrenin. PDF'lerde cilalı ve iyi sığdırılmış tablolar oluşturmak için mükemmeldir.
type: docs
weight: 50
url: /tr/net/programming-with-tables/auto-fit-to-window/
---
## giriiş

PDF'lerle çalışırken tablolarla uğraşmak yaygındır ve bu tabloların bir sayfanın genişliğine mükemmel şekilde uyması gereken zamanlar vardır. Bu eğitimde, .NET için Aspose.PDF kullanarak bir tablonun bir pencereye otomatik olarak nasıl sığdırılacağını inceleyeceğiz. Bu, tablolarınızın cilalı ve düzenli görünmesini sağlayarak taşma veya düzensiz sütunlar gibi sorunları önleyebilir. Öğrenmeye hazır mısınız? Hadi başlayalım!

## Ön koşullar

Adım adım kılavuza geçmeden önce ihtiyacınız olacak birkaç şey var:

1. Projenizde .NET için Aspose.PDF yüklü. Eğer henüz yoksa,[buradan indirin](https://releases.aspose.com/pdf/net/) veya keşfetmek[ücretsiz deneme sürümü](https://releases.aspose.com/).
2. .NET programlamanın temelleri hakkında bilgi.
3. Sisteminizde Visual Studio veya .NET destekli herhangi bir IDE yüklü olmalıdır.

>  PS Aspose.PDF'yi sınırlama olmaksızın kullanmak için bir lisansa ihtiyacınız olacağını unutmayın. Bir tane satın alabilirsiniz[Burada](https://purchase.aspose.com/buy) veya bir tane al[geçici lisans](https://purchase.aspose.com/temporary-license/) Tüm özelliklerini denemek için.

## Paketleri İçe Aktar

Koda dalmadan önce gerekli ad alanlarını içe aktarmanız gerekir:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Artık her şey tamam olduğuna göre, Aspose.PDF for .NET kullanarak bir tabloyu pencereye otomatik olarak nasıl sığdırabileceğinizi anlamak için bunu basit ve anlaşılır adımlara bölelim.

## Adım 1: Belge Nesnesini Başlatın

Öncelikle bir PDF belgesi oluşturmanız gerekir. Bu belgeyi, sayfalar ve tablolar ekleyeceğiniz boş bir sayfa olarak düşünün.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Boş oluşturucusunu çağırarak Pdf nesnesini örneklendirin
Document doc = new Document();
```
  
 Burada, şunu kullanarak yeni bir belge oluşturuyoruz:`Document` Aspose.PDF'den sınıf.`dataDir` işiniz bittikten sonra PDF'nizin kaydedileceği konumdur.

## Adım 2: Belgeye Bir Sayfa Ekleyin

Bir PDF belgesinin sayfalara ihtiyacı var, değil mi? Hadi bir tane ekleyelim.

```csharp
// Pdf nesnesinde bir bölüm (sayfa) oluşturun
Page sec1 = doc.Pages.Add();
```
  
 Belgeye yeni bir sayfa ekledik`Pages.Add()` yöntem. Bunu, tabloyu yerleştireceğiniz belgenize yeni bir sayfa eklemek olarak düşünebilirsiniz.

## Adım 3: Bir Tablo Oluşturun ve Yapılandırın

Şimdi bir tablo oluşturup pencerenin içine sığacak şekilde ayarlamanın zamanı geldi.

```csharp
// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
sec1.Paragraphs.Add(tab1);
```
  
 Yeni bir tane başlattık`Table` nesneyi ekledi ve sayfanın paragraf koleksiyonuna ekledi. Her PDF sayfası farklı paragraflara sahip olabilir ve burada tabloyu bir paragraf olarak ele alıyoruz.

## Adım 4: Sütun Genişliklerini Tanımlayın ve Pencereye Otomatik Olarak Sığdırın

Daha sonra sütun genişliklerini ayarlayıp tablonun pencereye uyacak şekilde kendini ayarlamasını sağlıyoruz.

```csharp
// Tablo için sütun genişliklerini ayarlayın
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 Tablo için sabit sütun genişlikleri belirledik ancak ayrıca şunları da ekledik:`ColumnAdjustment.AutoFitToWindow`, tablonun mevcut pencereye uyacak şekilde boyutunu ayarlamasını sağlar.

## Adım 5: Tablo ve Hücreler için Kenarlıkları ve Kenar Boşluklarını Ayarlayın

Kenarlıkları olmayan tablolar genellikle okunaksızdır. Düzenli görünmesi için kenarlıklar ve kenar boşlukları tanımlayalım.

```csharp
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Başka bir özelleştirilmiş BorderInfo nesnesini kullanarak tablo kenarlığını ayarlayın
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

// MarginInfo nesnesini oluşturun ve sol, alt, sağ ve üst kenar boşluklarını ayarlayın
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Varsayılan hücre dolgusunu MarginInfo nesnesine ayarlayın
tab1.DefaultCellPadding = margin;
```
  
 Tabloya ve hücrelere kenarlıklar, şunu kullanarak eklenir:`BorderInfo` kalınlığı tanımladığınız sınıf. Kenar boşlukları hücrelere biraz dolgu alanı sağlamak için ayarlanır.

## Adım 6: Tabloya Satır ve Hücreler Ekleyin

İçeriği olmayan bir tablo? Bu iyi değil! Hadi birkaç satır ve hücre ekleyelim.

```csharp
//Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
İki satır oluşturuyoruz ve her satıra üç hücre ekliyoruz. Gerçek verilerinizi (dizelerden daha karmaşık öğelere kadar her şey olabilir) buraya gireceksiniz.

## Adım 7: Belgeyi Kaydedin

Her şey ayarlandıktan sonra yeni oluşturduğunuz PDF belgenizi kaydetmek isteyeceksiniz.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Tablo nesnesini içeren güncellenmiş belgeyi kaydet
doc.Save(dataDir);
```
  
 The`doc.Save()` yöntem PDF'yi belirtilen dizine kaydeder. Bu durumda, belge şu şekilde kaydedilir:`AutoFitToWindow_out.pdf` tanımladığınız dizinde.

## Çözüm

İşte oldu! Aspose.PDF for .NET kullanarak pencereye otomatik olarak uyan bir tablo oluşturdunuz. Bu, tablonuzun yalnızca profesyonel ve iyi yerleştirilmiş görünmesini sağlamakla kalmaz, aynı zamanda farklı veri boyutlarıyla çalışırken size esneklik de sağlar. İster raporlar, ister faturalar veya tablo gerektiren herhangi bir belge oluşturuyor olun, bu yöntem temiz ve okunabilir düzenleri korumak için harika bir yoldur.

## SSS

### Dinamik olarak daha fazla satır ekleyebilir miyim?  
 Evet, satır eklemeye devam edebilirsiniz`tab1.Rows.Add()` içeriğe göre dinamik olarak uygulanan bir yöntemdir.

### Tablonun otomatik olarak sığmasını istemiyorsam nasıl ayarlarım?  
 Manuel olarak ayarlayabilirsiniz`ColumnWidths` kullanmadan`ColumnAdjustment.AutoFitToWindow` sabit bir masa genişliğini korumak için.

### Hücrelerin içine resim veya başka içerikler ekleyebilir miyim?  
Evet, Aspose.PDF hücrelerin içine resim, metin ve hatta diğer tabloları eklemenize olanak tanır!

### Daha karmaşık tablo stillerine ihtiyacım olursa ne olur?  
Arka plan rengi, metin hizalaması ve yazı tipi ayarları gibi özellikleri kullanarak tablo ve hücre stillerini daha da özelleştirebilirsiniz.

### Bu tabloyu PDF dışındaki formatlara aktarmak mümkün müdür?  
Kesinlikle! Aspose.PDF, HTML, DOCX ve daha fazlası gibi çeşitli formatlara aktarımı destekler.