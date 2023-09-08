---
title: Alt Küme Stratejisi ile Fontları PDF Dosyasına Gömme
linktitle: Alt Küme Stratejisiyle Yazı Tiplerini Gömme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak Alt Küme Stratejisi ile yazı tiplerini bir PDF dosyasına nasıl yerleştireceğinizi öğrenin. Yalnızca gerekli karakterleri yerleştirerek PDF boyutunuzu optimize edin.
type: docs
weight: 130
url: /tr/net/programming-with-document/embedfontsusingsubsetstrategy/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak yazı tiplerini bir PDF dosyasına alt küme stratejisiyle nasıl yerleştireceğimizi tartışacağız. Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı olarak oluşturmasına, düzenlemesine ve değiştirmesine olanak tanıyan güçlü bir kitaplıktır. Yazı tiplerini bir PDF dosyasına gömmek, gerekli yazı tiplerinin bu aygıtlarda yüklü olup olmadığına bakılmaksızın, belgenin farklı aygıtlarda doğru şekilde görüntülenmesini sağlamak için önemli bir adımdır.

## 1. Adım: Yeni bir C# Konsol Uygulaması oluşturun
Başlamak için Visual Studio'da yeni bir C# Konsol Uygulaması oluşturun. İstediğiniz ismi verebilirsiniz. Proje oluşturulduktan sonra Aspose.PDF for .NET kütüphanesine bir referans eklemeniz gerekir.

## Adım 2: Aspose.PDF Ad Alanını İçe Aktarın
Aspose.PDF ad alanını içe aktarmak için C# dosyanızın en üstüne aşağıdaki kod satırını ekleyin:

```csharp
using Aspose.Pdf;
```

## 3. Adım: Mevcut bir PDF Dosyasını Yükleyin
Yazı tiplerini mevcut bir PDF dosyasına gömmek için bu dosyayı Document sınıfını kullanarak yüklemeniz gerekir. Aşağıdaki kod mevcut bir PDF dosyasının nasıl yükleneceğini gösterir:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");
```

## Adım 4: Yazı Tiplerini Alt Küme Stratejisiyle Gömme
Aspose.PDF for .NET yazı tipi gömme için iki strateji sunar: SubsetAllFonts ve SubsetEmbeddedFontsOnly.

SubsetAllFonts stratejisi belgedeki tüm yazı tiplerini bir alt küme olarak gömecektir. Alt küme, yazı tipinin yalnızca belgede kullanılan karakterleri içeren kısmıdır. Bu strateji, PDF belgesinin dosya boyutunu küçültmek için kullanışlıdır.

SubsetEmbeddedFontsOnly stratejisi yalnızca belgeye zaten katıştırılmış olan yazı tiplerinin alt kümesini katıştırır. Bir yazı tipi gömülü değilse bu stratejiden etkilenmeyecektir.

Aşağıdaki kod, alt küme stratejisiyle yazı tiplerinin bir PDF dosyasına nasıl gömüleceğini gösterir:

```csharp
// SubsetAllFonts durumunda tüm yazı tipleri belgeye alt küme olarak gömülecektir.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Tamamen gömülü yazı tipleri için yazı tipi alt kümesi eklenecektir ancak belgeye gömülü olmayan yazı tipleri etkilenmeyecektir.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Adım 5: PDF Belgesini Kaydedin
Alt küme stratejisiyle tüm yazı tiplerini PDF dosyasına gömdükten sonra belgeyi kaydetmeniz gerekir. Aşağıdaki kod PDF dosyasının nasıl kaydedileceğini gösterir:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Aspose.PDF for .NET kullanarak yazı tiplerini alt küme stratejisiyle gömmek için örnek kaynak kodu. 

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// SubsetAllFonts durumunda tüm yazı tipleri belgeye alt küme olarak gömülecektir.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// Tamamen gömülü yazı tipleri için yazı tipi alt kümesi eklenecektir ancak belgeye gömülü olmayan yazı tipleri etkilenmeyecektir.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Çözüm
Bu makalede, Aspose.PDF for .NET kullanarak yazı tiplerinin bir PDF dosyasına alt küme stratejisiyle nasıl yerleştirileceğini tartıştık. Aspose.PDF for .NET, farklı stratejilerle yazı tipi ekleme ve gömme de dahil olmak üzere, PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar. Yazı tiplerini bir PDF dosyasına gömmek, belgenin farklı cihazlarda doğru şekilde görüntülenmesini sağlamak için önemli bir adımdır ve alt küme stratejisi, PDF belgesinin dosya boyutunu küçültmek için yararlı bir özelliktir.

### Alt küme stratejisiyle PDF dosyasına yazı tiplerinin yerleştirilmesiyle ilgili SSS

#### S: PDF dosyasına yazı tipi yerleştirmeye yönelik alt küme stratejisi nedir?

C: PDF dosyasına yazı tipi yerleştirmeye yönelik alt küme stratejisi, belgede kullanılan karakterleri içeren yazı tipinin yalnızca bir kısmının gömüleceği anlamına gelir. Bu, gereksiz yazı tipi verilerini ortadan kaldırarak PDF belgesinin dosya boyutunun azaltılmasına yardımcı olur.

#### S: SubsetAllFonts ve SubsetEmbeddedFontsOnly stratejileri arasındaki fark nedir?

 C:`SubsetAllFonts`strateji belgedeki tüm yazı tiplerini bir alt küme olarak gömecek,`SubsetEmbeddedFontsOnly` stratejisi yalnızca belgeye zaten gömülü olan yazı tiplerinin alt kümesini gömecektir. İkinci strateji, halihazırda gömülü olmayan yazı tiplerini etkilemeyecektir.

#### S: Alt küme stratejisiyle yazı tipi yerleştirme neden önemlidir?

C: Alt küme stratejisiyle yazı tipi gömme, PDF dosyasının metni doğru şekilde görüntülemek için gerekli yazı tipi verilerini içerdiğinden emin olmak ve aynı zamanda yalnızca belgede kullanılan karakterleri dahil ederek dosya boyutunu daha küçük tutmak açısından önemlidir.

#### S: Aspose.PDF for .NET'i farklı stratejilerle yazı tiplerini gömmek için kullanabilir miyim?

 C: Evet, Aspose.PDF for .NET yazı tipi yerleştirme için çeşitli stratejiler sunar;`SubsetAllFonts` Ve`SubsetEmbeddedFontsOnly`. İhtiyaçlarınıza göre uygun stratejiyi seçebilirsiniz.

#### S: Aspose.PDF for .NET, PDF belgeleriyle çalışmak için güvenilir bir kütüphane midir?

C: Evet, Aspose.PDF for .NET, PDF belgeleriyle çalışmak için güvenilir ve güçlü bir kütüphanedir. .NET uygulamalarında PDF dosyalarını oluşturmak, düzenlemek ve değiştirmek için kapsamlı özellikler sağlar.