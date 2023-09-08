---
title: XML'den PDFSet Görüntü Yoluna
linktitle: XML'den PDFSet Görüntü Yoluna
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile XML'i PDF'ye dönüştürürken görüntünün yolunu ayarlamak için adım adım kılavuz.
type: docs
weight: 340
url: /tr/net/document-conversion/xml-to-pdfset-image-path/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir XML dosyasını PDF'ye dönüştürürken görüntünün yolunu nasıl ayarlayacağınızı size adım adım anlatacağız. Sağlanan C# kaynak kodunu ayrıntılarıyla anlatacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz. Bu eğitimin sonunda XML'i PDF'ye dönüştürürken görüntünün yolunu kolayca belirleyebilirsiniz.

## 1. Adım: Dosya Yollarını Ayarlayın
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Giriş XML dosyalarının yollarını, kullanılacak görüntüyü ve çıktı PDF dosyasını tanımlayın. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` dosyalarınızı kaydettiğiniz yolla.

## Adım 2: Bir Belge nesnesinin örneğini oluşturun
```csharp
Document doc = new Document();
```
Document nesnesinin bir örneğini oluşturun.

## 3. Adım: Kaynak XML dosyasını bağlayın
```csharp
doc. BindXml(inXml);
```
Kaynak XML dosyasını belgeye bağlar.

## 4. Adım: Görüntü Yolunu Ayarlayın
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
XML'den Görüntü nesnesi referansını kimliğini kullanarak alın ve kullanılacak görüntünün yolunu ayarlayın.

## Adım 5: Ortaya Çıkan PDF Dosyasını Kaydedin
```csharp
doc.Save(outFile);
```
Ortaya çıkan PDF dosyasını belirtilen dizine kaydedin.

### Aspose.PDF for .NET kullanılarak XML to PDFSet Görüntü Yolu için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak XML'i PDF'ye dönüştürürken bir görüntünün yolunu nasıl ayarlayacağımızı öğrendik. Sağlanan adımları izleyerek, kendi XML'den PDF'ye dönüşümlerinizde görüntü yolunu kolayca belirleyebilirsiniz.

### SSS'ler

#### S: XML'i PDF'ye dönüştürürken görüntü yolunu ayarlamanın amacı nedir?

C: XML'i PDF'ye dönüştürürken, görüntü yolunu ayarlamak, XML'de başvurulan görüntünün konumunu belirtmenize olanak tanır. Bu, görüntünün ortaya çıkan PDF belgesinde doğru şekilde görüntülenmesini sağlar.

#### S: Farklı dizinlerdeki görselleri kullanabilir miyim?

 C: Evet, her görsel için doğru dosya yolunu sağlayarak farklı dizinlerdeki görselleri kullanabilirsiniz. Verilen kodda,`inFile` değişken görüntü dosyasının yolunu tutar ve bunu farklı dizinlerdeki görüntüleri işaret edecek şekilde güncelleyebilirsiniz.

#### S: Uzak bir URL'deki görselleri kullanabilir miyim?

C: Evet, yerel dosya yolu yerine URL'yi sağlayarak uzak bir URL'deki görselleri kullanabilirsiniz. Görüntüyü uzak URL'den almak için uygulamanızın internet erişimine sahip olduğundan emin olun.

#### S: Giriş XML dosyası hangi formatta olmalıdır?

C: Giriş XML dosyası, bir kimlik kullanarak görüntüye başvuran bir yapıya sahip olmalıdır. Sağlanan kodda, görüntüye referans vermek için "testImg" kimliği kullanılır.

#### S: PDF'ye birden fazla resim ekleyebilir miyim?

C: Evet, farklı kimlikler kullanarak XML dosyasında bunlara referans vererek ve dosya yollarını buna göre ayarlayarak PDF'ye birden fazla görüntü ekleyebilirsiniz.