---
title: DOM Kullanarak HTML Ekle ve Üzerine Yaz
linktitle: DOM Kullanarak HTML Ekle ve Üzerine Yaz
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te DOM kullanarak HTML içeriği eklemeyi öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-text/add-html-using-dom-and-overwrite/
---

Bu eğitim, Aspose.PDF for .NET'te DOM (Belge Nesne Modeli) kullanarak HTML içeriği ekleme sürecinde size rehberlik edecektir. Ek olarak, HTML içeriği için stillerin üzerine nasıl yazılacağını öğreneceksiniz. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
HTML içeriğini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ve çıktı dosyası yolunu ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages` Toplamak. Sağlanan kodda, yeni sayfa değişkene atanır.`page`.

```csharp
Page page = doc.Pages.Add();
```

## 6. Adım: HTML içeriğiyle bir HtmlFragment oluşturun
Bir örneğini oluşturun`HtmlFragment` nesne ve istenen HTML içeriğini sağlayın. Sağlanan kodda, HTML içeriği değişkene atanır.`title`. HTML içeriğini gerektiği gibi değiştirebilirsiniz.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## 7. Adım: HTML içeriği için stillerin üzerine yazın
 HTML içeriğinin stillerinin üzerine yazmak için`TextState` özellikleri`HtmlFragment` nesne. Verilen kodda yazı tipi ailesi "Arial" olarak değiştirilmiş ve yazı tipi boyutu 20 olarak ayarlanmıştır.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## 8. Adım: Kenar boşluğu bilgilerini ayarlayın
Gerekirse HTML parçasının alt ve üst kenar boşluklarını ayarlayın. Sağlanan kodda, alt kenar boşluğu 10 ve üst kenar boşluğu 400 olarak ayarlanmıştır.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## 9. Adım: HtmlFragment'i sayfaya ekleyin
 Ekle`HtmlFragment` sayfanın paragraflar koleksiyonuna itiraz.

```csharp
page.Paragraphs.Add(title);
```

## 10. Adım: PDF belgesini kaydedin
 kullanarak PDF belgesini kaydedin.`Save` yöntemi`Document` nesne. Adım 3'te ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Add HTMLUsing DOMAnd Overwrite using Aspose.PDF for .NET için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini örneklendir
Document doc = new Document();
// PDF dosyasının sayfalar koleksiyonuna bir sayfa ekleyin
Page page = doc.Pages.Add();
// HtmlFragment'i HTML içerikleriyle örnekleyin
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//'Verdana'daki yazı tipi ailesi, 'Arial' olarak sıfırlanacak
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Alt kenar boşluğu bilgilerini ayarla
title.Margin.Bottom = 10;
// Üst kenar boşluğu bilgilerini ayarla
title.Margin.Top = 400;
// Sayfanın paragraf koleksiyonuna HTML Parçası ekleyin
page.Paragraphs.Add(title);
// PDF dosyasını kaydet
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
```

## Çözüm
Aspose.PDF for .NET'te DOM kullanarak HTML içeriğini başarıyla eklediniz ve HTML içeriği için stillerin üzerine yazdınız. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.