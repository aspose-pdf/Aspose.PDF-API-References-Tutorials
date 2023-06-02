---
title: PDF'ye Metin
linktitle: PDF'ye Metin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak metin dosyalarının basit ve verimli bir şekilde PDF'e dönüştürülmesi.
type: docs
weight: 300
url: /tr/net/document-conversion/text-to-pdf/
---

Bu öğretici, Aspose.PDF for .NET kullanarak bir metin dosyasını PDF dosyasına dönüştürme adımlarında size yol gösterecektir. Aspose.PDF, metin biçimlendirmesini ve sunumunu korurken düz metni PDF'ye dönüştürmek için basit ve etkili bir çözüm sunar. Bu dönüşümü gerçekleştirmek için aşağıdaki adımları izleyin.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: Metin dosyasını okuma
 İlk adım, metin dosyasının içeriğini kullanarak okumaktır.`StreamReader` sınıf. Aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Metin dosyasını oku
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` metin dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: PDF belgesini oluşturma
 İkinci adım, bir`Document` son PDF belgesini temsil edecek nesne. Aşağıdaki kodu kullanın:

```csharp
// Belge nesnesi oluşturma
Document doc = new Document();
```

## 3. Adım: Belgeye metin ekleyin
Üçüncü adım, okunan metni PDF belgesinin sayfasına eklemektir. Aşağıdaki kodu kullanın:

```csharp
// Belgeye yeni bir sayfa ekleyin
Page page = doc.Pages.Add();

//Bir TextFragment nesnesi oluşturun ve okunan metni argüman olarak iletin
TextFragment text = new TextFragment(tr.ReadToEnd());

// Metin paragrafını sayfaya ekleyin
page.Paragraphs.Add(text);
```

## 4. Adım: PDF dosyasını kaydetme
Son olarak, istenen yolu ve dosya adını belirterek ortaya çıkan PDF dosyasını kaydedin. Aşağıdaki kodu kullanın:

```csharp
// Ortaya çıkan PDF dosyasını kaydedin
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Ortaya çıkan PDF dosyası için istenen yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Text to PDF için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Kaynak metin dosyasını okuyun
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Boş oluşturucusunu çağırarak bir Document nesnesinin örneğini oluşturun
	Document doc = new Document();

	// Belgenin Sayfalar koleksiyonuna yeni bir sayfa ekleyin
	Page page = doc.Pages.Add();

	// Bir TextFragmet örneği oluşturun ve okuyucu nesnesinden metni yapıcısına bağımsız değişken olarak iletin
	TextFragment text = new TextFragment(tr.ReadToEnd());
	// Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Paragraf koleksiyonuna yeni bir metin paragrafı ekleyin ve TextFragment nesnesini iletin
	page.Paragraphs.Add(text);

	// Ortaya çıkan PDF dosyasını kaydet
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanarak bir metin dosyasını PDF dosyasına dönüştürmeyi öğrendik. Yukarıda verilen adımları takip ederek bu dönüşümü kolaylıkla gerçekleştirebilirsiniz. Metin dosyalarınızı PDF'ye dönüştürmek için bu yöntemi kullanın ve Aspose.PDF'nin esnekliğinin ve kalitesinin keyfini çıkarın.