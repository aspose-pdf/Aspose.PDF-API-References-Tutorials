---
title: PDF Dosyasında Özel Sekme Durakları
linktitle: PDF Dosyasında Özel Sekme Durakları
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF kullanarak bir PDF'de özel sekme duraklarının nasıl ayarlanacağını öğrenin. Bu eğitim, metni profesyonelce hizalamak için adım adım talimatları kapsar.
type: docs
weight: 120
url: /tr/net/programming-with-text/custom-tab-stops/
---
## giriiş

Hiç PDF içindeki metni biçimlendirmek zorunda kaldınız mı ve her kelimenin nasıl sıralanacağı konusunda kesin bir kontrole sahip olmayı dilediniz mi? İşte tam bu noktada sekme durakları işe yarıyor! Word belgelerinde olduğu gibi, metninizi PDF'nizdeki belirli noktalarda mükemmel bir şekilde hizalamak için özel sekme duraklarını kullanabilirsiniz. İçeriği sağa hizalamak, ortaya hizalamak veya sola hizalamak isteyip istemediğinize bakılmaksızın, Aspose.PDF for .NET bunu kolaylaştırır. Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyanızda özel sekme duraklarını nasıl ayarlayacağınızı göstereceğiz. Sonunda, kolayca güzelce hizalanmış bir belge oluşturabileceksiniz.

## Ön koşullar

Başlamadan önce, takip etmeniz gerekenler şunlardır:

