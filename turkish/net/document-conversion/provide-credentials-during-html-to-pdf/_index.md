---
title: HTML'den PDF'ye Dönüştürme Sırasında Kimlik Bilgilerini Sağlayın
linktitle: HTML'den PDF'ye Dönüştürme Sırasında Kimlik Bilgilerini Sağlayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile kimlik bilgilerini sağlayarak HTML'yi PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 240
url: /tr/net/document-conversion/provide-credentials-during-html-to-pdf/
---

Bu öğreticide, Aspose.PDF for .NET kullanarak güvenli bir URL'ye erişirken kimlik bilgilerini sağlarken bir HTML dosyasını PDF'ye dönüştürme sürecinde size yol göstereceğiz. Aşağıdaki adımları izleyerek, uygun kimlik bilgilerini kullanarak HTML içeriğini PDF'ye dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgi.
- Sisteminizde kurulu .NET için Aspose.PDF kitaplığı.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: Güvenli HTML içeriği getirin
Bu adımda, uygun kimlik bilgilerini kullanarak bir URL'den güvenli HTML içeriği alacağız. Aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// URL için bir istek oluşturun.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Sunucu için gerekiyorsa, kimlik bilgilerini ayarlayın.
request.Credentials = CredentialCache.DefaultCredentials;
// Yanıtı alın.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Sunucu tarafından döndürülen içeriği içeren akışı alın.
Stream dataStream = response. GetResponseStream();
// Kolay erişim için bir StreamReader kullanarak akışı açın.
StreamReader reader = new StreamReader(dataStream);
// İçeriği okuyun.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` ortaya çıkan PDF dosyasını kaydetmek istediğiniz gerçek dizinle.

## 2. Adım: Kimlik bilgilerini sağlayarak HTML'yi PDF'ye dönüştürün
Şimdi, alınan HTML içeriğini yükleyeceğiz ve uygun kimlik bilgilerini sağlarken PDF formatına dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// HTML dosyasını yükleyin
Document pdfDocument = new Document(stream, options);
```

## 3. Adım: Ortaya çıkan PDF dosyasını kaydetme
Son olarak, ortaya çıkan PDF dosyasını kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Ortaya çıkan PDF dosyasını kaydedin
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Yukarıdaki kod, ortaya çıkan PDF dosyasını dosya adıyla kaydeder.`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Aspose.Words for .NET kullanarak HTML'den PDF'e Kimlik Bilgilerini Sağlamak için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// URL için bir istek oluşturun.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Sunucu gerektiriyorsa, kimlik bilgilerini ayarlayın.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Yanıtı alın.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Sunucu tarafından döndürülen içeriği içeren akışı alın.
	Stream dataStream = response.GetResponseStream();
	// Kolay erişim için bir StreamReader kullanarak akışı açın.
	StreamReader reader = new StreamReader(dataStream);
	// İçeriği okuyun.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// HTML dosyasını yükle
	Document pdfDocument = new Document(stream, options);
	// Ortaya çıkan dosyayı kaydet
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak güvenli bir URL'ye erişirken kimlik bilgilerini sağlarken bir HTML dosyasını PDF'ye dönüştürme sürecini adım adım ele aldık. Yukarıda özetlenen talimatları izleyerek, doğru kimlik bilgilerini sağlarken HTML içeriğini başarıyla PDF'ye dönüştürebileceksiniz.