---
title: Sayfadaki Tüm Ek Açıklamaları Sil
linktitle: Sayfadaki Tüm Ek Açıklamaları Sil
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzu kullanarak Aspose.PDF for .NET ile bir PDF sayfasından tüm notları nasıl sileceğinizi öğrenin.
type: docs
weight: 40
url: /tr/net/annotations/deleteallannotationsfrompage/
---
Aspose.PDF for .NET, geliştiricilerin PDF dosyaları oluşturmasına, değiştirmesine ve dönüştürmesine olanak sağlayan güçlü bir kitaplıktır. Bu makalede, bir PDF belgesinin belirli bir sayfasından tüm notları silmek için Aspose.PDF for .NET'in nasıl kullanılacağını keşfedeceğiz. Süreci anlamanıza yardımcı olacak adım adım bir kılavuz sağlayacağız.

Aspose.PDF for .NET Kullanarak Sayfadaki Tüm Ek Açıklamaları Sil için aşağıdaki adımları izleyin

## 1. Adım: Aspose.PDF for .NET'i kurun

 Aspose.PDF for .NET'i kullanmak için önce kütüphaneyi kurmanız gerekir. Yapabilirsiniz[indirmek](https://releases.aspose.com/pdf/net/)Aspose yayınlarından kütüphaneyi indirin ve bilgisayarınıza kurun. Kurulumdan sonra, projenizdeki kütüphaneye bir referans eklemeniz gerekir.

## 2. Adım: Yeni Bir Konsol Uygulaması Oluşturun

Visual Studio'da yeni bir konsol uygulaması oluşturun ve Aspose.PDF kitaplığına bir referans ekleyin. Bu eğitimde C# dilini kullanacağız.

## 3. Adım: PDF Belgesini Yükleyin

Sağlanan kaynak kodunda yaptığımız ilk şey, PDF belgesinin yolunu belirtmektir. "BELGE DİZİNİNİZİ", bilgisayarınızdaki PDF belgesinin gerçek yolu ile değiştirmeniz gerekir. Ardından, Document sınıfının yeni bir örneğini oluşturuyoruz ve PDF belgesini yüklüyoruz.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "DeleteAllAnnotationsFromPage.pdf");
```

## 4. Adım: Bir Sayfadan Tüm Ek Açıklamaları Silin

PDF belgesinin belirli bir sayfasından tüm açıklamaları silmek için Sayfa nesnesinin Ek Açıklamalar koleksiyonuna erişmemiz ve Delete() yöntemini çağırmamız gerekir. Sağlanan kaynak kodunda, PDF belgesinin ikinci sayfasındaki (dizin 1) tüm açıklamaları siliyoruz.

```csharp
pdfDocument.Pages[1].Annotations.Delete();
```

## 5. Adım: Güncellenmiş PDF Belgesini Kaydedin

Ek açıklamaları sildikten sonra güncellenmiş PDF belgesini kaydetmemiz gerekiyor. Sağlanan kaynak kodunda, çıktı PDF belgesinin yolunu belirtir ve Save() yöntemini çağırırız.

```csharp
dataDir = dataDir + "DeleteAllAnnotationsFromPage_out.pdf";
pdfDocument.Save(dataDir);
```

## Çözüm

Bu makalede, Aspose.PDF for .NET kullanarak bir PDF belgesinin belirli bir sayfasındaki tüm açıklamaları nasıl sileceğinizi anlamanıza yardımcı olacak adım adım bir kılavuz sağladık. Bu kılavuzda belirtilen adımları izleyerek bu özelliği kendi projenizde kolayca uygulayabilirsiniz.

### Aspose.PDF for .NET Kullanarak Sayfadaki Tüm Ek Açıklamaları Silmek İçin Örnek Kaynak Kodu

```csharp
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "DeleteAllAnnotationsFromPage.pdf");

	// Belirli notu sil
	pdfDocument.Pages[1].Annotations.Delete();

	dataDir = dataDir + "DeleteAllAnnotationsFromPage_out.pdf";
	// Güncellenen belgeyi kaydet
	pdfDocument.Save(dataDir);
``` 
