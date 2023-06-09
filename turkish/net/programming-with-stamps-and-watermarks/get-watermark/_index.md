---
title: Filigran Al
linktitle: Filigran Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizden filigranları nasıl çıkaracağınızı öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-stamps-and-watermarks/get-watermark/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinden nasıl filigran alacağınızı adım adım anlatacağız. Belirli bir sayfanın yapıtlarını yinelemek ve filigran türünü, metnini ve konumunu almak için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF belgesini aç
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Filigranı alma

Artık PDF belgesini yüklediğinize göre, filigran bilgilerini almak için belirli sayfa yapılarını yineleyebilirsiniz. İşte nasıl:

```csharp
// Eserlere göz atın ve filigran alt türünü, metnini ve konumunu alın
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Yukarıdaki kod, PDF belgesinin ilk sayfasındaki tüm yapılar arasında dolaşır ve karşılaşılan her filigranın alt tipini, metnini ve dikdörtgenini (konumu) görüntüler.

### Aspose.PDF for .NET kullanarak Get Watermark için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Yineleme yapın ve küvet tipini, metnini ve yapının konumunu alın
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinden filigran bilgisi almayı öğrendiniz. Artık bu bilgiyi PDF belgelerinizdeki filigranları analiz etmek ve işlemek için kullanabilirsiniz.
