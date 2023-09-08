---
title: PDF Dosyasında Belirtme Özelliğini Ayarlama
linktitle: PDF Dosyasında Belirtme Özelliğini Ayarlama
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF Dosyasında Bilgi Özelliğini nasıl ayarlayacağınızı öğrenin. Ek açıklamaları belirtme çizgileri, metin rengi ve bitiş stilleriyle özelleştirin.
type: docs
weight: 130
url: /tr/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET, C# dilinde PDF belgeleri oluşturmaya, işlemeye ve dönüştürmeye yönelik güçlü bir kitaplıktır. Bu kitaplığın sağladığı özelliklerden biri, PDF belgelerindeki serbest metin açıklamaları için belirtme çizgisi özelliklerini ayarlama yeteneğidir. Bu, kullanılarak yapılabilir.`FreeTextAnnotation` belirtme çizgileriyle ek açıklamalar oluşturmanıza olanak tanıyan sınıf.

Bu eğitimde, C#'ta Aspose.PDF for .NET kullanarak serbest metin açıklaması için belirtme çizgisi özelliklerini ayarlama sürecinde size rehberlik edeceğiz. Başlamak için aşağıdaki adımları izleyin.

## Aspose.PDF for .NET'i yükleyin

 Henüz yapmadıysanız, yapmanız gerekecek[indirmek](https://releases.aspose.com/pdf/net/) ve Aspose.PDF for .NET'i Aspose Sürümlerinden veya NuGet paket yöneticisi aracılığıyla yükleyin.

## 1. Adım: Yeni bir PDF belgesi oluşturun

 kullanarak yeni bir PDF belgesi oluşturun.`Document`sınıf Aspose.PDF for .NET tarafından sağlanmıştır.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye yeni bir sayfa ekleyin

 kullanarak belgeye yeni bir sayfa ekleyin.`Pages` koleksiyonu`Document` sınıf.

```csharp
Page page = doc.Pages.Add();
```

## 3. Adım: Varsayılan görünümü ayarlayın

 Yeni bir açıklama oluşturarak serbest metin açıklamasının varsayılan görünümünü ayarlayın.`DefaultAppearance` nesne ve onun gibi özelliklerinin ayarlanması`TextColor` Ve`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## 4. Adım: Belirtme çizgisiyle serbest metin ek açıklaması oluşturun

 kullanarak yeni bir serbest metin ek açıklaması oluşturun.`FreeTextAnnotation` sınıf. Yı kur`Intent` mülkiyet`FreeTextIntent.FreeTextCallout` Bunun bir belirtme çizgisi ek açıklaması olduğunu belirtmek için. Yı kur`EndingStyle` mülkiyet`LineEnding.OpenArrow` belirtme çizgisinin sonundaki okun stilini belirtmek için. Yı kur`Callout` bir dizi özellik`Point` sayfada belirtme çizgisinin çizilmesi gereken noktaları temsil eden nesneler.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## 5. Adım: Serbest metin açıklamasını sayfaya ekleyin

 Serbest metin açıklamasını kullanarak sayfaya ekleyin.`Annotations` koleksiyonu`Page` sınıf.

```csharp
page.Annotations.Add(fta);
```

## 6. Adım: Ek açıklamaya metin ekleyin

 ayarlayarak ek açıklamaya metin ekleyin.`RichText`özelliği, biçimlendirilmiş bir XML dizisinin özelliğidir. Bu eğitimde metin rengini kırmızıya ve yazı tipi boyutunu 9'a ayarlıyoruz.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"renk:#FF
```

## Adım 7: belgeyi kaydedin

Şimdi aşağıdaki kodu kullanarak belgeyi kaydedin:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Aspose.PDF for .NET kullanarak Set Callout Property için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Bu bir örnektir</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki serbest metin açıklaması için belirtme çizgisi özelliklerinin nasıl ayarlanacağını araştırdık. Belirtme çizgisi ek açıklamaları, bir belgedeki belirli alanlarla ilgili ek bilgi veya açıklamalar sağlamak için kullanışlıdır. Aspose.PDF for .NET, PDF dosyalarıyla çalışmak için, belirtme çizgileri gibi ek açıklamaların oluşturulması ve özelleştirilmesi de dahil olmak üzere çok çeşitli özellikler ve yetenekler sağlar. Geliştiriciler, adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, PDF belgelerine belirtme çizgileri ek açıklamalarını kolayca uygulayabilir, belgelerinin kullanılabilirliğini ve netliğini artırabilir. Aspose.PDF for .NET, .NET uygulamalarındaki PDF işlemleri için çok yönlü ve güvenilir bir kitaplıktır ve PDF ile ilgili çeşitli görevleri verimli bir şekilde gerçekleştirmek için güçlü araçlar sunar.

### PDF dosyasındaki belirtme çizgisi özelliğini ayarlamak için SSS

#### S: PDF belgesindeki belirtme çizgisi açıklaması nedir?

C: PDF belgesindeki belirtme çizgisi ek açıklaması, belgedeki belirli bir alanı işaret eden öncü çizgiye sahip bir metin kutusu oluşturmanıza olanak tanıyan bir ek açıklama türüdür. Genellikle belgedeki belirli bir bölüm veya öğeyle ilgili ek bilgi veya yorum sağlamak için kullanılır.

#### S: Belirtme çizgisi açıklamasının görünümünü Aspose.PDF for .NET'i kullanarak özelleştirebilir miyim?

C: Evet, belirtme çizgisi ek açıklamasının renk, yazı tipi boyutu, metin hizalaması, çizgi stili, ok stili ve daha fazlası gibi çeşitli özelliklerini özelleştirebilirsiniz.

#### S: Belirtme çizgisi ek açıklamasına nasıl metin eklerim?

 C: Belirtme çizgisi ek açıklamasına metin eklemek için`RichText` mülkiyeti`FreeTextAnnotation` nesne.`RichText` özelliği, belirtme çizgisi ek açıklamasında görüntülenecek metni temsil eden biçimlendirilmiş XML dizesini alır.

#### S: Aspose.PDF for .NET'i kullanarak bir PDF belgesine birden fazla belirtme çizgisi ek açıklaması ekleyebilir miyim?

 C: Evet, bir PDF belgesinde birden çok belirtme çizgisi ek açıklaması oluşturabilirsiniz.`FreeTextAnnotation`nesneyi kullanma ve bunları belgedeki farklı sayfalara veya konumlara ekleme.