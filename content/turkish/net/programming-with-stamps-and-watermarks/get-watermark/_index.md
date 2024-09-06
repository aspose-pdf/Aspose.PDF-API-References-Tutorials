---
title: PDF Dosyasından Filigran Al
linktitle: PDF Dosyasından Filigran Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasından filigranların nasıl çıkarılacağını öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-stamps-and-watermarks/get-watermark/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasından filigran alma konusunda adım adım yol göstereceğiz. Sağlanan C# kaynak kodunu kullanarak belirli bir sayfanın yapıtları arasında nasıl gezineceğinizi ve filigran türünü, metnini ve konumunu nasıl alacağınızı göstereceğiz.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini açın
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizin bulunduğu dizinin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 3: Filigranı alma

Artık PDF belgesini yüklediğinize göre, filigran bilgilerini almak için belirli sayfa yapıtları arasında yineleme yapabilirsiniz. İşte nasıl:

```csharp
// Eserlere göz atın ve filigran alt türünü, metni ve konumu alın
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Yukarıdaki kod, PDF belgesinin ilk sayfasındaki tüm eserleri dolaşır ve karşılaşılan her filigranın alt türünü, metnini ve dikdörtgenini (konumunu) görüntüler.

### .NET için Aspose.PDF kullanarak Filigran Almak için örnek kaynak kodu 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Yineleme yapın ve yapıtın küvet türünü, metnini ve konumunu alın
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinden filigran bilgisinin nasıl alınacağını öğrendiniz. Şimdi bu bilgiyi PDF belgelerinizdeki filigranları analiz etmek ve işlemek için kullanabilirsiniz.

### PDF dosyasından filigran alma hakkında SSS

#### S: PDF belgesinde filigran nedir ve bilgilerini neden çıkarmam gerekir?

A: PDF belgesindeki filigran, genellikle durumunu, sahipliğini veya gizli niteliğini belirtmek için belgenin içeriğine eklenen tanınabilir bir görüntü veya metindir. Filigran bilgilerini çıkarmak, belgenin gerçekliğini analiz etmek, belge kaynağını belirlemek veya belgeleri filigran varlığına göre işlemek için yararlı olabilir.

#### S: Sağlanan C# kaynak kodu bir PDF dosyasından filigran bilgilerinin çıkarılmasına nasıl yardımcı olur?

 A: Sağlanan kod, mevcut bir PDF belgesinin nasıl yükleneceğini, belirli bir sayfanın yapıtları arasında nasıl gezinileceğini ve filigranlar hakkında bilginin nasıl çıkarılacağını gösterir. Bunu, şuraya erişerek yapar:`Subtype`, `Text` , Ve`Rectangle` Her bir eserin özellikleri.

####  S: Ne anlama geliyor?`Subtype` property of an artifact represent?

 A:`Subtype` Bir eserin özelliği, eserin türünü temsil eder. Filigranlar için, eserin bir filigran olduğunu gösterir.

#### S: Kod, filigranın sayfadaki konumunu (dikdörtgen) nasıl belirler?

 A: Kod şunu kullanır:`Rectangle` filigranın yerini belirlemek için eserin özelliği.`Rectangle` özellik, sayfadaki yapıtın sınırlayıcı dikdörtgenini temsil eder.

#### S: Filigranın görünümü veya rengi gibi ek bilgileri çıkarmak için kodu değiştirebilir miyim?

C: Evet, eğer bu tür bilgiler mevcutsa ve kullanım durumunuzla alakalıysa, eserin görünümü veya rengi gibi diğer özelliklerine erişmek için kodu değiştirebilirsiniz.

#### S: Bu kodu kullanarak PDF belgesinin birden fazla sayfasından filigran bilgilerini çıkarabilir miyim?

C: Evet, döngüdeki sayfa dizinini değiştirerek farklı sayfalardaki eserler arasında yineleme yapmak için kodu düzenleyebilirsiniz.

#### S: Belirtilen sayfada filigran yoksa ne olur?

A: Belirtilen sayfada filigran yoksa döngü yürütülmeyecek ve filigran bilgisi görüntülenmeyecektir.

#### S: Çıkarılan filigran bilgilerini daha sonraki işlemlerde nasıl kullanabilirim?

A: Çıkarılan filigran bilgileri, filigranların varlığına veya özelliklerine dayalı olarak günlük kaydı tutma, analiz etme, raporlama veya belirli eylemlerin otomasyonu gibi çeşitli amaçlarla kullanılabilir.

#### S: Bu kodu, bir PDF belgesindeki diğer türdeki eserler hakkında bilgi çıkarmak için değiştirebilir miyim?

C: Evet, benzer bir yaklaşım kullanarak diğer türdeki eserlerin özelliklerine erişerek bunlar hakkında bilgi çıkarmak için kodu değiştirebilirsiniz.

#### S: Eser olmayan ancak PDF içeriğinin bir parçası olan filigranlara nasıl erişebilirim?

A: Eser olmayan filigranlar, PDF içeriğinin bir parçası olabilir, örneğin resimler veya metinler. Bu tür filigranlar hakkında bilgi çıkarmak için PDF içeriğini analiz etmeniz ve filigranları temsil eden belirli öğeleri tanımlamanız gerekebilir.