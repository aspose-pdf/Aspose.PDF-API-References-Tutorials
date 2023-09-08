---
title: PDF Dosyasında Satır Sonunu Belirleme
linktitle: PDF Dosyasında Satır Sonunu Belirleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki satır sonlarını nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 130
url: /tr/net/programming-with-text/determine-line-break/
---
Bu eğitim, Aspose.PDF for .NET kullanarak PDF dosyasındaki satır sonlarını belirleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Satır sonlarını belirlemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System.IO;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

## 4. Adım: Yeni bir Belge örneği oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages`Toplamak. Verilen kodda yeni sayfa değişkene atanır.`page`.

```csharp
Page page = doc.Pages.Add();
```

## 6. Adım: Satır sonlarıyla metin parçaları ekleyin
Sayfaya, her biri satır sonları içeren bir paragraf içeren birden çok metin parçası eklemek için bir döngü oluşturun.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Adım 7: PDF belgesini kaydedin ve satır sonu bilgilerini çıkarın
 PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne. Daha sonra satır sonu bilgisini aşağıdaki komutu kullanarak çıkarın.`GetNotifications` İstenilen sayfanın yöntemi.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Aspose.PDF for .NET kullanarak Satır Sonunu Belirleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Çözüm
Aspose.PDF for .NET'i kullanarak bir PDF belgesinde satır sonlarını başarıyla belirlediniz. Satır sonu bilgisi çıkarıldı ve bir metin dosyasına kaydedildi.

### SSS'ler

#### S: Bu eğitimin ana odağı nedir?

C: Bu eğitim, Aspose.PDF for .NET kütüphanesini kullanarak bir PDF dosyasındaki satır sonlarını belirleme sürecinde size rehberlik etmeye odaklanmıştır. Sağlanan C# kaynak kodu, bunu başarmak için gerekli adımları gösterir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmalıyım?

C: Satır sonlarını belirlemek istediğiniz kod dosyasında, dosyanın başında aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### S: Belge dizinini nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Yeni bir Belge örneğini nasıl oluşturabilirim?

 C: 4. Adımda yeni bir örnek oluşturacaksınız.`Document` sağlanan kodu kullanarak nesne.

#### S: Belgeye nasıl sayfa eklerim?

 C: 5. Adımda belgeye yeni bir sayfa ekleyeceksiniz.`Add` yöntemi`Pages` Toplamak.

#### S: Satır sonları olan metin parçalarını nasıl eklerim?

C: 6. Adımda, sayfaya her biri satır sonları olan bir paragraf içeren birden çok metin parçası eklemek için bir döngü oluşturacaksınız.

#### S: PDF belgesini nasıl kaydederim ve satır sonu bilgilerini nasıl çıkarırım?

 C: 7. Adımda, PDF belgesini aşağıdaki komutu kullanarak kaydedeceksiniz:`Save` yöntemi`Document` nesne. Daha sonra satır sonu bilgisini kullanarak çıkaracaksınız.`GetNotifications` İstediğiniz sayfanın yöntemini seçin ve bir metin dosyasına kaydedin.

#### S: Çıkarılan satır sonu bilgilerinin amacı nedir?

C: Çıkarılan satır sonu bilgileri, PDF belgesinde bulunan satır sonları ve bildirimler hakkında ayrıntılı bilgi sağlar. Bu, belgedeki metin ve paragrafların nasıl yapılandırıldığını analiz etmek ve anlamak için yararlı olabilir.

#### S: Bu eğitimden çıkan ana sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET kullanarak bir PDF belgesindeki satır sonlarını nasıl belirleyeceğinizi öğrendiniz. Bu bilgiyi, PDF dosyalarından satır sonu bilgilerini programlı olarak çıkarmak ve analiz etmek için kullanabilirsiniz.