---
title: Belge Al Penceresi
linktitle: Belge Al Penceresi
second_title: Aspose.PDF for .NET API Referansı
description: Bir PDF belgesinin pencere özellikleri hakkında bilgi almak için Aspose.PDF for .NET'in GetDocumentWindow özelliğini nasıl kullanacağınızı öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-document/getdocumentwindow/
---

 Aspose.PDF for .NET, geliştiricilerin kendi .NET uygulamalarında PDF dosyaları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan güçlü bir PDF işleme kitaplığıdır. Bu kitaplığın sunduğu özelliklerden biri, bir belgenin pencere özellikleri hakkında bilgi alma yeteneğidir. Bu öğretici, kullanımın adımlarında size rehberlik edecektir.`GetDocumentWindow` Aspose.PDF for .NET'in bir PDF belgesinin pencere özellikleri hakkında bilgi almak için özelliği.

## 1. Adım: Aspose.PDF for .NET'i kurun

 Aspose.PDF for .NET'i .NET uygulamalarınızda kullanmak için önce kütüphaneyi kurmalısınız. Kütüphanenin en son sürümünü adresinden indirebilirsiniz.[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net).

Kitaplığı indirdikten sonra, ZIP dosyasının içeriğini bilgisayarınızdaki bir klasöre çıkarın. Ardından, .NET projenizde Aspose.PDF for .NET DLL'ye bir referans eklemeniz gerekecektir.

## 2. Adım: PDF Belgesini Yükleyin

 Aspose.PDF for .NET'i yükledikten ve .NET projenize DLL'ye bir referans ekledikten sonra,`GetDocumentWindow` PDF belgesinin pencere özellikleri hakkında bilgi alma özelliği.

Bu özelliği kullanmanın ilk adımı, hakkında bilgi almak istediğiniz PDF belgesini yüklemektir. Bunu yapmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF belgesini aç
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolu ile. Bu kod, PDF belgesini bir`Document` belgenin pencere özellikleri hakkında bilgi almak için kullanabileceğiniz nesne.

## 3. Adım: Belgenin Pencere Özelliklerini Alın

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

Yukarıdaki kodda, her satır PDF belgesinin farklı bir pencere özelliğini alır ve onu konsola verir. Yalnızca ilgilendiğiniz özellikleri almak için bu kodu özelleştirebilirsiniz.

### Aspose.PDF for .NET kullanan PDF dosyasının belge alma penceresi için örnek kaynak kodu 

 Burada, bir PDF belgesinin pencere özelliklerini almak için tam kaynak kodu`GetDocumentWindow` Aspose.PDF for .NET özelliği:

```csharp

            
            // Belgeler dizininin yolu.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Belgeyi aç
            Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

            // Farklı belge özellikleri edinin
            // Belge penceresinin konumu - Varsayılan: yanlış
            Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
   
            // Baskın okuma sırası; sayfanın konumunu belirler
            // Yan yana görüntülendiğinde - Varsayılan: L2R
            Console.WriteLine("Direction : {0}", pdfDocument.Direction);
            
            // Pencerenin başlık çubuğunun belge başlığını gösterip göstermeyeceği
            // Yanlışsa, başlık çubuğunda PDF dosya adı görüntülenir - Varsayılan: yanlış
            Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
            
            // Belgenin penceresinin boyutuna sığacak şekilde yeniden boyutlandırılıp boyutlandırılmayacağı
            // İlk görüntülenen sayfa - Varsayılan: yanlış
            Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
            
            // Görüntüleyici uygulamasının menü çubuğunun gizlenip gizlenmeyeceği - Varsayılan: false
            Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
            
            //Görüntüleyici uygulamasının araç çubuğunun gizlenip gizlenmeyeceği - Varsayılan: false
            Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
            
            // Kaydırma çubukları gibi UI öğelerinin gizlenip gizlenmeyeceği
            // Ve yalnızca görüntülenen sayfa içeriğini bırakmak - Varsayılan: false
            Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
            
            // Belgenin sayfa modu. Tam ekran modundan çıkarken belge nasıl görüntülenir?
            Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
            
            // Sayfa düzeni, yani tek sayfa, bir sütun
            Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
            
            // Belge açıldığında nasıl görünmelidir?
            // Yani küçük resimleri göster, tam ekran, ek panelini göster
            Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
            
        
```
