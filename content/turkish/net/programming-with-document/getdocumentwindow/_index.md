---
title: Belgeyi Al Penceresi
linktitle: Belgeyi Al Penceresi
second_title: .NET API Referansı için Aspose.PDF
description: Bir PDF belgesinin pencere özellikleri hakkında bilgi almak için Aspose.PDF for .NET'in GetDocumentWindow özelliğini nasıl kullanacağınızı öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF dosyaları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan güçlü bir PDF işleme kitaplığıdır. Bu kitaplığın sunduğu özelliklerden biri, belgenin pencere özellikleri hakkında bilgi alabilme yeteneğidir. Bu eğitim, kullanımın adımları konusunda size rehberlik edecektir.`GetDocumentWindow` Aspose.PDF for .NET'in bir PDF belgesinin pencere özellikleri hakkında bilgi alma özelliği.

## Adım 1: Aspose.PDF for .NET'i yükleyin

 Aspose.PDF for .NET'i .NET uygulamalarınızda kullanmak için öncelikle kütüphaneyi kurmanız gerekir. Kütüphanenin en son sürümünü adresinden indirebilirsiniz.[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net).

Kütüphaneyi indirdikten sonra ZIP dosyasının içeriğini bilgisayarınızdaki bir klasöre çıkarın. Daha sonra .NET projenize Aspose.PDF for .NET DLL dosyasına bir referans eklemeniz gerekecektir.

## Adım 2: PDF Belgesini Yükleyin

Aspose.PDF for .NET'i yükledikten ve .NET projenize DLL'ye bir referans ekledikten sonra, kullanmaya başlayabilirsiniz.`GetDocumentWindow` PDF belgesinin pencere özellikleri hakkında bilgi alma özelliği.

Bu özelliği kullanmanın ilk adımı, hakkında bilgi almak istediğiniz PDF belgesini yüklemektir. Bunu yapmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// PDF belgesinin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF belgesini açın
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolu ile birlikte. Bu kod, PDF belgesini bir`Document` daha sonra belgenin pencere özellikleri hakkında bilgi almak için kullanabileceğiniz nesne.

## 3. Adım: Belgenin Pencere Özelliklerini Alın

Bir PDF belgesinin pencere özellikleri hakkında bilgi almak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// Belgenin pencere özelliklerini alın
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

Yukarıdaki kodda, her satır PDF belgesinin farklı bir pencere özelliğini alır ve bunu konsola çıkarır. Yalnızca ilgilendiğiniz özellikleri almak için bu kodu özelleştirebilirsiniz.

### Aspose.PDF for .NET kullanarak PDF dosyasının belgeyi al penceresi için örnek kaynak kodu 

 Burada, bir PDF belgesinin pencere özelliklerini almak için kullanılan kaynak kodun tamamı bulunmaktadır.`GetDocumentWindow` Aspose.PDF for .NET'in özelliği:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Farklı belge özellikleri edinin
// Belge penceresinin konumu - Varsayılan: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Baskın okuma sırası; sayfanın konumunu belirler
// Yan yana görüntülendiğinde - Varsayılan: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Pencerenin başlık çubuğunun belge başlığını görüntülemesi gerekip gerekmediği
// Yanlışsa başlık çubuğunda PDF dosya adı görüntülenir - Varsayılan: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Belgenin penceresinin boyutuna uyacak şekilde yeniden boyutlandırılıp boyutlandırılmayacağı
// İlk görüntülenen sayfa - Varsayılan: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Görüntüleyici uygulamasının menü çubuğunun gizlenip gizlenmeyeceği - Varsayılan: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Görüntüleyici uygulamasının araç çubuğunun gizlenip gizlenmeyeceği - Varsayılan: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Kaydırma çubukları gibi kullanıcı arayüzü öğelerinin gizlenip gizlenmeyeceği
// Ve yalnızca sayfa içeriğinin görüntülenmesine izin verilir - Varsayılan: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Belgenin sayfa modu. Tam ekran modundan çıkıldığında belge nasıl görüntülenir?
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Sayfa düzeni yani tek sayfa, bir sütun
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Belge açıldığında nasıl görüntülenmeli?
// Yani küçük resimleri göster, tam ekran, ek panelini göster
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Çözüm

Bu eğitimde, bir PDF belgesinin pencere özellikleri hakkında bilgi almak için Aspose.PDF for .NET'in nasıl kullanılacağını öğrendik. Bir PDF belgesi yükleyerek ve pencere özelliklerine erişerek, belgenin bir görüntüleyici uygulamada açıldığında nasıl görüntülenmesi gerektiği hakkında bilgi toplayabilirsiniz. Aspose.PDF for .NET, PDF dosyalarıyla programlı olarak çalışmak için güçlü bir dizi özellik sunar ve bu da onu .NET uygulamalarında PDF manipülasyonu için değerli bir araç haline getirir.

### SSS'ler

#### S: Bir PDF belgesinin pencere özelliklerini almanın amacı nedir?

C: Bir PDF belgesinin pencere özelliklerini almak, PDF belgesinin bir görüntüleyici uygulamada açıldığında nasıl görüntülenmesi gerektiği hakkında bilgi toplamanıza olanak tanır. Bu özellikler, pencere konumu, görüntüleme modu ve kullanıcı arayüzü öğelerinin görünürlüğü gibi çeşitli hususları kontrol eder.

#### S: Aspose.PDF for .NET'i .NET projeme nasıl kurabilirim?

 C: Aspose.PDF for .NET'i kurmak için kütüphaneyi şuradan indirmeniz gerekir:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net). İndirdikten sonra ZIP dosyasının içeriğini çıkarın ve .NET projenize Aspose.PDF for .NET DLL dosyasına bir referans ekleyin.

#### S: Kodu yalnızca belirli pencere özelliklerini alacak şekilde özelleştirebilir miyim?

C: Evet, ihtiyacınız olmayan satırlara yorum ekleyerek belirli pencere özelliklerini almak için kodu özelleştirebilirsiniz. Koddaki her satır belirli bir pencere özelliğine karşılık gelir; böylece gereksinimlerinize göre özellikleri dahil edebilir veya hariç tutabilirsiniz.

#### S: Aspose.PDF for .NET'i kullanarak ne tür pencere özelliklerine ulaşabilirim?

C: Aspose.PDF for .NET'i kullanarak, bir PDF belgesinin pencereyi ortalamak, sayfa düzenini ayarlamak, araç çubuklarının ve menü çubuklarının görünümünü kontrol etmek ve daha fazlası dahil olmak üzere çeşitli pencere özelliklerini alabilirsiniz.