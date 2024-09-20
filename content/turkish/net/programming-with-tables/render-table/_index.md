---
title: Tabloyu PDF Belgesinde Oluştur
linktitle: Tabloyu PDF Belgesinde Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF ile tabloları işleyerek profesyonel PDF'leri kolayca oluşturun. Belge oluşturmada ustalaşmak için adım adım kılavuzumuzu izleyin.
type: docs
weight: 170
url: /tr/net/programming-with-tables/render-table/
---
## giriiş

Profesyonel görünümlü PDF'leri programatik olarak oluşturmak zorlu bir görev gibi görünebilir, ancak .NET için Aspose.PDF ile bu bir esinti haline gelir. Raporlar, faturalar veya tablo verileri gerektiren başka bir belge türü oluşturuyor olun, Aspose.PDF ihtiyacınız olan araçları sunar. Bu eğitimde, bir PDF belgesinde tabloların adım adım nasıl işleneceğini inceleyeceğiz. Sonunda, tabloları nasıl işleyeceğinizi, sayfa özelliklerini nasıl yöneteceğinizi ve PDF dosyalarını nasıl kolayca kaydedeceğinizi sağlam bir şekilde anlayacaksınız.

## Ön koşullar

Koda dalmadan önce ihtiyacınız olanlar şunlardır:

