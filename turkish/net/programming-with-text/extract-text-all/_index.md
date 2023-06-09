---
title: Metnin Tümünü Çıkar
linktitle: Metnin Tümünü Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinden tüm metni nasıl çıkaracağınızı öğrenin.
type: docs
weight: 180
url: /tr/net/programming-with-text/extract-text-all/
---

Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF belgesinden tüm metni çıkarma sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
Metni çıkarmak istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using System.IO;
```

## 3. Adım: Belge dizinini ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: PDF belgesini açın
 kullanarak mevcut bir PDF belgesini açın.`Document` yapıcı ve yolu giriş PDF dosyasına geçirme.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## 5. Adım: Tüm metni ayıklayın
 Oluşturmak`TextAbsorber` belgeden metin ayıklamak için nesne. Ardından, emiciyi tüm sayfalar için kabul edin.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## 6. Adım: Ayıklanan metni alın
 Ayıklanan metne şuradan erişin:`TextAbsorber` nesne.

```csharp
string extractedText = textAbsorber.Text;
```

## 7. Adım: Ayıklanan metni kaydedin
 Oluşturmak`TextWriter` ve ayıklanan metni kaydetmek istediğiniz dosyayı açın. Ayıklanan metni dosyaya yazın ve akışı kapatın.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Aspose.PDF for .NET kullanarak Metin Tümünü Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Metni çıkarmak için TextAbsorber nesnesi oluşturun
TextAbsorber textAbsorber = new TextAbsorber();
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages.Accept(textAbsorber);
// Ayıklanan metni al
string extractedText = textAbsorber.Text;
// Bir yazar oluşturun ve dosyayı açın
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Dosyaya bir metin satırı yazın
tw.WriteLine(extractedText);
// akışı kapat
tw.Close();
```

## Çözüm
Aspose.PDF for .NET kullanarak bir PDF belgesindeki tüm metni başarıyla çıkardınız. Ayıklanan metin, belirtilen çıktı dosyasına kaydedildi.