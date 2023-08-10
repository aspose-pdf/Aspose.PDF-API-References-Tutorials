---
title: PDF Dosyasından Filigran Alın
linktitle: PDF Dosyasından Filigran Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasından filigranları nasıl çıkaracağınızı öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-stamps-and-watermarks/get-watermark/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasından nasıl filigran alacağınızı adım adım anlatacağız. Belirli bir sayfanın yapıtlarını yinelemek ve filigran türünü, metnini ve konumunu almak için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//PDF belgesini aç
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Filigranı alma

Artık PDF belgesini yüklediğinize göre, filigran bilgilerini almak için belirli sayfa yapılarını yineleyebilirsiniz. İşte nasıl:

```csharp
// Eserlere göz atın ve filigran alt türünü, metnini ve konumunu alın
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Yukarıdaki kod, PDF belgesinin ilk sayfasındaki tüm yapılar arasında dolaşır ve karşılaşılan her filigranın alt tipini, metnini ve dikdörtgenini (konumu) görüntüler.

### Aspose.PDF for .NET kullanarak Get Watermark için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Yineleme yapın ve küvet tipini, metnini ve yapının konumunu alın
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinden filigran bilgisi almayı öğrendiniz. Artık bu bilgiyi PDF belgelerinizdeki filigranları analiz etmek ve işlemek için kullanabilirsiniz.

### PDF dosyasından filigran almayla ilgili SSS

#### S: Bir PDF belgesindeki filigran nedir ve neden bilgilerini almam gerekir?

Y: Bir PDF belgesindeki filigran, genellikle durumunu, sahipliğini veya gizli yapısını belirtmek için belgenin içeriğine eklenen tanınabilir bir resim veya metindir. Filigran bilgilerinin çıkarılması, belge doğruluğunu analiz etmek, belge kaynağını belirlemek veya belgeleri filigran varlığına dayalı olarak işlemek için yararlı olabilir.

#### S: Sağlanan C# kaynak kodu, bir PDF dosyasından filigran bilgilerinin çıkarılmasına nasıl yardımcı olur?

 C: Sağlanan kod, mevcut bir PDF belgesinin nasıl yükleneceğini, belirli bir sayfanın yapıları arasında yinelemenin nasıl yapılacağını ve filigranlarla ilgili bilgilerin nasıl çıkarılacağını gösterir. Bunu, şuraya erişerek yapar:`Subtype`, `Text` , Ve`Rectangle` her eserin özellikleri.

####  S: ne yapar`Subtype` property of an artifact represent?

 C:`Subtype` Bir yapının özelliği, yapının türünü temsil eder. Filigranlar için, yapının bir filigran olduğunu belirtir.

#### S: Kod, filigranın sayfadaki konumunu (dikdörtgen) nasıl belirler?

 C: Kod şunu kullanır:`Rectangle` filigranın konumunu belirlemek için yapının özelliği. bu`Rectangle` özelliği, sayfadaki yapıtın sınırlayıcı dikdörtgenini temsil eder.

#### S: Filigran hakkında görünümü veya rengi gibi ek bilgileri çıkarmak için kodu değiştirebilir miyim?

C: Evet, bu tür bilgiler mevcutsa ve kullanım durumunuzla ilgiliyse, yapının görünümü veya rengi gibi diğer özelliklerine erişmek için kodu değiştirebilirsiniz.

#### S: Bu kodu kullanarak bir PDF belgesinin birden çok sayfasından filigran bilgilerini çıkarabilir miyim?

C: Evet, farklı sayfalardaki yapılara erişmek için döngüdeki sayfa dizinini değiştirerek birden çok sayfadaki yapılar arasında yineleme yapmak üzere kodu değiştirebilirsiniz.

#### S: Belirtilen sayfada filigran yoksa ne olur?

C: Belirtilen sayfada filigran yoksa döngü yürütülmez ve filigran bilgisi görüntülenmez.

#### S: Ayıklanan filigran bilgilerini daha sonraki işlemler için nasıl kullanabilirim?

C: Ayıklanan filigran bilgileri, filigranların varlığına veya özelliklerine dayalı olarak günlük kaydı, analiz, raporlama veya belirli eylemlerin otomasyonu gibi çeşitli amaçlar için kullanılabilir.

#### S: Bir PDF belgesindeki diğer yapı türleri hakkında bilgi çıkarmak için bu kodu değiştirebilir miyim?

C: Evet, benzer bir yaklaşım kullanarak özelliklerine erişerek diğer yapı türleri hakkında bilgi çıkarmak için kodu değiştirebilirsiniz.

#### S: Yapay olmayan ancak PDF içeriğinin parçası olan filigranlara nasıl erişebilirim?

Y: Yapay olmayan filigranlar, resimler veya metin gibi PDF içeriğinin kendisinin bir parçası olabilir. Bu tür filigranlar hakkında bilgi almak için PDF içeriğini analiz etmeniz ve filigranları temsil eden belirli öğeleri belirlemeniz gerekebilir.