-  .NET için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olması gerekir.[buradan indirin](https://releases.aspose.com/pdf/net/).
- .NET Geliştirme Ortamı: .NET uygulamalarını çalıştırmak için Visual Studio veya başka bir IDE'nin kurulu olduğundan emin olun.
- C# Hakkında Temel Bilgi: C# dilinde kod yazacağız, dolayısıyla bu dile aşina olmanız önerilir.
-  Geçici Lisans: Şunu kullanabilirsiniz:[geçici lisans](https://purchase.aspose.com/temporary-license/)Aspose.PDF for .NET'in tüm özelliklerinin kilidini açmak için.

Her şey hazır olduğunda, gerekli paketleri içeri aktarma ve ortamı ayarlama aşamasına geçelim.

## Paketleri İçe Aktar

Başlamak için Aspose.PDF ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

 Bu iki satır önemlidir.`Aspose.Pdf` namespace belge yapısını sağlarken`Aspose.Pdf.Text` bize özel sekme durakları gibi metne özgü özelliklere erişim sağlar.

PDF'de özel sekme durakları ayarlama sürecini parçalara ayıralım. Tam olarak ne olduğunu anlamanızı sağlamak için her adımı ayrıntılı olarak ele alacağız.

## Adım 1: Yeni bir PDF Belgesi Oluşturun

Yapmanız gereken ilk şey yeni bir PDF belgesi oluşturmaktır. Bunu tuvaliniz olarak düşünün. Sayfalar ekleyecek ve ardından biçimlendirilmiş metninizi bunların üzerine yerleştireceksiniz.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
```

Bu kesitte:
-  Yeni bir şey yaratıyoruz`Document` nesne.
-  Belgeye yeni bir sayfa eklemek için şunu kullanıyoruz:`Pages.Add()`. Buraya tab duraklı metni ekleyeceğiz.

## Adım 2: Sekme Duraklarını Ayarlayın

Artık boş bir belgemiz olduğuna göre, sekme duraklarını tanımlamanın zamanı geldi. Sekme durakları, metnin sayfadaki farklı konumlarda nasıl hizalanacağını kontrol eder. Örneğin, bazı metinleri sağa, diğerlerini ortaya veya sola hizalamak isteyebilirsiniz.

```csharp
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
```

Burada biz:
-  Birini başlat`TabStops` Özel sekme duraklarımızı tutacak nesne.
-  100 piksel işaretinde bir sekme durağı ekleyin`ts.Add(100)`. Bu sekmenin nerede oluşacağını tanımlar.
-  Hizalama türünü şu şekilde ayarlayın:`Right`, bu sekme durağına çarpan metnin sağa hizalanacağı anlamına gelir.
- Bir lider türü tanımlayın. Liderler, sekme durağının önündeki boşluğu dolduran noktalar veya çizgilerdir. Bu durumda, düz bir çizgi kullanırız.

## Adım 3: Daha Fazla Sekme Durağı Ekleyin

İhtiyacımız kadar sekme durağı ekleyebiliriz. Bu örnekte, bir orta hizalı sekme ve bir de sola hizalı sekme ekleyeceğiz.

```csharp
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

- İkinci sekme durağı, merkez hizalama ve çizgi lideri ile 200 piksel olarak ayarlanmıştır.
- Üçüncü sekme durağı 300 piksele yerleştirilir, sola hizalanır ve noktalı bir lider kullanır.

## Adım 4: Sekme Duraklarıyla Metin Oluşturun

Artık sekme durakları ayarlandığına göre, bunları kullanan bir metin oluşturmanın zamanı geldi. Bu sekme duraklarını, içeriğinizi farklı konumlarda hizalamaya yardımcı olan görünmez kılavuzlar olarak düşünebilirsiniz.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
```

- `TextFragment` bir metin parçasını temsil eder.
- Sekme işaretleyicileri kullanıyoruz (`#$TAB`) PDF'e sekme duraklarının nerede uygulanacağını söylemek için.
-  Örneğin,`text0`, `#$TABHead1` ilk sekme durağına göre hizalanacaktır,`#$TABHead2` ikinciye hizalanacak ve bu böyle devam edecek.

## Adım 5: Metne Segmentler Ekleyin

 Bazen metninizi her biri kendi sekme durağına sahip birden fazla parçaya bölmek isteyebilirsiniz. İşte tam da bu noktada`TextSegment` işe yarar.

```csharp
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
```

Bu durumda:
-  Şöyle başlayalım`#$TABdata21`, ilk sekme durağına hizalanır.
-  Daha fazla segment ekliyoruz`data22` Ve`data23`, her biri farklı sekme duraklarına hizalanır.

## Adım 6: PDF Sayfasına Metin Ekleme

Artık tüm metin parçalarımızı oluşturduğumuza göre, onları sayfaya eklemenin zamanı geldi.

```csharp
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

 Bu kod her birini ekler`TextFragment`PDF sayfasına, metnin sekme duraklarına göre biçimlendirilmesini sağlayarak.

## Adım 7: PDF Belgesini Kaydedin

Son olarak belgeyi belirttiğiniz dizine kaydetmemiz gerekiyor.

```csharp
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

- PDF dosyası özel sekme durakları uygulanarak kaydedilir.
- Dosyanın başarıyla oluşturulduğunu onaylayan bir mesaj görüntülenir.

## Çözüm

İşte karşınızda! Bu kılavuzu takip ederek, .NET için Aspose.PDF kullanarak bir PDF belgesinde özel sekme durakları oluşturmayı öğrendiniz. Sekme durakları, metni yapılandırılmış ve görsel olarak çekici bir şekilde hizalamanıza olanak tanır ve PDF'lerinizi daha profesyonel hale getirir. Fatura ayrıntılarını, tabloları veya başka herhangi bir veri biçimini hizalıyor olun, bu özellik size metin yerleşimi üzerinde tam kontrol sağlar.

## SSS

### Mevcut PDF'lere sekme durdurucuları uygulayabilir miyim?  
Evet, metni hizalamak için özel sekme durakları ekleyerek mevcut PDF'leri değiştirebilirsiniz.

### Hangi lider tipleri mevcuttur?  
Sekme durağının önündeki boşluğu doldurmak için düz, kesikli, noktalı ve diğer lider türlerinden birini seçebilirsiniz.

### Tek bir satıra birden fazla hizalama türü ekleyebilir miyim?  
Kesinlikle! Örnekte gösterildiği gibi aynı satırda sağ, sol ve orta hizalamaları birleştirebilirsiniz.

### Ekleyebileceğim sekme durağı sayısında bir sınır var mı?  
Hayır, tasarım gereksinimlerinize uyacak şekilde istediğiniz kadar sekme durağı ekleyebilirsiniz.

### Sekme duraklarının konumunu özelleştirebilir miyim?  
Evet, her sekme durağı için düzeninize uyacak şekilde tam piksel konumunu tanımlayabilirsiniz.