-  Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. İndirebilirsiniz[Burada](https://visualstudio.microsoft.com/downloads/).
-  .NET için Aspose.PDF: Aspose.PDF kütüphanesini şu adresten kolayca indirebilirsiniz:[Aspose sürüm sayfası](https://releases.aspose.com/pdf/net/).
- C# Temel Bilgisi: C# temellerini anlamak, konuyu daha iyi takip etmenize yardımcı olacaktır.
- .NET Framework: İdeal olarak, uyumlu bir .NET ortamında çalıştığınızdan emin olun.

Bu ön koşulları sağladıktan sonra PDF belgelerinizi oluşturmaya başlayabilirsiniz!

## Paketleri İçe Aktar

C# dosyanızın başlangıcında, gerekli Aspose.PDF ad alanlarını içe aktarmanız gerekecektir. Bu, projemizde kütüphane işlevselliklerini kullanmanıza olanak tanır.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

 Projenizde Aspose.PDF kütüphanesine gerekli referansları eklediğinizden emin olun. NuGet kullanıyorsanız, bunu arayarak kolayca ekleyebilirsiniz`Aspose.PDF`.

Artık her şeyi ayarladığımıza göre, bir PDF belgesinde tabloyu işlemek için süreci yönetilebilir adımlara bölelim. Endişelenmeyin; her adımda sizi net talimatlarla yönlendireceğim!

## Adım 1: Belge ve Sayfa Bilgilerini Ayarlayın

İlk önce, yeni bir belge oluşturmamız ve sayfa ayarlarını yapılandırmamız gerekiyor. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

Açıklama: 
- Belgemizin nereye kaydedileceğini tanımlayarak başlıyoruz (`dataDir`). 
-  Daha sonra, yeni bir örnek oluşturuyoruz`Document` sınıf. 
- Masamızın etrafında nefes alacak alan yaratmak için sayfa kenar boşluklarını ayarlıyoruz.
- Son olarak, daha geniş tabloları görüntülerken yardımcı olması için belgeyi yatay yönelime ayarladık.

## Adım 2: İlk Tabloyu Oluşturun

Şimdi ilk tablomuzu oluşturalım ve onu bazı örnek verilerle dolduralım:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100"; // Sütun genişliklerini tanımla
```

 Açıklama: Burada, şunu örneklendiriyoruz:`Table` sınıf ve sütun genişliklerini ayarlayın. İlk sütun 50 birim genişliğinde olacak ve ikinci sütun 100 birim genişliğinde olacak.

## Adım 3: Tabloyu Satırlarla Doldurun

Şimdi tablomuza bir döngü içerisinde satır ekleyelim:

```csharp
Page curPage = doc.Pages.Add(); // Yeni bir sayfa ekleme
for (int i = 1; i <= 120; i++)
{
    Aspose.Pdf.Row row = table.Rows.Add();
    row.FixedRowHeight = 15; // Satırlar için sabit bir yükseklik ayarlayın
    
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("Content 1"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

Açıklama: 
- Burada tablomuzu eklemek için yeni bir sayfa oluşturuyoruz.
-  Biz bir kullanıyoruz`for` Tablomuza 120 satır eklemek için döngü. Her satırın sabit 15 birimlik bir yüksekliği vardır.
- Her satırın içine iki hücre ekliyoruz ve bu hücreleri metinle dolduruyoruz.

## Adım 4: Sayfaya İlk Tabloyu Ekleyin

Tabloyu doldurduktan sonra onu geçerli sayfaya ekleyeceğiz:

```csharp
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
```

Açıklama: Bu adım, oluşturduğumuz tabloyu geçerli sayfanın paragraflarına ekleyerek, tablonun PDF belgesinde görünür olmasını sağlar.

## Adım 5: İkinci Bir Tablo Oluşturun

Şimdi farklı içerikli ikinci bir tablo oluşturalım ve onu yeni bir sayfaya ekleyelim:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
    Aspose.Pdf.Row row = table1.Rows.Add();
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true; // İkinci tablonun yeni bir sayfada görünmesini ayarlama
paragraphs.Add(table1);
```

Açıklama: 
- Bu kod parçacığı, her ikisi de 100 birim genişliğinde iki sütundan oluşan yeni bir tablo oluşturur.
-  A`for` döngü örnek içerikli 10 satır ekler.
-  Ayarlayarak`table1.IsInNewPage` Doğrusunu söylemek gerekirse, bu tablonun yeni bir sayfada görünmesini sağlayarak her şeyin düzenli ve temiz kalmasını sağlıyoruz.

## Adım 6: Belgeyi Kaydedin

Tablolarımız hazır olduğuna göre artık belgemizi kaydedelim:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);
```

 Açıklama: Dosya adını belirtip belgeyi tanımlanan dizine kaydediyoruz. Bu kodu çalıştırdığınızda, başlıklı bir PDF dosyası`IsNewPageProperty_Test_out.pdf` belirttiğiniz lokasyonda oluşturulacaktır.

## Adım 7: Onay Mesajı

Son olarak, kullanıcıya her şeyin düzgün çalıştığını bildirmek için kullanıcı dostu bir konsol mesajı ekleyebiliriz:

```csharp
Console.WriteLine("\nTable rendered successfully on a page.\nFile saved at " + dataDir);
```

Açıklama: Bu, işlemin başarılı olduğunu ve kullanıcının yeni PDF dosyasını bulabileceğini doğrulamanın basit bir yoludur.

## Çözüm

İşte karşınızda! .NET için Aspose.PDF kullanarak bir PDF belgesinde tabloları başarıyla oluşturdunuz. Sadece birkaç satır kodla, büyük miktarda veriyi düzenli bir biçimde işleyebilir ve sunabilir, belgelerinizi hem bilgilendirici hem de görsel olarak çekici hale getirebilirsiniz. İster envanter listeleri, ister finansal raporlar veya eğitim belgeleri üzerinde çalışıyor olun, tablolar karmaşık bilgileri tek bakışta iletmenin mükemmel bir yoludur.

## SSS

### Aspose.PDF'deki tabloların görünümünü özelleştirebilir miyim?  
Kesinlikle! Tablolarınızın görünümünü geliştirmek için renkleri, kenarlıkları, yazı tiplerini ve diğer özellikleri ayarlayabilirsiniz.

### Aspose.PDF'i kullanmak ücretsiz mi?  
 Aspose.PDF ücretsiz deneme sürümü sunar, ancak ticari kullanım için satın alma gereklidir. Fiyatlandırmayı kontrol edebilirsiniz[Burada](https://purchase.aspose.com/buy).

### Aspose.PDF sorunları için nasıl destek alabilirim?  
 Aspose destek forumundan yardım alabilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).

### Ücretsiz deneme sürümünde herhangi bir sınırlama var mı?  
 Evet, deneme sürümünde, oluşturulan belgelerde filigran gibi belirli sınırlamalar olabilir. Tam işlevsellik için geçici bir lisans edinmeyi düşünün[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.PDF özellikleri hakkında daha fazla bilgiyi nerede bulabilirim?  
 Mevcut kapsamlı belgeleri inceleyebilirsiniz[Burada](https://reference.aspose.com/pdf/net/).