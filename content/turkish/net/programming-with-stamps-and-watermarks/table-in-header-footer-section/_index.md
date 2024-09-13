---
title: Üstbilgi Altbilgi Bölümündeki Tablo
linktitle: Üstbilgi Altbilgi Bölümündeki Tablo
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin üstbilgi/altbilgi bölümüne tablo eklemeyi öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
## giriiş

Hiç kendinizi düz bir PDF belgesine bakarken buldunuz mu, keşke o ekstra havası olsaydı? Şanslısınız! Aspose.PDF for .NET, PDF dosyalarını bir profesyonel gibi oluşturmanıza ve düzenlemenize olanak tanır. Bugün, PDF belgenizin başlığına bir tablo eklemenize olanak tanıyan kullanışlı bir özelliği ele alacağız. Bunu nasıl yapacağınızı öğrenmekle kalmayacak, aynı zamanda size adım adım rehberlik ederek tüm süreci tereyağı kadar kolay hale getireceğim. 🎉

## Ön koşullar

Gerçek kodlama kısmına geçmeden önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım. İşte ihtiyacınız olacaklar:

1.  Visual Studio: Bilgisayarınızda Visual Studio'nun yüklü olduğundan emin olun. Eğer yüklü değilse, şuradan indirebilirsiniz:[Microsoft'un sitesi](https://visualstudio.microsoft.com/).
2.  Aspose.PDF Kütüphanesi: .NET için Aspose.PDF kütüphanesine sahip olmalısınız. Aşağıdaki bağlantıyı kullanarak alabilirsiniz[.NET paketi için Aspose.PDF](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: En azından temel bir C# bilgisine sahip olmalısınız. Hala öğreniyorsanız endişelenmeyin; mümkün olduğunca basit tutacağım!

## Paketleri İçe Aktar

Tamam, kolları sıvayıp kodlamaya başlamanın zamanı geldi! Ama önce, gerekli paketleri içe aktararak ortamımızı kurmamız gerekiyor. İşte bunu nasıl yapacağınız:

###  Projenizi Açın
PDF oluşturma üzerinde çalışacağınız Visual Studio projenizi açın. 

###  Aspose.PDF'e Referans Ekle
1. NuGet Paket Yöneticisi: Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
2. Aspose.PDF'i arayın: Arama çubuğuna "Aspose.PDF" yazın ve paketi yükleyin.

Bu adımın sonunda her şey ayarlanmış ve kodlamaya başlamaya hazır olmalı!

Şimdi biraz kodla ellerimizi kirletelim! PDF'nizin başlık bölümünde bir tablo oluşturmak için şu adımları izleyin:

## Adım 1: Belge Dizininizin Yolunu Ayarlayın

PDF'imizi oluşturmaya başlamadan önce, belgemizin nerede saklanacağını tanımlamamız gerekir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Bunu gerçek dizininize değiştirin
```

 Yer değiştirmek`YOUR DOCUMENT DIRECTORY`PDF'nizi kaydetmek istediğiniz yol ile. Bu, sisteminizdeki herhangi bir yer olabilir—sadece erişilebilir olduğundan emin olun!

## Adım 2: Belgeyi Örneklendirin

Daha sonra yeni bir PDF belgesi oluşturacağız.

```csharp
// Boş oluşturucuyu çağırarak Belge örneğini örneklendirin
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();
```

Burada yaptığımız şey, tüm güzelliklerimizi ekleyeceğimiz boş bir PDF belgesi oluşturmak.

## Adım 3: Yeni Bir Sayfa Oluşturun

Dokümanımıza yeni bir sayfa ekleyelim. 

```csharp
// PDF belgesinde bir sayfa oluşturun
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Bu sayfayı, şaheserimizi çizeceğimiz boş bir tuval olarak düşünün!

## Adım 4: Bir Başlık Bölümü Oluşturun

Şimdi PDF'imiz için bir başlık oluşturacağız.

```csharp
// PDF dosyasının Başlık Bölümünü Oluşturun
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
```

Bu başlık masamızı taşıyacak. 

## Adım 5: Başlığı Sayfaya Ata

Daha sonra başlığımızın sayfada göründüğünden emin olmak istiyoruz.

```csharp
// PDF dosyası için Garip Başlığı Ayarla
page.Header = header;
```

## Adım 6: Üst Kenar Boşluğunu Ayarlayın

Başlığımızın üstte biraz nefes alabilmesi için kenar boşluklarını ayarlayalım.

```csharp
//Başlık bölümü için üst kenar boşluğunu ayarlayın
header.Margin.Top = 20;
```

Kenar boşluğu ayarlamak, metninize kişisel bir alan vermek gibidir; kimse sıkışıklıktan hoşlanmaz!

## Adım 7: Tabloyu Oluşturun

Şimdi başlığımıza girecek tabloyu oluşturmanın zamanı geldi.

```csharp
// Bir tablo nesnesi örneği oluşturun
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Adım 8: Tabloyu Başlığa Ekleyin

Yeni oluşturduğumuz tabloyu başlığın paragraf koleksiyonuna ekleyeceğiz.

```csharp
// İstenilen bölümün paragraf koleksiyonuna tabloyu ekleyin
header.Paragraphs.Add(tab1);
```

## Adım 9: Hücre Kenarlıklarını Ayarla

Varsayılan hücre kenarlığını tanımlayarak tablomuza biraz yapı kazandıralım.

```csharp
// BorderInfo nesnesini kullanarak varsayılan hücre kenarlığını ayarlayın
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Adım 10: Sütun Genişliklerini Tanımlayın

Tablonun her sütununun ne kadar geniş olacağını belirleyebilirsiniz.

```csharp
// Tablonun sütun genişlikleriyle ayarlayın
tab1.ColumnWidths = "60 300";
```

Değerler her sütunun genişliğini puan olarak temsil eder. İhtiyaçlarınıza uyacak şekilde ayarlamakta özgürsünüz!

## Adım 11: Satırları Oluşturun ve Hücreleri Ekleyin

Artık birkaç satır ve hücre eklemenin zamanı geldi! 

```csharp
//Tabloda satırlar ve ardından satırlarda hücreler oluşturun
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;
```

Bu, metin içeren bir hücrenin bulunduğu ilk satırı oluşturur ve arka plan rengini gri olarak ayarlar.

## Adım 12: Satır Genişliğini ve Metin Stilini Ayarlayın

Satırınızın birden fazla sütuna yayılmasını mı istiyorsunuz? İşte nasıl:

```csharp
// İlk satır için satır aralığı değerini 2 olarak ayarlayın
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

Bu adım yalnızca satır aralığını ayarlamakla kalmaz, aynı zamanda metin rengini ve yazı tipini de değiştirir.

## Adım 13: İkinci Bir Satır Ekleyin

Tablomuza bir satır daha ekleyelim mi?

```csharp
// Tabloda başka bir satır oluşturun
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Satır2 için arka plan rengini ayarlayın
row2.BackgroundColor = Color.White;
```

## Adım 14: İkinci Satıra Bir Resim Ekleyin

Şimdi masamızı şık gösterecek bir logo ekleyelim!

```csharp
// Resmi tutan hücreyi ekleyin
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg"; // Resmi dizininize yerleştirdiğinizden emin olun
```

 Değiştirmeyi unutmayın`"aspose-logo.jpg"` Resminizin gerçek adıyla!

## Adım 15: Görüntü Genişliğini Ayarlayın

Görüntünün hücrede tam olarak doğru görünmesini sağlamak için görüntü genişliğini ayarlayın.

```csharp
// Resim genişliğini 60'a ayarlayın
img.FixWidth = 60;

//Resmi tablo hücresine ekle
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
cell2.Paragraphs.Add(img);
```

## Adım 16: İkinci Hücreye Metin Ekleyin

Logomuzun yanına küçük bir metin eklemenin zamanı geldi!

```csharp
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

## Adım 17: Metni Dikey ve Yatay Olarak Hizalayın

Her şeyin düzenli göründüğünden emin olun. Metninizi hizalayın!

```csharp
// Metnin dikey hizalamasını ortaya hizalanmış olarak ayarlayın
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Adım 18: PDF Belgesini Kaydedin

Son olarak, eserimizi kurtaralım!

```csharp
// PDF dosyasını kaydedin
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

İşte karşınızda! Başlık bölümünde bir tablo bulunan muhteşem bir PDF oluşturdunuz!

## Çözüm

İşte oldu! Aspose.PDF for .NET kullanarak PDF belgenizin başlığına başarıyla bir tablo eklediniz. Sadece birkaç satır kodun basit bir PDF'yi profesyonel görünümlü bir belgeye nasıl dönüştürebildiği şaşırtıcı. İster raporlar, ister faturalar veya sunumlar hazırlıyor olun, biraz yaratıcılık katmak her şeyi değiştirebilir. 

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına ve düzenlemelerine olanak tanıyan güçlü bir kütüphanedir.

### Aspose.PDF'i kullanmak için lisansa ihtiyacım var mı?
 Deneme süresi boyunca kütüphaneyi ücretsiz kullanabilirsiniz ancak uzun süreli kullanım için lisans gereklidir. Bir lisans alabilirsiniz.[geçici lisans](https://purchase.aspose.com/temporary-license/) Değerlendirme için.

### Dokümantasyonu nerede bulabilirim?
Kapsamlı dokümantasyon ve örnekleri şu adreste bulabilirsiniz:[Aspose.PDF dokümantasyon sayfası](https://reference.aspose.com/pdf/net/).

### Teknik sorunlarda destek ekibiyle nasıl iletişime geçebilirim?
 Destek için bize ulaşabilirsiniz[Aspose forumu](https://forum.aspose.com/c/pdf/10).

### PDF'in diğer bölümlerinde tablo oluşturabilir miyim?
Kesinlikle! Altbilgilerde ve gövde bölümlerinde de tablolar oluşturabilirsiniz; sadece benzer adımları izleyin.