---
title: Kelimeleri Çiz
linktitle: Kelimeleri Çiz
second_title: Aspose.PDF for .NET API Referansı
description: Bu makale, Aspose.PDF for .NET'in Strike Out Words özelliğinin kullanımı için adım adım kılavuz ve açıklamalar içeren adım adım bir kılavuz sunmaktadır.
type: docs
weight: 150
url: /tr/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET, PDF dosyalarını oluşturmak, değiştirmek ve dönüştürmek için çeşitli özellikler sağlayan bir PDF belge işleme ve işleme kitaplığıdır. Aspose.PDF'nin sağladığı kullanışlı özelliklerden biri, C# kaynak kodunu kullanarak bir PDF belgesindeki sözcüklerin veya tümcelerin üstünü çizebilme yeteneğidir. Bu yazıda, Aspose.PDF for .NET kullanarak kelimelerin üstünün nasıl çizileceğine dair adım adım bir kılavuz sunacağız.

## PDF belgesini yükleme
İlk adım, değiştirmek istediğiniz PDF belgesini yüklemektir. Bu eğitimde, "BELGE DİZİNİNİZ" klasöründen "input.pdf" adlı bir PDF belgesi yükleyeceğiz. 

```
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Metin parçalarını arama
PDF belgesindeki belirli sözcüklerin veya tümceciklerin üstünü çizmek için önce bunları aramanız gerekir. Aspose.PDF, PDF belgesinde belirli bir metin parçasını aramak için kullanılabilecek bir TextFragmentAbsorber sınıfı sağlar.

```
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Yukarıdaki kodda, PDF belgesindeki "Estoque" metin parçasını arıyoruz. Üstünü çizmek istediğiniz başka bir kelimeyi veya tümceciği aramak için bunu değiştirebilirsiniz.

## Metin parçalarının üzerinin çizilmesi
Metin parçalarını bulduktan sonraki adım, bunların üstünü çizmek. Aspose.PDF, metin parçası için üzeri çizili not oluşturmak için kullanılabilecek bir StrikeOutAnnotation sınıfı sağlar. 

```
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Yukarıdaki kodda, bulduğumuz her metin parçası için üstü çizili bir not oluşturuyoruz. Üstü çizili ek açıklamanın opaklığını, kenarlığını ve rengini de ayarlıyoruz.

## Değiştirilen PDF belgesini kaydetme
Metin parçalarının üzerini çizdikten sonra değiştirilen belgeyi kaydedin.

```
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Strike Out Words için örnek kaynak kodu


```csharp

            
            
            // Belgeler dizininin yolu.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Belgeyi aç
            Document document = new Document(dataDir + "input.pdf");

            // Belirli bir metin parçasını aramak için TextFragment Absorber örneği oluşturun
            Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
            // PDF belgesinin sayfalarını yineleyin
            for (int i = 1; i <= document.Pages.Count; i++)
            {
                // PDF belgesinin ilk sayfasını alın
                Page page = document.Pages[1];
                page.Accept(textFragmentAbsorber);
            }

            // Emilmiş metin koleksiyonu oluşturma
            Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

            // Yukarıdaki koleksiyonu yineleyin
            for (int j = 1; j <= textFragmentCollection.Count; j++)
            {
                Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

                // TextFragment nesnesinin dikdörtgen boyutlarını alın
                Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
                            (float)textFragment.Position.XIndent,
                            (float)textFragment.Position.YIndent,
                            (float)textFragment.Position.XIndent +
                            (float)textFragment.Rectangle.Width,
                            (float)textFragment.Position.YIndent +
                            (float)textFragment.Rectangle.Height);

                // StrikeOut Annotation örneğini başlat
                StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
                // Açıklama için opaklığı ayarla
                strikeOut.Opacity = .80f;
                // Ek açıklama örneği için sınırı ayarlayın
                strikeOut.Border = new Border(strikeOut);
                // Ek açıklamanın rengini ayarlayın
                strikeOut.Color = Aspose.Pdf.Color.Red;
                // TextFragment ek açıklamalar koleksiyonuna ek açıklama ekleyin
                textFragment.Page.Annotations.Add(strikeOut);
            }
            dataDir = dataDir + "StrikeOutWords_out.pdf";
            document.Save(dataDir);


        
```
