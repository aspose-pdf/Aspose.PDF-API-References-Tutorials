---
title: Yazdırma İletişim Kutusu İçin Özellikleri Ayarla
linktitle: Yazdırma İletişim Kutusu İçin Özellikleri Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Adım adım kılavuz kullanarak Aspose.PDF for .NET'te yazdırma iletişim kutusunun özelliklerini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 320
url: /tr/net/programming-with-document/setpropertiesforprintdialog/
---
İşte Aspose.PDF for .NET kullanarak yazdırma iletişim kutusunun özelliklerini ayarlamak için adım adım bir kılavuz:


## 1. Adım: PDF belgenizin bulunduğu dizini tanımlayın:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  Adım 2: Yeni bir örneğini oluşturun.`Document` class:

```csharp
using (Document doc = new Document())
{
  // Kod buraya
}
```
   
## 3. Adım: Belgeye yeni bir sayfa ekleyin:

```csharp
doc.Pages.Add();
```
   
##  Adım 4: dubleks özelliğini şu şekilde ayarlayın:`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## Adım 5: Belgeyi belirtilen dosya adı ve biçimiyle kaydedin:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

### Aspose.PDF for .NET kullanarak Yazdırma İçin Özellikleri Ayarla İletişim Kutusu için örnek kaynak kodu

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document doc = new Document())
{
	doc.Pages.Add();
	doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
	doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
}
```

## Çözüm

Aspose.PDF for .NET, PDF dosyalarınızda yazdırma iletişim kutusunun özelliklerini ayarlamayı kolaylaştırır. Yukarıdaki adım adım kılavuzu izleyerek, PDF dosyalarınızı yazdırmak için hızlı bir şekilde optimize edebilirsiniz.