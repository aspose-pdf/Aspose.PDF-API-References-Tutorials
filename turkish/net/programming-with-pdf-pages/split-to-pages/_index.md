---
title: Sayfalara Böl
linktitle: Sayfalara Böl
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesini ayrı sayfalara bölmek için adım adım kılavuz.
type: docs
weight: 140
url: /tr/net/programming-with-pdf-pages/split-to-pages/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesini ayrı sayfalara bölmek için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, bir PDF belgesini her biri tek bir sayfa içeren birden çok PDF dosyasına nasıl böleceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bölmek istediğiniz PDF belgesinin bulunduğu yer burasıdır. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini açın
 Ardından, bölmek için PDF belgesini açabilirsiniz.`Document` Aspose.PDF sınıfı. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## 3. Adım: Sayfaları gözden geçirin ve bölün
Artık bir döngü kullanarak PDF belgesinin tüm sayfaları arasında geçiş yapabilirsiniz. Her sayfa için yeni bir belge oluşturun ve o sayfayı bu yeni belgeye ekleyin. Ardından, her sayfa için benzersiz bir dosya adı kullanarak yeni belgeyi kaydedin.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Aspose.PDF for .NET kullanan Sayfalara Böl için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Tüm sayfaları dolaş
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesini ayrı sayfalara nasıl ayıracağımızı öğrendik. Bu adım adım kılavuzu izleyerek, bir PDF belgesini her biri tek bir sayfa içeren birden çok PDF dosyasına kolaylıkla bölebilirsiniz. Aspose.PDF, projelerinizde PDF belgeleriyle çalışmak için güçlü ve esnek bir API sunar. Artık bu özelliği, özel ihtiyaçlarınıza göre PDF belge bölme işlemlerini gerçekleştirmek için kullanabilirsiniz.
