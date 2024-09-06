---
title: HTML'den PDF'e Geçiş Sırasında Kimlik Bilgilerini Sağlayın
linktitle: HTML'den PDF'e Geçiş Sırasında Kimlik Bilgilerini Sağlayın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak HTML'yi PDF'ye nasıl dönüştüreceğinizi öğrenin. Belge oluşturmayı kolaylaştırmak isteyen geliştiriciler için mükemmeldir.
type: docs
weight: 240
url: /tr/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## giriiş

Yazılım geliştirme dünyasında, HTML'yi PDF'ye dönüştürmek yaygın bir gerekliliktir. Raporlar, faturalar veya başka herhangi bir belge oluşturuyor olun, bu görevi halletmek için güvenilir bir kütüphaneye sahip olmak size çok fazla zaman ve emek kazandırabilir. Geliştiricilerin PDF belgelerini kolaylıkla oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan güçlü bir kütüphane olan Aspose.PDF for .NET'e girin. Bu eğitimde, güvenli erişim için kimlik bilgileri sağlarken HTML'yi PDF'ye dönüştürmek için Aspose.PDF'yi kullanma sürecinde size yol göstereceğiz. O halde, kodlama şapkanızı alın ve başlayalım!

## Ön koşullar

Başlamadan önce, yerinde olması gereken birkaç şey var:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Bu bizim geliştirme ortamımız olacak.
2.  .NET için Aspose.PDF: Kütüphaneyi şu adresten indirebilirsiniz:[web sitesi](https://releases.aspose.com/pdf/net/) Eğer önce denemek isterseniz, ayrıca bir tane alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/).
3. Temel C# Bilgisi: C# programlamaya aşina olmak örnekleri daha iyi anlamanıza yardımcı olacaktır.
4. İnternet Erişimi: HTML içeriğini bir URL'den alacağımız için aktif bir internet bağlantınız olduğundan emin olun.

## Paketleri İçe Aktar

Aspose.PDF'e başlamak için gerekli paketleri projenize aktarmanız gerekir. Bunu şu şekilde yapabilirsiniz:

1. Visual Studio projenizi açın.
2. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF" dosyasını arayın ve en son sürümü yükleyin.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
Artık her şeyi ayarladığımıza göre, HTML'yi kimlik bilgileriyle PDF'ye dönüştürme sürecini yönetilebilir adımlara bölelim.

## Adım 1: Belge Dizininizi Ayarlayın

HTML'yi PDF'ye dönüştürmeden önce çıktı PDF'imizin nereye kaydedileceğini belirtmemiz gerekir. Bu, belgeler dizinine bir yol tanımlayarak yapılır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızı kaydetmek istediğiniz gerçek yol ile. Bu, masaüstünüzdeki bir klasör veya sisteminizdeki herhangi bir konum olabilir.

## Adım 2: Bir Web İsteği Oluşturun

 Sonra, belirli bir URL'den HTML içeriğini almak için bir istek oluşturmamız gerekiyor. Burada şunu kullanacağız:`WebRequest` sınıf.

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

Burada, dönüştürmek istediğimiz HTML'yi içeren URL'ye bir istek oluşturuyoruz. URL'yi kullanmayı düşündüğünüz URL ile değiştirdiğinizden emin olun.

## Adım 3: Kimlik Bilgilerini Ayarlayın (Gerekirse)

Sunucunun içeriğe erişmek için kimlik bilgilerine ihtiyacı varsa, bunları ayarlamamız gerekir. Bu, şu şekilde yapılır:`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

 Bu satır, isteğin geçerli kullanıcının varsayılan kimlik bilgilerini kullanmasını sağlar. Belirli kimlik bilgileri sağlamanız gerekiyorsa, yeni bir tane oluşturabilirsiniz`NetworkCredential` nesne.

## Adım 4: Yanıtı Alın

Artık isteğimizi ayarladığımıza göre, sunucudan yanıtı alma zamanı geldi.

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

Bu satır isteği gönderir ve sunucunun yanıt vermesini bekler. Her şey yolunda giderse, ihtiyacımız olan HTML içeriğini alırız.

## Adım 5: Yanıt Akışını Okuyun

 Yanıtı aldıktan sonra, sunucu tarafından döndürülen içeriği okumamız gerekir. Bu, bir`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

 Burada, yanıt akışının tüm içeriğini şu dize değişkenine okuyoruz:`responseFromServer`Kaynakları serbest bırakmak için okuyucuyu ve akışı kapatmayı unutmayın.

## Adım 6: HTML'yi PDF'ye dönüştürün

Şimdi heyecan verici kısım geliyor! HTML içeriğini Aspose.PDF kullanarak PDF belgesine dönüştüreceğiz.

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://Benim.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

Bu adımda bir tane oluşturuyoruz`MemoryStream` HTML içeriğinden ve kurulumdan`HtmlLoadOptions`Bu, HTML'nin başvurabileceği herhangi bir harici kaynak (resimler veya stil sayfaları gibi) için temel URL'yi belirtmemize olanak tanır.

## Adım 7: PDF Belgesini Kaydedin

Son olarak oluşturulan PDF belgesini belirtilen dizine kaydetmemiz gerekiyor.

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Bu satır PDF dosyasını şu adla kaydeder:`ProvideCredentialsDuringHTMLToPDF_out.pdf` daha önce belirttiğimiz dizinde.

## Çözüm

Ve işte oldu! Aspose.PDF for .NET kullanarak HTML'yi PDF'ye başarıyla dönüştürdünüz ve güvenli erişim için kimlik bilgileri sağladınız. Bu güçlü kütüphane PDF belgelerini yönetmeyi kolaylaştırır ve sadece birkaç satır kodla HTML içeriğinden profesyonel görünümlü PDF'ler üretebilirsiniz. 

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF belgeleri oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi nasıl yüklerim?
 Aspose.PDF'yi Visual Studio'daki NuGet Paket Yöneticisi aracılığıyla yükleyebilir veya şu adresten indirebilirsiniz:[web sitesi](https://releases.aspose.com/pdf/net/).

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
Evet, Aspose satın almadan önce kütüphaneyi değerlendirebilmeniz için ücretsiz deneme sürümü sunuyor.

### Aspose.PDF ile hangi tür belgeler oluşturabilirim?
Aspose.PDF'i kullanarak raporlar, faturalar ve formlar dahil olmak üzere çok çeşitli belgeler oluşturabilirsiniz.

### Aspose.PDF için desteği nerede bulabilirim?
 Destek bulabilir ve soru sorabilirsiniz.[Aspose destek forumu](https://forum.aspose.com/c/pdf/10).