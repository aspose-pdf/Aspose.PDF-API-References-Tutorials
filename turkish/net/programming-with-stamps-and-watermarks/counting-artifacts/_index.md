---
title: Eserleri Sayma
linktitle: Eserleri Sayma
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki filigranları kolayca nasıl sayacağınızı öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-stamps-and-watermarks/counting-artifacts/
---

Bu eğitimde, sizi Aspose.PDF for .NET kullanarak bir PDF belgesindeki yapıların nasıl sayılacağını adım adım anlatacağız. PDF belgesinin belirli bir sayfasındaki "filigran" eserlerin sayısını saymak için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi aç
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Yapıları sayın

Artık PDF belgesini yüklediğinize göre, belgenin belirli bir sayfasındaki "filigran" türü yapıları sayabilirsiniz. İşte nasıl:

```csharp
// sayacı başlat
int count = 0;

// Tüm ilk sayfa yapıları arasında geçiş yapın
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     // Artefakt alt türü "filigran" ise, sayacı artırın
     if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark)
         count++;
}

// "Filigran" türü yapıların sayısını görüntüleyin
Console.WriteLine("The page contains " + count + " watermarks");
```

Yukarıdaki kod, PDF belgesinin ilk sayfasındaki tüm yapılar arasında dolaşır ve karşılaşılan her "filigran" türü yapı için sayacı artırır.

### Aspose.PDF for .NET kullanarak Sayım Eserleri için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

int count = 0;
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	// Yapı türü filigran ise sayacı artırın
	if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark) count++;
}
Console.WriteLine("Page contains " + count + " watermarks");

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki "filigran" eserlerini nasıl sayacağınızı öğrendiniz. Artık bu bilgiyi, PDF belgelerinizdeki yapılar üzerinde belirli analizler ve işlemler gerçekleştirmek için kullanabilirsiniz.
