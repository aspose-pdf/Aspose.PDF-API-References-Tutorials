---
title: Yazı Tipi Değiştirme İçin Uyarılar Alın
linktitle: Yazı Tipi Değiştirme İçin Uyarılar Alın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'in GetWarningsForFontSubstitution özelliğinin, bir PDF belgesini açarken yazı tipi değiştirme uyarılarını algılamak için nasıl kullanılacağını öğrenin.
type: docs
weight: 190
url: /tr/net/programming-with-document/getwarningsforfontsubstitution/
---

 Aspose.PDF for .NET, geliştiricilerin kendi .NET uygulamalarında PDF dosyaları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan popüler bir PDF işleme kitaplığıdır. Bu kitaplığın sunduğu özelliklerden biri, bir PDF belgesi açıldığında yazı tipi değiştirme uyarılarını algılama yeteneğidir. Bu öğretici, kullanımın adımlarında size rehberlik edecektir.`GetWarningsForFontSubstitution` Aspose.PDF for .NET'in bir PDF belgesi açarken yazı tipi değiştirme uyarılarını algılama özelliği.

## 1. Adım: Aspose.PDF for .NET'i kurun

 Aspose.PDF for .NET'i .NET uygulamalarınızda kullanmak için önce kütüphaneyi kurmalısınız. Kütüphanenin en son sürümünü adresinden indirebilirsiniz.[Aspose.PDF for .NET indirme sayfası](https://relases.aspose.com/pdf/net).

Kitaplığı indirdikten sonra, ZIP dosyasının içeriğini bilgisayarınızdaki bir klasöre çıkarın. Ardından, .NET projenizde Aspose.PDF for .NET DLL'ye bir referans eklemeniz gerekecektir.

## 2. Adım: PDF Belgesini Yükleyin

 Aspose.PDF for .NET'i yükledikten ve .NET projenize DLL'ye bir referans ekledikten sonra,`GetWarningsForFontSubstitution` PDF belgesini açarken yazı tipi değiştirme uyarılarını algılama özelliği.

Bu özelliği kullanmanın ilk adımı, yazı tipi değiştirme uyarılarını algılamak istediğiniz PDF belgesini yüklemektir. Bunu yapmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF belgesini aç
Document doc = new Document(dataDir + "input.pdf");
```

 Yukarıdaki kodda değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolu ile. Bu kod, PDF belgesini bir`Document` yazı tipi değiştirme uyarılarını algılamak için kullanabileceğiniz nesne.

## 3. Adım: Yazı Tipi Değiştirme Uyarılarını Algıla

Bir PDF belgesini açarken yazı tipi değiştirme uyarılarını algılamak için aşağıdaki kodu kullanabilirsiniz:

```csharp
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);
```

 Yukarıdaki kodda,`OnFontSubstitution` yazı tipi değiştirme uyarısı algılandığında çağrılacak bir yöntemdir. Yazı tipi değiştirme uyarısını istediğiniz şekilde işlemek için bu yöntemi özelleştirebilirsiniz.

 İşte örnek bir uygulama`OnFontSubstitution` yöntem:

```csharp
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```

 Yukarıdaki kodda,`OnFontSubstitution` yöntem, bir yazı tipi değiştirme uyarısı algılandığında, yalnızca orijinal yazı tipi adını ve değiştirilen yazı tipi adını konsola verir. Yazı tipi değiştirme uyarısını istediğiniz şekilde işlemek için bu yöntemi özelleştirebilirsiniz.

### Aspose.NET for PDF kullanarak Font Değiştirme İçin Uyarı Al için örnek kaynak kodu

 Kullanarak bir PDF belgesi açarken yazı tipi değiştirme uyarılarını algılamak için tam kaynak kodu buradadır.`GetWarningsForFontSubstitution` Aspose.PDF for .NET özelliği:

```csharp
// PDF belgesine giden yol
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF belgesini aç
Document doc = new Document(dataDir + "input.pdf");

// Yazı tipi değiştirme uyarılarını algıla
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);

// Yazı tipi değiştirme uyarısını işle
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.