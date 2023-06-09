---
title: Kök Yapısı
linktitle: Kök Yapısı
second_title: Aspose.PDF for .NET API Referansı
description: PDF belgesinin kök ve StructTreeRoot nesnesine erişmek için kök yapı öğelerini Aspose.PDF for .NET ile kullanmaya yönelik adım adım kılavuz.
type: docs
weight: 130
url: /tr/net/programming-with-tagged-pdf/root-structure/
---
Bu adım adım kılavuzda, kök yapı öğelerini Aspose.PDF for .NET ile nasıl kullanacağınızı göstereceğiz. Aspose.PDF, PDF belgelerini programlı olarak oluşturmanıza ve yönetmenize izin veren güçlü bir kitaplıktır. Kök yapı öğeleri, PDF belgesinin StructTreeRoot nesnesine ve kök yapı öğesine erişmenizi sağlar.

Şimdi koda inelim ve kök yapı elemanlarının Aspose.PDF for .NET ile nasıl kullanılacağını öğrenelim.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.PDF kitaplığı for .NET kurulu.
2. C# programlama dili hakkında temel bilgi.

## 1. Adım: Ortamı ayarlama

Başlamak için C# geliştirme ortamınızı açın ve yeni bir proje oluşturun. Projenizde .NET için Aspose.PDF kitaplığına bir referans eklediğinizden emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi oluşturma

 İlk adım, kullanarak yeni bir PDF belgesi oluşturmaktır.`Document` sınıf.

```csharp
// PDF belgesini oluşturun
Document document = new Document();
```

## 3. Adım: Etiketli içerikle çalışın

Ardından, çalışmak için belgenin etiketli içeriğini alırız.

```csharp
// Belgenin etiketli içeriğini alın
ITaggedContent taggedContent = document.TaggedContent;
```

## 4. Adım: Belge başlığını ve dilini ayarlayın

Artık belge başlığını ve dilini ayarlayabiliriz.

```csharp
// Belge başlığını ve dilini tanımlayın
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Adım 5: Kök yapı öğesine erişin

Artık belgenin StructTreeRoot nesnesine ve kök yapı öğesine erişebiliriz.

```csharp
// Kök yapı öğesine erişin
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;
```

### Aspose.PDF for .NET kullanan Root Structure için örnek kaynak kodu 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF Belgesi Oluştur
Document document = new Document();

// TaggedPdf ile çalışmak için İçerik Alın
ITaggedContent taggedContent = document.TaggedContent;

// Documnet için Başlığı ve Dili Ayarlayın
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// StructTreeRootElement ve RootElement özellikleri erişim için kullanılır.
// Pdf belgesinin StructTreeRoot nesnesine ve kök yapı öğesine (Belge yapısı öğesi).
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;

```

## Çözüm

Tebrikler! Aspose.PDF for .NET ile kök yapı elemanlarını nasıl kullanacağınızı öğrendiniz. Belge yapısı üzerinde gelişmiş işlemler gerçekleştirmek için artık PDF belgesinin StructTreeRoot nesnesine ve kök yapı öğesine erişebilirsiniz.
