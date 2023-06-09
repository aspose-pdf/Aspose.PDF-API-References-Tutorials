---
title: Hizalamayı Tanımla
linktitle: Hizalamayı Tanımla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizde metin hizalamasını kolayca nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 70
url: /tr/net/programming-with-stamps-and-watermarks/define-alignment/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinde metin hizalamasını nasıl ayarlayacağınız konusunda size adım adım yol göstereceğiz. PDF belgesinde ortalanmış bir metin damgası oluşturmak için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Giriş dosyasıyla bir Belge nesnesi oluşturun
Document doc = new Document(dataDir + "DefineAlignment.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Hizalamayı tanımlama

Artık PDF belgesini yüklediğinize göre, metin damgasının hizalamasını ayarlayabilirsiniz. İşte nasıl:

```csharp
// Örnek dizeyle bir FormattedText nesnesi oluşturun
FormattedText text = new FormattedText("This");

// FormattedText'e yeni bir metin satırı ekleyin
text.AddNewLineText("is an example");
text.AddNewLineText("Center aligned");
text.AddNewLineText("Text buffer");
text.AddNewLineText("Subject");

// FormattedText kullanarak bir TextStamp nesnesi oluşturun
TextStamp stamp = new TextStamp(text);

// Metin arabelleğinin yatay hizalamasını ortalanmış olarak belirtin
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Metin arabelleğinin dikey hizalamasını ortalanmış olarak belirtin
stamp.VerticalAlignment = VerticalAlignment.Center;

// TextStamp'taki metnin yatay hizalamasını ortalanmış olarak belirtin
stamp.TextAlignment = HorizontalAlignment.Center;

// Arabellek nesnesi için üst kenar boşluğunu ayarla
stamp. TopMargin = 20;

// Damga nesnesini belgenin ilk sayfasına ekleyin
doc.Pages[1].AddStamp(stamp);
```

Yukarıdaki kod, içeriği belirtmek için FormattedText sınıfını kullanarak ortalanmış bir metin arabelleği oluşturur ve metin arabelleğinin yatay ve dikey hizalamasını ayarlar.

## 4. Adım: Çıktı belgesini kaydedin

Metin damgası hizalamasını ayarladıktan sonra, değiştirilen PDF belgesini kaydedebilirsiniz. İşte nasıl:

```csharp
// Güncellenen belgeyi kaydedin
doc.Save(dataDir);
```

Yukarıdaki kod, düzenlenen PDF belgesini belirtilen dizine kaydeder.

### Aspose.PDF for .NET kullanarak Hizalamayı Tanımla için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Girdi dosyasıyla Belge nesnesini somutlaştırın
Document doc = new Document(dataDir+ "DefineAlignment.pdf");

// Örnek dize ile FormattedText nesnesini örnekleyin
FormattedText text = new FormattedText("This");

// FormattedText'e yeni metin satırı ekleyin
text.AddNewLineText("is sample");
text.AddNewLineText("Center Aligned");
text.AddNewLineText("TextStamp");
text.AddNewLineText("Object");

// FormattedText kullanarak TextStamp nesnesi oluşturun
TextStamp stamp = new TextStamp(text);

// Metin damgasının Yatay Hizalamasını Ortaya hizalanmış olarak belirtin
stamp.HorizontalAlignment = HorizontalAlignment.Center;

// Metin damgasının Dikey Hizalamasını Ortaya hizalanmış olarak belirtin
stamp.VerticalAlignment = VerticalAlignment.Center;

// TextStamp'ın Metin Yatay Hizalamasını Ortaya hizalanmış olarak belirtin
stamp.TextAlignment = HorizontalAlignment.Center;

// Damga nesnesi için üst kenar boşluğunu ayarla
stamp.TopMargin = 20;

// Damga nesnesini belgenin ilk sayfasına ekleyin
doc.Pages[1].AddStamp(stamp);
dataDir = dataDir + "StampedPDF_out.pdf";

// Güncellenen belgeyi kaydet
doc.Save(dataDir);
Console.WriteLine("\nAlignment defined successfully for text stamp.\nFile saved at " + dataDir);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinde metin hizalamasını nasıl ayarlayacağınızı öğrendiniz. Artık bu bilgiyi, PDF belgelerinizde farklı hizalamalara sahip metin damgaları oluşturmak için uygulayabilirsiniz.
