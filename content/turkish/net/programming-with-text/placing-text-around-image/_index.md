---
title: PDF Dosyasında Görüntünün Etrafına Metin Yerleştirme
linktitle: PDF Dosyasında Görüntünün Etrafına Metin Yerleştirme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'lerde resimlerin etrafına metin yerleştirmeyi öğrenin. Resim ve metnin yan yana olduğu profesyonel PDF'ler oluşturmak için adım adım kılavuzumuzu izleyin.
type: docs
weight: 260
url: /tr/net/programming-with-text/placing-text-around-image/
---
## giriiş

PDF dosyasındaki bir resmin etrafına metin yerleştirmeyi hiç denediniz mi ancak zorlandınız mı? Eğer öyleyse, doğru yerdesiniz! Aspose.PDF for .NET bu işlemi basitleştirir ve sadece birkaç satır kodla resimlerin yanına metin yerleştirmenize olanak tanır. İster raporlar, ister belgeler veya sunumlar oluşturuyor olun, bu özellik içeriğinizin düzenini geliştirmenin ve görsel olarak daha çekici hale getirmenin harika bir yoludur. Bugün, Aspose.PDF for .NET'i kullanarak bir PDF belgesinde resimlerin etrafına metin yerleştirmenin nasıl yapılacağını ele alacağız.

## Ön koşullar

Koda geçmeden önce her şeyin ayarlandığından emin olalım. İhtiyacınız olanlar şunlar:

-  Aspose.PDF for .NET: Buradan indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
- Visual Studio: Sorunsuz bir şekilde ilerleyebilmeniz için en son sürümün yüklü olduğundan emin olun.
- .NET Framework: Bu örnek .NET kullanır, bu nedenle ortamınızın .NET geliştirmeye uygun şekilde ayarlandığından emin olun.
-  Geçici Lisans: Geçici lisans talebinde bulunabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) eğer ürünü değerlendiriyorsanız.

Aspose.PDF'yi henüz .NET için kurmadıysanız, kurulum talimatlarını izleyin[belgeleme](https://reference.aspose.com/pdf/net/).

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce gerekli ad alanlarını içe aktarmamız gerekiyor. Bunu yapmak için kod parçacığı şu şekilde:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Bu ad alanları, aşağıdaki gibi sınıflara erişim sağladıkları için önemlidir:`Document`, `Page`, `Image` , Ve`HtmlFragment`PDF'yi oluşturmak ve düzenlemek için kullanacağımız.

Artık sahneyi hazırladığımıza göre, Aspose.PDF for .NET kullanarak PDF dosyanızdaki bir resmin etrafına nasıl metin yerleştireceğinizi açıklayalım. Bunu adım adım anlatacağız.

## Adım 1: Belge Nesnesini Örneklendirin

 Öncelikle bir PDF belgesi oluşturmanız gerekir. Aspose.PDF'de bu, bir örnek oluşturarak yapılır`Document` nesne. Bu nesne ekleyeceğimiz tüm içeriklerin temelini oluşturacaktır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Burada boş bir PDF belgesi oluşturduk. Henüz hiçbir sayfası yok, ancak endişelenmeyin, bir sonraki adımda bir tane ekleyeceğiz.

## Adım 2: Belgeye Bir Sayfa Ekleyin

Artık belgemiz olduğuna göre, bir sayfa ekleme zamanı geldi. Bunu, içeriğinizi ekleyeceğiniz boş bir kağıt parçası oluşturmak olarak düşünün.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Bu kod belgeye yeni bir sayfa ekler. Varsayılan olarak sayfa boştur, ancak bunu değiştirmek üzereyiz.

## Adım 3: İçeriği Düzenlemek İçin Bir Tablo Oluşturun

Görüntümüzü ve metnimizi düzgün bir şekilde hizalamak için bir tablo kullanacağız. PDF'lerdeki tablolar, Word belgelerinde veya HTML'de olduğu gibi düzeninizi yapılandırmanıza yardımcı olabilir.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Bu kod parçası bir tablo oluşturur ve sayfaya ekler. Tabloyu, resminizi ve metninizi hizalamak için bir çerçeve olarak düşünün.

## Adım 4: Tablo için Sütun Genişliklerini Ayarlayın

Artık bir tablo eklediğimize göre, sütunların ne kadar geniş olması gerektiğini tanımlamamız gerekiyor. Bu, görüntü ve metnin sayfada uygun şekilde boyutlandırılmasını sağlar.

