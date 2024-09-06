---
title: Belge Al Penceresi
linktitle: Belge Al Penceresi
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF'nin GetDocumentWindow özelliğinin bir PDF belgesinin pencere özellikleri hakkında bilgi almak için nasıl kullanılacağını öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF dosyaları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan güçlü bir PDF düzenleme kütüphanesidir. Bu kütüphanenin sunduğu özelliklerden biri, bir belgenin pencere özellikleri hakkında bilgi alma yeteneğidir. Bu eğitim, sizi kullanma adımlarında yönlendirecektir`GetDocumentWindow` Aspose.PDF for .NET'in bir PDF belgesinin pencere özellikleri hakkında bilgi alma özelliği.

## Adım 1: .NET için Aspose.PDF'yi yükleyin

 .NET uygulamalarınızda Aspose.PDF for .NET'i kullanmak için önce kütüphaneyi yüklemeniz gerekir. Kütüphanenin en son sürümünü şu adresten indirebilirsiniz:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net).

Kütüphaneyi indirdikten sonra, ZIP dosyasının içeriğini bilgisayarınızdaki bir klasöre çıkarın. Daha sonra .NET projenizde Aspose.PDF for .NET DLL'sine bir referans eklemeniz gerekecektir.

## Adım 2: PDF Belgesini Yükleyin

 Aspose.PDF for .NET'i yükledikten ve .NET projenize DLL'ye bir başvuru ekledikten sonra, kullanmaya başlayabilirsiniz.`GetDocumentWindow`Bir PDF belgesinin pencere özellikleri hakkında bilgi almaya yarayan özellik.

Bu özelliği kullanmanın ilk adımı, hakkında bilgi almak istediğiniz PDF belgesini yüklemektir. Bunu yapmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini açın
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Yukarıdaki kodda şunu değiştirin:`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kod. Bu kod PDF belgesini bir`Document` Daha sonra belgenin pencere özellikleri hakkında bilgi almak için kullanabileceğiniz nesne.

## Adım 3: Belgenin Pencere Özelliklerini Alın

Bir PDF belgesinin pencere özellikleri hakkında bilgi almak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// Belgenin pencere özelliklerini al
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

Yukarıdaki kodda, her satır PDF belgesinin farklı bir pencere özelliğini alır ve bunu konsola çıktı olarak verir. Bu kodu yalnızca ilgilendiğiniz özellikleri alacak şekilde özelleştirebilirsiniz.

### .NET için Aspose.PDF kullanarak PDF dosyasının belge penceresini almak için örnek kaynak kodu 

 İşte PDF belgesinin pencere özelliklerini almak için tam kaynak kodu:`GetDocumentWindow` Aspose.PDF for .NET'in özelliği:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Farklı belge özellikleri edinin
// Belge penceresinin konumu - Varsayılan: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Baskın okuma sırası; sayfanın konumunu belirler
// Yan yana görüntülendiğinde - Varsayılan: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Pencerenin başlık çubuğunun belge başlığını görüntüleyip görüntülemeyeceği
// Yanlışsa, başlık çubuğu PDF dosya adını görüntüler - Varsayılan: yanlış
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Belgenin penceresinin, belgenin boyutuna uyacak şekilde yeniden boyutlandırılması gerekip gerekmediği
// İlk görüntülenen sayfa - Varsayılan: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Görüntüleyici uygulamasının menü çubuğunu gizleyip gizlememe - Varsayılan: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// Görüntüleyici uygulamasının araç çubuğunu gizleyip gizlememe - Varsayılan: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Kaydırma çubukları gibi kullanıcı arayüzü öğelerinin gizlenip gizlenmeyeceği
// Ve sadece sayfa içeriklerinin görüntülenmesini sağlar - Varsayılan: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//Belgenin sayfa modu. Tam ekran modundan çıkıldığında belgenin nasıl görüntüleneceği.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Sayfa düzeni, yani tek sayfa, tek sütun
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Belge açıldığında nasıl görüntülenmesi gerektiği
// Küçük resimleri göster, tam ekran, ek panelini göster
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Çözüm

Bu eğitimde, bir PDF belgesinin pencere özellikleri hakkında bilgi almak için Aspose.PDF for .NET'i nasıl kullanacağımızı öğrendik. Bir PDF belgesini yükleyerek ve pencere özelliklerine erişerek, belgenin bir görüntüleyici uygulamada açıldığında nasıl görüntülenmesi gerektiği hakkında bilgi toplayabilirsiniz. Aspose.PDF for .NET, PDF dosyalarıyla programatik olarak çalışmak için güçlü bir özellik seti sunar ve bu da onu .NET uygulamalarında PDF düzenleme için değerli bir araç haline getirir.

### SSS

#### S: Bir PDF belgesinin pencere özelliklerini almanın amacı nedir?

A: Bir PDF belgesinin pencere özelliklerini almak, PDF belgesinin bir görüntüleyici uygulamasında açıldığında nasıl görüntülenmesi gerektiği hakkında bilgi toplamanıza olanak tanır. Bu özellikler, pencere konumu, görüntüleme modu ve kullanıcı arayüzü öğelerinin görünürlüğü gibi çeşitli yönleri kontrol eder.

#### S: .NET projemde Aspose.PDF for .NET'i nasıl kurabilirim?

 A: .NET için Aspose.PDF'yi yüklemek için, kütüphaneyi şu adresten indirmeniz gerekir:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net). İndirdikten sonra, ZIP dosyasının içeriğini çıkarın ve .NET projenize Aspose.PDF for .NET DLL'sine bir referans ekleyin.

#### S: Kodu yalnızca belirli pencere özelliklerini alacak şekilde özelleştirebilir miyim?

A: Evet, ihtiyacınız olmayan satırları yorumlayarak belirli pencere özelliklerini almak için kodu özelleştirebilirsiniz. Koddaki her satır belirli bir pencere özelliğine karşılık gelir, böylece gereksinimlerinize göre özellikleri dahil edebilir veya hariç tutabilirsiniz.

#### S: Aspose.PDF for .NET kullanarak hangi tür pencere özelliklerini alabilirim?

A: Aspose.PDF for .NET'i kullanarak, pencereyi ortalamak, sayfa düzenini ayarlamak, araç çubuklarının ve menü çubuklarının görüntüsünü kontrol etmek ve daha fazlası dahil olmak üzere bir PDF belgesinin çeşitli pencere özelliklerini alabilirsiniz.