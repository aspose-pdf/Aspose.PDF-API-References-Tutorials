---
title: HTML'den PDF'ye Dönüştürme Sırasında Kimlik Bilgilerini Sağlayın
linktitle: HTML'den PDF'ye Dönüştürme Sırasında Kimlik Bilgilerini Sağlayın
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile kimlik bilgileri sağlayarak HTML'yi PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 240
url: /tr/net/document-conversion/provide-credentials-during-html-to-pdf/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak güvenli bir URL'ye erişirken kimlik bilgileri sağlarken bir HTML dosyasını PDF'ye dönüştürme sürecinde size yol göstereceğiz. Aşağıdaki adımları takip ederek, uygun kimlik bilgilerini kullanarak HTML içeriğini PDF'ye dönüştürebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: Güvenli HTML içeriğini alın
Bu adımda, uygun kimlik bilgilerini kullanarak bir URL'den güvenli HTML içeriğini getireceğiz. Aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// URL için bir istek oluşturun.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Sunucu için gerekiyorsa kimlik bilgilerini ayarlayın.
request.Credentials = CredentialCache.DefaultCredentials;
// Yanıtı alın.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Sunucu tarafından döndürülen içeriği içeren akışı alın.
Stream dataStream = response. GetResponseStream();
// Kolay erişim için akışı StreamReader kullanarak açın.
StreamReader reader = new StreamReader(dataStream);
// İçeriği okuyun.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` ortaya çıkan PDF dosyasını kaydetmek istediğiniz gerçek dizinle.

## Adım 2: Kimlik bilgilerini sağlayarak HTML'yi PDF'ye dönüştürün
Şimdi alınan HTML içeriğini yükleyeceğiz ve uygun kimlik bilgilerini sağlayarak PDF formatına dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// HTML dosyasını yükleyin
Document pdfDocument = new Document(stream, options);
```

## 3. Adım: Ortaya çıkan PDF dosyasını kaydetme
Son olarak ortaya çıkan PDF dosyasını kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Ortaya çıkan PDF dosyasını kaydedin
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Yukarıdaki kod, ortaya çıkan PDF dosyasını dosya adıyla kaydeder.`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Aspose.PDF for .NET kullanarak HTML'den PDF'ye Dönüştürme Sırasında Kimlik Bilgilerini Sağlama için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// URL için bir istek oluşturun.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Sunucu gerektiriyorsa kimlik bilgilerini ayarlayın.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Yanıtı alın.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Sunucu tarafından döndürülen içeriği içeren akışı alın.
	Stream dataStream = response.GetResponseStream();
	// Kolay erişim için akışı StreamReader kullanarak açın.
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
Bu eğitimde, Aspose.PDF for .NET kullanarak güvenli bir URL'ye erişirken kimlik bilgileri sağlarken bir HTML dosyasını PDF'ye dönüştürmenin adım adım sürecini ele aldık. Yukarıda özetlenen talimatları izleyerek, doğru kimlik bilgilerini sağlarken HTML içeriğini başarıyla PDF'ye dönüştürebileceksiniz.

### SSS'ler

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin C# uygulamalarında PDF belgeleriyle çalışmasını sağlayan güçlü bir kitaplıktır. HTML'den PDF'ye dönüştürme de dahil olmak üzere çok çeşitli işlevler sunar.

#### S: Bir URL'den güvenli HTML içeriğini nasıl alabilirim?

 C: Bir URL'den güvenli HTML içeriği almak için`WebRequest` C#'ta sınıf. kullanarak uygun kimlik bilgilerini ayarladığınızdan emin olun.`Credentials` mülk.

#### S: Bu eğitimin önkoşulları nelerdir?

C: Eğiticiye devam etmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

#### S: Aspose.PDF for .NET, HTML'yi PDF'ye dönüştürürken harici kaynakları nasıl yönetir?

 C: Aspose.PDF for .NET şunları sağlar:`HtmlLoadOptions`HTML'den PDF'ye dönüştürme sırasında harici kaynakları yönetmek için sınıf. Harici kaynak kimlik bilgilerini aşağıdaki komutu kullanarak ayarlayabilirsiniz:`ExternalResourcesCredentials` mülk.

#### S: Ortaya çıkan PDF dosyasının dosya adını özelleştirebilir miyim?

 C: Evet, PDF belgesini kaydeden kodu değiştirerek ortaya çıkan PDF dosyasının dosya adını özelleştirebilirsiniz. İstediğiniz dosya adını değiştirmeniz yeterlidir.`pdfDocument.Save()` yöntem.