```csharp
table1.ColumnWidths = "120 270";
```

Bu satır iki sütunun genişliğini ayarlar—biri resim için, diğeri metin için. Resim veya metninizin daha fazla veya daha az alana ihtiyacı varsa bu değerleri ayarlayın.

## Adım 5: Kenar Boşluklarını ve Dolguyu Tanımlayın

Her şeyin düzgün görünmesini sağlamak için tabloya biraz kenar boşluğu ve dolgu ekleyelim.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Bu ayarlar tablonuzun aralıklarının tutarlı olmasını sağlayarak içeriğin görsel olarak çekici olmasını sağlar.

## Adım 6: Tabloya Bir Resim Ekleyin

Şimdi eğlenceli kısma geçelim: Bir resim ekleme. Bu durumda, Aspose logosunu ekleyeceğiz, ancak istediğiniz herhangi bir resmi kullanmakta özgürsünüz.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

İşte olanlar:
- Resminizi belirttiğiniz dizinden yüklüyoruz.
- Resmin yüksekliğini ve genişliğini ayarlıyoruz.
- Son olarak tablonun ilk hücresine resmi ekliyoruz.

## Adım 7: Resmin Yanına Metin Ekleyin

Artık resim yerinde olduğuna göre, yanına biraz metin ekleyelim. Bu örnekte, içeriği biçimlendirmek için HTML biçimli metin kullanacağız.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Bu blok, resmin yanındaki hücreye biçimlendirilmiş bir başlık ve açıklama ekler. Daha fazla özelleştirme için metni HTML etiketleri kullanarak biçimlendirebilirsiniz.

## Adım 8: Dikey Hizalamayı Ayarlayın

Varsayılan olarak, tablo hücrelerindeki içerik istediğiniz şekilde hizalanmayabilir. Bu durumda, metnin hücrenin üstüne hizalandığından emin olmak istiyoruz.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Bu, metnin hücrenin en üstünde yer almasını sağlayarak düzenin temiz ve profesyonel kalmasını sağlar.

## Adım 9: Resmin ve Açıklamanın Altına Daha Fazla Metin Ekleyin

Görüntü ve metnin altına daha fazla içerik eklemek isteyebilirsiniz. Bu amaçla tabloya başka bir satır ekleyelim.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Burada, düzende dengeyi korumak için her iki sütuna yayılan ek metin içeren başka bir satır ekledik.

## Adım 10: PDF Belgesini Kaydedin

Son olarak değişiklikleri görebilmeniz için belgeyi kaydetmemiz gerekiyor.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Bu, PDF'i resim ve metin formatıyla istediğimiz gibi kaydeder.

## Çözüm

PDF'deki resimlerin etrafına metin yerleştirmek zorlu bir görev gibi görünebilir, ancak Aspose.PDF for .NET süreci basitleştirir. Tabloları, resimleri ve biçimlendirilmiş metni kullanarak, minimum çabayla profesyonel görünümlü PDF'ler oluşturabilirsiniz. Sadece birkaç satır kodla, içeriği tam olarak istediğiniz yere yerleştirebilir, belgelerinize cilalı ve iyi düzenlenmiş bir görünüm kazandırabilirsiniz.

## SSS

### Bu yöntemi kullanarak birden fazla görseli metinle birlikte yerleştirebilir miyim?
Evet, tablonuza daha fazla satır ve hücre ekleyerek ek resimler ve metinler ekleyebilirsiniz.

### Resmin hizalamasını değiştirebilir miyim?
Kesinlikle! Hücrenin hizalama özelliklerini ayarlayarak görüntü hizalamasını değiştirebilirsiniz.

### Metni nasıl daha fazla biçimlendirebilirim?
 HTML etiketlerini şurada kullanabilirsiniz:`HtmlFragment` Kalın, italik veya farklı yazı tipleri gibi çeşitli stiller uygulamak için nesne.

### Metin ile resim arasındaki boşluğu kontrol edebilir miyim?
 Evet, kullanarak`MarginInfo` nesnesi, öğeler arasındaki dolguyu ve kenar boşluklarını kontrol etmenizi sağlar.

### Metne bağlantı eklemek mümkün mü?
 Kesinlikle! HTML biçimli metne köprü metinleri yerleştirebilirsiniz.`<a>` etiket.