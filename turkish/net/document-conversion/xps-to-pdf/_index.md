---
title: XPS'den PDF'ye dönüştürücü
linktitle: XPS'den PDF'ye dönüştürücü
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile XPS dosyasını PDF'ye dönüştürmek için adım adım kılavuz.
type: docs
weight: 350
url: /tr/net/document-conversion/xps-to-pdf/
---

Bu eğitimde, adım adım Aspose.PDF library for .NET kullanarak XPS dosyasını PDF'ye nasıl dönüştüreceğinizi göstereceğiz. Sağlanan C# kaynak kodunu detaylandıracağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz. Bu eğitimin sonunda, XPS dosyalarını kolayca PDF belgelerine dönüştürebileceksiniz.

## 1. Adım: Belgeler Dizinini Ayarlayın
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` dosyalarınızı kaydettiğiniz yolla.

## 2. Adım: XPS Yükleme Seçeneklerini Kullanarak LoadOptions Nesnesini Başlatın
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
XPS yükleme seçeneklerini kullanarak LoadOptions nesnesinin bir örneğini oluşturun.

## 3. Adım: Belge Nesnesini Oluşturun
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Giriş XPS dosyasını ve yükleme seçeneklerini belirten bir Belge nesnesi oluşturun.

## 4. Adım: Elde Edilen PDF Belgesini Kaydedin
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Ortaya çıkan PDF belgesini belirtilen dizine kaydedin.

### Aspose.Words for .NET kullanarak XPS'den PDF'e dönüştürme için örnek kaynak kodu

```csharp
try
{
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// XPS yükleme seçeneğini kullanarak LoadOption nesnesini oluşturun
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Belge nesnesi oluştur
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Ortaya çıkan PDF belgesini kaydedin
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm
Bu eğitimde, Aspose.PDF library for .NET kullanarak XPS dosyasını PDF'ye dönüştürmeyi öğrendik. Verilen adımları takip ederek bu dönüşümü kendi uygulamalarınızda kolayca gerçekleştirebilirsiniz. XPS dosyalarını PDF'ye dönüştürürken doğru ve profesyonel sonuçlar alın.