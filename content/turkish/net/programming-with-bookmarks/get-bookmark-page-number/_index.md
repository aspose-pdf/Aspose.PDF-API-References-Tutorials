---
title: PDF Dosyasında Yer İmi Sayfa Numarasını Al
linktitle: PDF Dosyasında Yer İmi Sayfa Numarasını Al
second_title: Aspose.PDF for .NET API Referansı
description: Bu kapsamlı eğitimde Aspose.PDF for .NET kullanarak PDF dosyalarından yer imi sayfa numaralarının nasıl çıkarılacağını öğrenin.
type: docs
weight: 60
url: /tr/net/programming-with-bookmarks/get-bookmark-page-number/
---
## giriiş

Dijital çağda, PDF belgelerini etkili bir şekilde yönetmek hem kişisel hem de profesyonel kullanım için çok önemlidir. İster uygulamanızı geliştirmek isteyen bir geliştirici olun, ister belgelerinizi düzenlemesi gereken bir iş profesyoneli olun, PDF'leri nasıl düzenleyeceğinizi anlamak size zaman ve emek kazandırabilir. PDF yönetiminin temel özelliklerinden biri, yer imlerini ve bunlara karşılık gelen sayfa numaralarını çıkarabilme yeteneğidir. Bu eğitimde, PDF düzenlemeyi basitleştiren güçlü bir kütüphane olan Aspose.PDF for .NET kullanarak bunu nasıl başaracağımızı inceleyeceğiz.

## Ön koşullar

Koda dalmadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. Visual Studio: Makinenizde Visual Studio'nun yüklü olduğundan emin olun. Bu sizin geliştirme ortamınız olacaktır.
2.  .NET için Aspose.PDF: Aspose.PDF kütüphanesine sahip olmanız gerekir. Bunu şuradan indirebilirsiniz:[web sitesi](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: C# programlamaya aşina olmak, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

1. Visual Studio projenizi açın.
2. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
3.  Arama`Aspose.PDF` ve en son sürümü yükleyin.

Artık her şeyi ayarladığınıza göre, yer imi sayfa numaralarını çıkarma sürecini adım adım inceleyelim.

## Adım 1: Belge Dizininizi Ayarlayın

Yer imlerini çıkarabilmeniz için önce PDF belgenizin yolunu belirtmeniz gerekir. PDF dosyanız burada bulunur.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Bu adımda, değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın saklandığı gerçek yol ile. Bu yol, programa çalışmak istediğiniz PDF dosyasını nerede arayacağını söylediği için önemlidir.

## Adım 2: Bir PdfBookmarkEditor Örneği Oluşturun

 Daha sonra, bir örnek oluşturmanız gerekir`PdfBookmarkEditor`sınıf. Bu sınıf, PDF dosyalarındaki yer imlerini düzenlemek için yöntemler sağlar.

```csharp
// PDFBookmarkEditor Oluştur
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

 Burada, şunu örneklendiriyoruz:`PdfBookmarkEditor`Bu nesne PDF dosyamızı bağlamamıza ve ondan yer imlerini çıkarmamıza olanak tanıyacaktır.

## Adım 3: PDF Dosyasını Açın

 Şimdi PDF dosyasını bağlamanın zamanı geldi`PdfBookmarkEditor` Az önce oluşturduğunuz örnek.

```csharp
// PDF dosyasını aç
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Bu satırda şunu kullanıyoruz:`BindPdf` adlı PDF dosyasını açma yöntemi`GetBookmarks.pdf`Bu dosyanın belirtilen dizinde bulunduğundan emin olun; aksi takdirde bir hatayla karşılaşırsınız.

## Adım 4: Yer İşaretlerini Çıkarın

 PDF dosyası açıldığında, artık yer imlerini kullanarak çıkarabilirsiniz`ExtractBookmarks` Yöntem.

```csharp
// Yer imlerini ayıkla
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

 Bu adım, PDF dosyasındaki tüm yer imlerini alır ve bunları şu adlı bir değişkende depolar:`bookmarks`Bu değişken, bir sonraki adımda işleyeceğimiz tüm yer imi bilgilerini tutacaktır.

## Adım 5: Yer İşaretleri Üzerinde Yineleme Yapın

Artık yer imleriniz olduğuna göre, bunlar arasında gezinerek başlıklarını ve sayfa numaralarını görüntüleyebilirsiniz.

```csharp
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
    string strLevelSeprator = string.Empty;
    for (int i = 1; i < bookmark.Level; i++)
    {
        strLevelSeprator += "----";
    }
    Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
    Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
    Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

Bu döngüde, her yer imi üzerinde yineleme yapıyoruz. Her yer imi için, seviyesine göre bir dize ayırıcı oluşturuyoruz (yer imlerinin hiyerarşisini görsel olarak temsil etmek için). Sonra, her yer imi ile ilişkili başlığı, sayfa numarasını ve eylemi konsola yazdırıyoruz.

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF dosyasından yer imi sayfa numaralarını çıkarmak basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek PDF belgelerinizdeki yer imlerini etkili bir şekilde yönetebilirsiniz. Bir uygulama geliştiriyor veya yalnızca PDF'lerinizi düzenlemeniz gerekiyorsa, bu bilgi şüphesiz işe yarayacaktır.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan bir kütüphanedir.

### Aspose.PDF'yi ücretsiz kullanabilir miyim?
 Evet, Aspose kütüphaneyi değerlendirmek için kullanabileceğiniz ücretsiz bir deneme sürümü sunuyor. İndirebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.PDF'in dokümanlarını nerede bulabilirim?
 Belgeler mevcuttur[Burada](https://reference.aspose.com/pdf/net/).

### Aspose.PDF için lisans nasıl satın alabilirim?
 Lisansı şuradan satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).

### Sorunla karşılaşırsam ne yapmalıyım?
 Herhangi bir sorunla karşılaşırsanız, yardım isteyebilirsiniz.[Aspose destek forumu](https://forum.aspose.com/c/pdf/10).