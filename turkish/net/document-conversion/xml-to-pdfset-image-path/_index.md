---
title: XML'den PDFSet Görüntü Yoluna
linktitle: XML'den PDFSet Görüntü Yoluna
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile XML'i PDF'ye dönüştürürken görüntünün yolunu ayarlamak için adım adım kılavuz.
type: docs
weight: 340
url: /tr/net/document-conversion/xml-to-pdfset-image-path/
---
Bu eğitimde, bir XML dosyasını Aspose.PDF for .NET kullanarak PDF'ye dönüştürürken görüntünün yolunu nasıl ayarlayacağınızı adım adım anlatacağız. Sağlanan C# kaynak kodunu detaylandıracağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz. Bu eğitimin sonunda, XML'i PDF'ye dönüştürürken bir görüntünün yolunu kolayca belirleyebilirsiniz.

## 1. Adım: Dosya Yollarını Ayarlayın
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Giriş XML dosyalarının, kullanılacak görüntünün ve çıktı PDF dosyasının yollarını tanımlayın. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` dosyalarınızı kaydettiğiniz yolla.

## 2. Adım: Bir Document nesnesinin örneğini oluşturun
```csharp
Document doc = new Document();
```
Belge nesnesinin bir örneğini oluşturun.

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
Kimliğini kullanarak XML'den Görüntü nesnesi referansını alın ve kullanılacak görüntünün yolunu ayarlayın.

## 5. Adım: Elde Edilen PDF Dosyasını Kaydedin
```csharp
doc.Save(outFile);
```
Ortaya çıkan PDF dosyasını belirtilen dizine kaydedin.

### Aspose.PDF for .NET kullanarak XML to PDFSet Image Path için örnek kaynak kodu

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
Bu eğitimde, Aspose.PDF kitaplığı .NET'i kullanarak XML'i PDF'ye dönüştürürken bir görüntünün yolunu nasıl ayarlayacağımızı öğrendik. Sağlanan adımları izleyerek, kendi XML'den PDF'e dönüştürmelerinizde görüntü yolunu kolayca belirleyebilirsiniz.

### SSS

#### S: XML'i PDF'ye dönüştürürken görüntü yolunu belirlemenin amacı nedir?

C: XML'i PDF'ye dönüştürürken, görüntü yolunu ayarlamak, XML'de başvurulan bir görüntünün konumunu belirtmenize olanak tanır. Bu, görüntünün ortaya çıkan PDF belgesinde doğru şekilde görüntülenmesini sağlar.

#### S: Farklı dizinlerdeki görüntüleri kullanabilir miyim?

 C: Evet, her resim için doğru dosya yolunu sağlayarak farklı dizinlerdeki resimleri kullanabilirsiniz. Sağlanan kodda,`inFile` değişkeni, görüntü dosyasının yolunu tutar ve farklı dizinlerdeki görüntüleri gösterecek şekilde güncelleyebilirsiniz.

#### S: Uzak bir URL'den resimler kullanabilir miyim?

Y: Evet, yerel bir dosya yolu yerine URL'yi sağlayarak uzak bir URL'deki resimleri kullanabilirsiniz. Görüntüyü uzak URL'den almak için uygulamanızın internet erişimi olduğundan emin olun.

#### S: Giriş XML dosyası hangi formatta olmalıdır?

C: Girdi XML dosyası, bir kimlik kullanarak görüntüye başvuran bir yapıya sahip olmalıdır. Sağlanan kodda, görüntüye başvurmak için "testImg" kimliği kullanılır.

#### S: PDF'ye birden fazla resim ekleyebilir miyim?

C: Evet, farklı kimlikler kullanarak ve dosya yollarını buna göre ayarlayarak XML dosyasında bunlara atıfta bulunarak PDF'ye birden çok görüntü ekleyebilirsiniz.