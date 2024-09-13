---
title: PDF Dosyasında Varsayılan Yazı Tipini Ayarla
linktitle: PDF Dosyasında Varsayılan Yazı Tipini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak PDF dosyalarında varsayılan yazı tipini nasıl ayarlayacağınızı öğrenin. PDF belgelerini geliştirmek isteyen geliştiriciler için mükemmeldir.
type: docs
weight: 280
url: /tr/net/programming-with-document/setdefaultfont/
---
## giriiş

Hiç bir PDF belgesini açıp yazı tiplerinin eksik olduğunu veya doğru şekilde görüntülenmediğini mi gördünüz? Sinir bozucu olabilir, değil mi? Endişelenmeyin! Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF dosyasında varsayılan bir yazı tipinin nasıl ayarlanacağını ele alacağız. Bu güçlü kitaplık, PDF belgelerini kolayca düzenlemenizi sağlar ve varsayılan bir yazı tipi ayarlamak, sunduğu birçok özellikten yalnızca biridir. O halde, kodlama şapkanızı alın ve başlayalım!

## Ön koşullar

Koda geçmeden önce, yerinde olması gereken birkaç şey var:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. .NET geliştirme için en iyi IDE'dir.
2.  .NET için Aspose.PDF: Aspose.PDF kütüphanesini indirip yüklemeniz gerekecek. Bunu bulabilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya dair biraz bilgi sahibi olmak, ele alacağımız örnekleri anlamanızda size büyük katkı sağlayacaktır.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

1. Visual Studio projenizi açın.
2. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
3.  Arama`Aspose.PDF` ve en son sürümü yükleyin.

Paketi kurduktan sonra kodlamaya başlamaya hazırsınız!

## Adım 1: Projenizi Kurun

### Yeni Bir Proje Oluştur

Öncelikle Visual Studio'da yeni bir C# projesi oluşturalım:

- Visual Studio'yu açın ve "Yeni proje oluştur" seçeneğini seçin.
- "Konsol Uygulaması (.NET Core)" seçeneğini seçin ve "İleri"ye tıklayın.
-  Projenize bir isim verin (örneğin,`AsposePdfExample`) ve "Oluştur"a tıklayın.

### Yönergeleri Kullanarak Ekle

 Şimdi, gerekli using yönergelerini en üste ekleyelim.`Program.cs` dosya:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

Bu yönergeler Aspose.PDF sınıflarına ve metotlarına erişmenizi sağlayacaktır.

## Adım 2: PDF Belgesini Yükleyin

### Belge Yolunu Belirleyin

Sonra, çalışmak istediğiniz PDF belgesinin yolunu belirtmeniz gerekecek. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Gerçek dizininizle değiştirin
string documentName = Path.Combine(dataDir, "input.pdf");
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın bulunduğu gerçek yol ile.

### Belgeyi Yükle

Şimdi mevcut PDF dokümanını yükleyelim:

```csharp
using (FileStream fs = new FileStream(documentName, FileMode.Open))
{
    Document document = new Document(fs);
}
```

 Bu kod parçacığı PDF dosyasını açar ve bir`Document` manipüle edebileceğiniz nesne.

## Adım 3: Varsayılan Yazı Tipini Ayarlayın

### PDFSaveOptions Oluştur

 Şimdi heyecan verici kısım geliyor! Bir örnek oluşturmanız gerekecek`PdfSaveOptions` varsayılan yazı tipini belirtmek için:

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
```

### Varsayılan Yazı Tipi Adını Belirleyin

Sonra, varsayılan yazı tipi adını ayarlayacaksınız. Bu örnek için "Arial" kullanacağız:

```csharp
pdfSaveOptions.DefaultFontName = "Arial";
```

Bu satır, Aspose.PDF'ye belirli bir yazı tipi olmayan herhangi bir metin için varsayılan yazı tipi olarak Arial'i kullanmasını söyler.

## Adım 4: Belgeyi Kaydedin

Son olarak, değiştirilmiş PDF belgesini yeni varsayılan yazı tipiyle kaydetmenin zamanı geldi:

```csharp
document.Save(Path.Combine(dataDir, "output_out.pdf"), pdfSaveOptions);
```

 Bu satır belgeyi şu şekilde kaydeder:`output_out.pdf` belirtilen dizinde.

## Çözüm

İşte oldu! Aspose.PDF for .NET kullanarak bir PDF dosyasında varsayılan bir yazı tipini başarıyla ayarladınız. Bu basit ama güçlü özellik, yazı tipleri eksik olsa bile belgelerinizin tam olarak istediğiniz gibi görünmesini sağlamaya yardımcı olabilir. Yani, bir dahaki sefere yazı tipi sorunları olan bir PDF ile karşılaştığınızda, tam olarak ne yapmanız gerektiğini bileceksiniz!

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Arial dışında başka fontlar kullanabilir miyim?
Evet, sisteminizde yüklü olan herhangi bir yazı tipini varsayılan yazı tipi olarak belirleyebilirsiniz.

### Aspose.PDF'i kullanmak ücretsiz mi?
Aspose.PDF ücretsiz deneme sürümü sunuyor, ancak tüm işlevlerden yararlanmak için lisans satın almanız gerekiyor.

### Daha fazla dokümanı nerede bulabilirim?
 Kapsamlı dokümanları bulabilirsiniz[Burada](https://reference.aspose.com/pdf/net/).

### Aspose.PDF için nasıl destek alabilirim?
 Aspose forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).