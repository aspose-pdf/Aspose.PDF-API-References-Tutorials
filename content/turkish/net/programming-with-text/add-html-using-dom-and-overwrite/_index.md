---
title: DOM ve PDF Üzerine Yazma Kullanarak HTML Ekleme
linktitle: DOM Kullanarak HTML Ekleme ve Üzerine Yazma
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te DOM ve PDF üzerine yazma kullanarak HTML içeriğinin nasıl ekleneceğini öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Bu eğitim, Aspose.PDF for .NET'te DOM (Document Object Model) kullanarak HTML içeriği ekleme sürecinde size rehberlik edecektir. Ayrıca, HTML içeriği için stilleri nasıl geçersiz kılacağınızı öğreneceksiniz. Sağlanan C# kaynak kodu gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
HTML içeriğini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Adım 3: Belge dizinini ve çıktı dosyası yolunu ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 4: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesneyi oluşturun:

```csharp
Document doc = new Document();
```

## Adım 5: Belgeye bir sayfa ekleyin
 Belgeye yeni bir sayfa eklemek için şunu kullanın:`Add` yöntemi`Pages`koleksiyon. Sağlanan kodda, yeni sayfa değişkene atanır`page`.

```csharp
Page page = doc.Pages.Add();
```

## Adım 6: HTML içeriğiyle bir HtmlFragment oluşturun
 Bir örnek oluştur`HtmlFragment` nesne ve istenen HTML içeriğini sağlayın. Sağlanan kodda, HTML içeriği değişkene atanır`title`HTML içeriğini ihtiyacınıza göre değiştirebilirsiniz.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Adım 7: HTML içeriği için stilleri üzerine yaz
 HTML içeriğinin stillerini geçersiz kılmak için şunu değiştirebilirsiniz:`TextState` özellikleri`HtmlFragment` nesne. Sağlanan kodda, yazı tipi ailesi "Arial" olarak değiştirildi ve yazı tipi boyutu 20 olarak ayarlandı.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Adım 8: Marj bilgilerini ayarlayın
Gerekirse HTML parçasının alt ve üst kenar boşluklarını ayarlayın. Sağlanan kodda, alt kenar boşluğu 10 olarak ve üst kenar boşluğu 400 olarak ayarlanmıştır.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Adım 9: HtmlFragment'ı sayfaya ekleyin
 Ekle`HtmlFragment` sayfanın paragraf koleksiyonuna nesne.

```csharp
page.Paragraphs.Add(title);
```

## Adım 10: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin`Save` yöntemi`Document` nesne. Adım 3'te ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak DOMA ve Üzerine Yazma kullanarak HTML Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini örnekle
Document doc = new Document();
// PDF dosyasının sayfa sayfa koleksiyonuna bir sayfa ekle
Page page = doc.Pages.Add();
// HtmlFragment'ı HTML içerikleriyle örneklendirin
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//'Verdana' font ailesi 'Arial' olarak sıfırlanacak
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Alt kenar boşluğu bilgilerini ayarla
title.Margin.Bottom = 10;
// Üst kenar boşluğu bilgilerini ayarlayın
title.Margin.Top = 400;
// Sayfanın paragraf koleksiyonuna HTML Parçası Ekle
page.Paragraphs.Add(title);
// PDF dosyasını kaydet
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
```

## Çözüm
Aspose.PDF for .NET'te DOM kullanarak HTML içeriğini başarıyla eklediniz ve HTML içeriği için stilleri üzerine yazdınız. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS

#### S: Bu eğitimin odak noktası nedir?

A: Bu eğitim, .NET için Aspose.PDF'de Belge Nesne Modeli'ni (DOM) kullanarak bir PDF belgesine HTML içeriği ekleme sürecinde size yol göstermek için tasarlanmıştır. Ayrıca, HTML içeriği için stilleri nasıl geçersiz kılacağınızı öğreneceksiniz, böylece görünümünü özelleştirebilirsiniz. Eğitim, gerekli adımları göstermek için C# kaynak kodu parçacıkları sağlar.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

A: HTML içeriği eklemeyi planladığınız kod dosyasında, dosyanın başına aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini ve çıktı dosyası yolunu nasıl belirtirim?

 A: Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile.

#### S: Belge nesnesi nasıl oluştururum?

 A: 4. Adımda yeni bir örnek oluşturacaksınız`Document` Aşağıdaki kod satırını kullanarak nesneyi oluşturun:

```csharp
Document doc = new Document();
```

#### S: Belgeye nasıl sayfa eklerim?

 A: 5. Adımda, belgeye yeni bir sayfa ekleyeceksiniz`Add` yöntemi`Pages` koleksiyon:

```csharp
Page page = doc.Pages.Add();
```

#### S: DOM kullanarak HTML içeriğini nasıl ayarlayabilirim?

 A: 6. Adımda bir`HtmlFragment` nesneyi seçin ve istediğiniz HTML içeriğini ona atayın. HTML içeriği değişkene atanır`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### S: HTML içeriğinin stillerini nasıl geçersiz kılabilirim?

 A: 7. Adımda, HTML içeriğinin stillerini değiştirerek üzerine yazacaksınız.`TextState` özellikleri`HtmlFragment` nesne. Örneğin, yazı tipi ailesini "Arial" olarak değiştirebilir ve yazı tipi boyutunu 20 olarak ayarlayabilirsiniz:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### S: HTML içeriğinin kenar boşluklarını ayarlayabilir miyim?

C: Evet, 8. Adımda HTML parçasının alt ve üst kenar boşluklarını gerektiği gibi ayarlayabilirsiniz:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### S: HtmlFragment'ı PDF belgesine nasıl eklerim?

 A: 9. Adımda şunları ekleyeceksiniz:`HtmlFragment` nesne (`title`) sayfanın paragraf koleksiyonuna:

```csharp
page.Paragraphs.Add(title);
```

#### S: Ortaya çıkan PDF belgesini nasıl kaydedebilirim?

 A: HTML içeriğini ekledikten ve stillerini özelleştirdikten sonra,`Save` yöntemi`Document` PDF belgesini kaydetmek için nesne:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, .NET için Aspose.PDF'de Belge Nesne Modeli'ni (DOM) kullanarak HTML içeriğini nasıl dahil edeceğinizi başarıyla öğrendiniz. Ayrıca, ortaya çıkan PDF belgesindeki HTML içeriğinin görünümünü özelleştirmek için stilleri geçersiz kılma yeteneği kazandınız.