---
title: Açıklama Özelliğini Ayarla
linktitle: Açıklama Özelliğini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak Bilgi Özelliğini nasıl ayarlayacağınızı öğrenin. Ek açıklamaları belirtme çizgileri, metin rengi ve bitiş stilleriyle özelleştirin.
type: docs
weight: 130
url: /tr/net/annotations/setcalloutproperty/
---
Aspose.PDF for .NET, C# dilinde PDF belgeleri oluşturmak, işlemek ve dönüştürmek için güçlü bir kitaplıktır. Bu kitaplığın sağladığı özelliklerden biri, PDF belgelerindeki serbest metin ek açıklamaları için belirtme çizgisi özelliklerini ayarlama yeteneğidir. Bu, kullanılarak yapılabilir`FreeTextAnnotation` belirtme çizgileriyle ek açıklamalar oluşturmanıza olanak tanıyan sınıf.

Bu eğitimde, C# dilinde Aspose.PDF for .NET kullanarak serbest metin ek açıklaması için bilgi özelliklerini ayarlama sürecinde size rehberlik edeceğiz. Başlamak için aşağıdaki adımları izleyin.

## Aspose.PDF for .NET'i kurun

 Henüz yapmadıysanız, yapmanız gerekecek[indirmek](https://releases.aspose.com/pdf/net/) ve Aspose Releases'ten veya NuGet paket yöneticisi aracılığıyla Aspose.PDF for .NET'i kurun.

## Yeni bir PDF belgesi oluştur

 kullanarak yeni bir PDF belgesi oluşturun.`Document` Aspose.PDF for .NET tarafından sağlanan sınıf.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Belgeye yeni bir sayfa ekleyin

 kullanarak belgeye yeni bir sayfa ekleyin.`Pages` koleksiyonu`Document` sınıf.

```csharp
Page page = doc.Pages.Add();
```

## Varsayılan görünümü ayarla

Yeni bir tane oluşturarak serbest metin notu için varsayılan görünümü ayarlayın.`DefaultAppearance` nesne ve onun gibi özelliklerini ayarlama`TextColor` Ve`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Belirtme çizgisiyle ücretsiz bir metin notu oluşturun

 kullanarak belirtme çizgisiyle yeni bir serbest metin ek açıklaması oluşturun.`FreeTextAnnotation` sınıf. Yı kur`Intent` mülkiyet`FreeTextIntent.FreeTextCallout` bunun bir ek açıklama olduğunu belirtmek için. Yı kur`EndingStyle` mülkiyet`LineEnding.OpenArrow` belirtme çizgisinin sonundaki okun stilini belirtmek için. Yı kur`Callout` bir dizi özelliği`Point` sayfada belirtme çizgisinin çizilmesi gereken noktaları temsil eden nesneler.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Sayfaya serbest metin açıklamasını ekleyin

 kullanarak sayfaya serbest metin notu ekleyin.`Annotations` koleksiyonu`Page` sınıf.

```csharp
page.Annotations.Add(fta);
```

## Ek açıklamaya metin ekleyin

 ayarlayarak ek açıklamaya metin ekleyin.`RichText` özelliğini biçimlendirilmiş bir XML dizisine dönüştürür. Bu eğitimde, metin rengini kırmızıya ve yazı tipi boyutunu 9'a ayarlıyoruz.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## 8. belgeyi kaydedin

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
