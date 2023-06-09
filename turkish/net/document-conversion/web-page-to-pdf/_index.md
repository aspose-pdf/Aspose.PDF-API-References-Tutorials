---
title: Web Sayfasından PDF'e
linktitle: Web Sayfasından PDF'e
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak web sayfasını PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 320
url: /tr/net/document-conversion/web-page-to-pdf/
---

Bu eğitimde, Aspose.PDF for .NET kitaplığını kullanarak bir web sayfasını PDF'ye nasıl dönüştüreceğiniz konusunda size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz. Bu eğitimin sonunda, web sayfalarını zahmetsizce PDF belgelerine dönüştürebileceksiniz.

## giriiş
Web sayfalarını PDF formatına dönüştürmek, birçok uygulamada ortak bir gerekliliktir. Web içeriğini PDF'ye dönüştürerek, orijinal web sayfasının düzenini, biçimlendirmesini ve görüntülerini kolayca koruyabilirsiniz. Aspose.PDF for .NET, bu dönüştürmeyi verimli ve doğru bir şekilde yapmanızı sağlayan güçlü bir kitaplıktır.

## Gereksinimler
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Makinenizde yüklü Visual Studio
- Aspose.PDF for .NET library (resmi Aspose web sitesinden indirebilirsiniz)
- Temel C# programlama bilgisi


## 1. Adım: Belge Dizinini Tanımlayın
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` oluşturulan PDF dosyasını kaydetmek istediğiniz yolla.

## 2. Adım: Bir Web İsteği Oluşturun
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Bir web isteği nesnesi oluşturun ve dönüştürmek istediğiniz web sayfasının URL'sini belirtin. URL'yi istediğiniz herhangi bir web sayfasıyla değiştirebilirsiniz.

## 3. Adım: Web Yanıtını Alın
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Web isteğini gönderin ve yanıtı sunucudan alın.

## 4. Adım: Web İçeriğini Okuyun
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 kullanarak web sayfasının içeriğini okuyun.`StreamReader` ve içinde saklayın`responseFromServer` değişken.

## Adım 5: HTML'yi PDF'ye Dönüştürün
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Oluşturmak`MemoryStream` web sayfası içeriğini yüklemek için nesne. Ardından, örneğini oluşturun`HtmlLoadOptions` ve web sayfasının temel URL'sini iletin. Ardından, bir`Document` yüklenen akışı ve HTML yükleme seçeneklerini kullanarak nesne. Yı kur`IsLandscape` mülkiyet`true` PDF'nin yatay yönde olmasını istiyorsanız. Son olarak, PDF belgesini belirtilen dizine kaydedin

.

## 6. Adım: İstisnaları İşleyin
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Dönüştürme işlemi sırasında oluşabilecek istisnaları yakalayın ve hata mesajını görüntüleyin.

### Aspose.PDF for .NET kullanarak Web Sayfasını PDF'e dönüştürmek için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// URL için bir istek oluşturun.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Sunucu gerektiriyorsa, kimlik bilgilerini ayarlayın.
	request.Credentials = CredentialCache.DefaultCredentials;
	// İstek zaman aşımına uğramadan önce milisaniye cinsinden zaman aşımı
	// İstek.Zaman Aşımı = 100;

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
	HtmlLoadOptions options = new HtmlLoadOptions("https:// tr.wikipedia.org/wiki/");


	// HTML dosyasını yükle
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Çıktıyı PDF formatında kaydedin
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kitaplığı kullanılarak bir web sayfasının PDF'ye nasıl dönüştürüleceğini öğrendik. Sağlanan C# kaynak kodunu açıklayan adım adım kılavuzu inceledik. Bu talimatları izleyerek, web sayfasını PDF'e dönüştürme işlevini kendi .NET uygulamalarınıza kolayca entegre edebilirsiniz.