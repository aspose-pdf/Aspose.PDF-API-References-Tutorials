---
title: PDF'deki Kenarlığı Tabloya Ayarla
linktitle: PDF'deki Kenarlığı Tabloya Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'i kullanarak adım adım kılavuzumuzla PDF tablosunda kenarlıkları nasıl ayarlayacağınızı öğrenin. Belgenizin görünümünü kolayca geliştirin.
type: docs
weight: 200
url: /tr/net/programming-with-tables/set-border/
---
## giriiş

Aspose.PDF for .NET ile profesyonel görünümlü PDF belgeleri oluşturmak her zamankinden daha kolay. Raporlar, faturalar veya yapılandırılmış belgeler oluşturuyor olun, belge tasarımının temel yönlerinden biri tablolara kenarlıklar eklemektir. Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF tablosuna kenarlıkların nasıl ayarlanacağını inceleyeceğiz. Bu makalenin sonunda, PDF belgelerinizin görsel çekiciliğini zahmetsizce nasıl artıracağınızı öğreneceksiniz.

## Ön koşullar

Koda dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: .NET uygulamalarınızı yazmak ve çalıştırmak için uygun bir Entegre Geliştirme Ortamı (IDE).
2.  Aspose.PDF for .NET Library: Bu kütüphaneyi yüklediğinizden emin olun. Doğrudan şuradan indirebilirsiniz:[Aspose PDF for .NET sürümleri](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya aşinalık, kod uygulamasını daha iyi anlamanıza yardımcı olacaktır.
4. .NET Framework: Aspose.PDF for .NET ile uyumlu herhangi bir sürüm.

## Paketleri İçe Aktar

Başlamak için, Aspose kütüphanesinden gerekli paketleri içe aktarmanız gerekir. Gereken birincil ad alanı şudur:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bu, PDF belgeleri oluşturmak ve düzenlemek için ihtiyaç duyduğunuz sınıflara ve yöntemlere erişmenizi sağlayacaktır.

Şimdi, bir PDF belgesine kenarlıklı bir tablo ekleme sürecini yönetilebilir adımlara bölelim.

## Adım 1: Belge Dizinini Tanımlayın

İlk önce ilk şeyler! PDF'inizin kaydedileceği dizini belirtmek isteyeceksiniz. Bu yolu sisteminize göre güncellediğinizden emin olun.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Bu, çıktı dosyanız için temel yolu belirler, bu nedenle değiştirmeyi unutmayın`"YOUR DOCUMENT DIRECTORY"` makinenizdeki gerçek bir yola.

## Adım 2: Belge Nesnesini Örneklendirin

 Daha sonra, bir örnek oluşturmanız gerekir`Document` sınıf. Bu sınıf, üzerinde çalışacağınız tüm PDF belgesini temsil eder.

```csharp
Document doc = new Document();
```

 Örnekleme yaparak`Document` nesne, PDF'nize sayfalar ve içerik eklemeye hazırlanıyorsunuz.

## Adım 3: Belgeye Bir Sayfa Ekleyin

Her PDF bir veya daha fazla sayfadan oluşur. Bu adımda PDF belgemize yeni bir sayfa ekleyeceğiz.

```csharp
Page page = doc.Pages.Add();
```

Burada, tablomuzun gideceği yere boş bir sayfa ekleyerek belgemizi büyütüyoruz. Bunu bir şaheser için boş bir tuval hazırlamak gibi düşünün!

## Adım 4: BorderInfo Nesnesini Oluşturun

 Şimdi masamızın sınırlarını belirleme zamanı.`BorderInfo` sınıfı, kenarlık özelliklerini belirtmenize olanak tanır.

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

 Bu satırda bir tane oluşturuyoruz`BorderInfo` Hücrelerin tüm kenarlarına uygulanacak nesne.

## Adım 5: Kenarlık Stillerini Ayarlayın

Sonra, sınırların nasıl görünmesi gerektiğini belirteceğiz. İşte yaratıcı olabileceğiniz yer burası!

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

Bu örnekte, üst ve alt sınırların iki katına çıkarılması gerektiğini belirtiyoruz. Bu, tablonuza vurgu ve görsel derinlik katmak için harikadır.

## Adım 6: Tablo Nesnesini Örneklendirin

Sınırlar tanımlandıktan sonra sıra tabloyu oluşturmaya geldi.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

Şimdi veri tutmaya hazır boş bir tablomuz var. Üzerine inşa edebileceğiniz bir iskelet yapısı oluşturmak gibi.

## Adım 7: Sütun Genişliklerini Tanımlayın

Herhangi bir tablo için sütun genişliklerini ayarlamak çok önemlidir. Bu, içeriğinizin iyi oturmasını ve düzenli görünmesini sağlar.

```csharp
table.ColumnWidths = "100";
```

Bu satır tablomuzdaki tüm sütunlar için 100 puanlık tekdüze bir genişlik belirler. Bunu içerik ihtiyaçlarınıza göre ayarlayabilirsiniz.

## Adım 8: Bir Satır Oluşturun

Her tablonun en az bir satıra ihtiyacı vardır, onu da ekleyelim.

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

Bu komutla, yeni oluşturduğumuz tabloya yeni bir satır ekliyoruz. Bir binanın temelini atmak gibi, diğer her şey bunun üzerine inşa ediliyor.

## Adım 9: Metinli Bir Hücre Ekleyin

Şimdi, bir hücre oluşturarak tablomuza biraz içerik ekleyelim. Hücreler gerçek verilerin bulunduğu yerlerdir.

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

 Değiştirmekten çekinmeyin`"some text"` görüntülemek istediğiniz herhangi bir dizeyle. Bu bir etiket, bir sayı veya belgeniz için gerekli herhangi bir metinsel bilgi olabilir.

## Adım 10: Hücre için Kenarlığı Ayarlayın

İşte sihir burada gerçekleşiyor! Şimdi daha önce tanımlanmış olan sınırı tablomuzdaki hücreye atayacaksınız.

```csharp
cell.Border = border;
```

Şimdi hücre, belirttiğimiz şekilde üstte ve altta çift kenarlıkla biçimlendirildi. Bu, içeriğinizi özel bir durum için giydirmek gibi.

## Adım 11: Tabloyu Sayfaya Ekleyin

Her şey ayarlandıktan sonra, tabloyu görüntüleneceği sayfaya eklemenin zamanı geldi.

```csharp
page.Paragraphs.Add(table);
```

Bu çizgi tabloyu sayfanın içeriğine entegre eder. Bunu tamamlanmış resmi bir galeri duvarına yerleştirmek olarak düşünün.

## Adım 12: Belgeyi Kaydedin

Son olarak geriye sadece belgenizi belirtilen dizine kaydetmek kalıyor.

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);
```

Gerekirse dosya adını ayarladığınızdan emin olun! Programınızı çalıştırdığınızda, tabloda kenarlıkları olan PDF'niz oluşturulacak ve tanımlanan konuma kaydedilecektir.

## Çözüm

Kenarlıklı bir tablo içeren bir PDF belgesi oluşturmak, okunabilirliğini ve profesyonelliğini önemli ölçüde artırabilir. .NET için Aspose.PDF'nin yardımıyla, bu görev basit ve verimli hale gelir. Bu eğitimde özetlenen adımları izleyerek, tablolarınıza kolayca kenarlıklar ayarlayabilir, PDF belgelerinizi yalnızca işlevsel değil, aynı zamanda görsel olarak da çekici hale getirebilirsiniz.

## SSS

### Kenarlık stilini kesikli veya noktalı olarak değiştirebilir miyim?  
 Evet! Kenarlık özelliklerini değiştirebilirsiniz.`BorderInfo` Uygun özellikleri ayarlayarak kesikli veya noktalı kenarlıklar oluşturmak için nesne.

### Aspose.PDF tablolardaki resimleri destekliyor mu?  
 Kesinlikle! Tıpkı metinde olduğu gibi tablo hücrelerine de resim ekleyebilirsiniz.`Cell` sınıfın yöntemleri.

### Farklı sütunlar için farklı genişlikleri nasıl belirleyebilirim?  
 Genişlik dizelerini kullanarak her sütun genişliğini ayrı ayrı tanımlayabilirsiniz, örneğin:`"100;150;200"`.

### Aynı sayfada birden fazla tablo oluşturabilir miyim?  
Evet! Tablo oluşturma adımlarını tekrarlayarak aynı sayfada ihtiyacınız kadar tablo oluşturabilir ve ekleyebilirsiniz.

### Tablo hücrelerine stil uygulamanın bir yolu var mı?  
 Elbette! Arka plan rengi, metin stili ve hizalama gibi çeşitli özellikleri ayarlayabilirsiniz.`Cell` nesne.