---
title: PDF Dosyasına Gizli Metin Ekleme ve Arama
linktitle: PDF Dosyasına Gizli Metin Ekleme ve Arama
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF belgelerine gizli metin eklemeyi ve aramayı öğrenin. Kod örneklerinin de dahil olduğu adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-text/add-and-search-hidden-text/
---
## giriiş

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF dosyasına gizli metin ekleme ve arama konusunda adım adım bir kılavuzda size yol göstereceğiz. İster deneyimli bir geliştirici olun, ister programlama becerilerinizi geliştirmek isteyen bir acemi olun, bu makale uygulamalarınıza gizli metin işlevselliğini dahil etmek için ihtiyaç duyduğunuz içgörüleri sağlayacaktır.

## Ön koşullar

Kodlama kısmına geçmeden önce, halletmeniz gereken birkaç ön koşul var:

### Gereksinim Kontrol Listesi
- Visual Studio: Visual Studio'nun yüklü olduğundan emin olun. Bu eğitim .NET Framework kullandığınızı varsayar.
-  Aspose.PDF for .NET: Aspose.PDF for .NET kütüphanesine sahip olmanız gerekir. Bunu indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
- Temel C# bilgisi: C# programlamaya aşina olmak, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

## Paketleri İçe Aktar

Kodunuza başlamadan önce, gerekli Aspose.PDF ad alanlarını içe aktardığınızdan emin olmanız gerekir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

### Projenizi Kurun
1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun veya mevcut bir projeyi kullanın.
2.  NuGet paketini ekleyerek Aspose.PDF'yi yükleyin. Bunu NuGet Paket Yöneticisi'ne gidip arayarak yapabilirsiniz`Aspose.PDF`. 
3.  Alternatif olarak, kütüphaneyi doğrudan şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/pdf/net/) ve bunu projenize referans olarak ekleyin.

### Gerekli Ad Alanlarını İçe Aktar
C# dosyanızın en üstüne aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu adım çok önemlidir çünkü bu ad alanları PDF belgelerini düzenlemek için gerekli sınıfları ve yöntemleri içerir.

## Gizli Metinli PDF Belgesi Oluşturma

Artık kurulumunuz tamamlandığına göre, hem görünür hem de görünmez metin içeren bir PDF belgesi oluşturmak için gereken adımları inceleyelim.

### Adım 1: Belge Dizinini Tanımlayın
İlk olarak, PDF'nin kaydedileceği yolu ayarlamak isteyeceksiniz. Sihir burada başlıyor!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Bunu dizininize değiştirin
```

 Bu satır, oluşturduğunuz PDF'nin nerede saklanacağını tanımlar. Değiştirmeyi unutmayın`YOUR DOCUMENT DIRECTORY` gerçek yolunuzla.

### Adım 2: Bir PDF Belgesi Oluşturun
Şimdi yeni bir PDF belgesi oluşturalım ve içine sayfalar ekleyelim.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Burada yeni bir belge başlatıyoruz ve metin parçalarımızı yerleştireceğimiz bir sayfa ekliyoruz.

### Adım 3: Görünür ve Gizli Metin Ekleme
Şimdi PDF dosyamıza hem görünür hem de görünmez metin ekleyeceğiz.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 Bu kesitte,`frag1` görünür olacak, oysa`frag2` bundan sonra görünmez olarak ayarlanacak.

### Adım 4: Metni Görünmez Olarak Ayarlayın
 Metnini yapmak için`frag2` görünmez, sadece onu değiştirirsiniz`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Bu özelliği ayarlayarak, ilişkili herhangi bir metin`frag2` PDF görüntülendiğinde işlenmeyecektir.

### Adım 5: Sayfaya Metin Parçaları Ekleyin
Son olarak bu metin parçalarını sayfaya ekleyip PDF'i kaydediyoruz.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Kodun bu kısmı metin parçalarımızı sayfaya ekler. Bundan sonra, belgeyi düzgün bir şekilde kaydeder ve imha ederiz.

## PDF'de Gizli Metni Arama

Artık hem görünür hem de gizli metinle PDF'imizi oluşturduğumuza göre, gizli metni nasıl arayacağız? Bunu parçalara ayıralım.

### Adım 1: PDF Belgesini Yükleyin
PDF içerisinde metin aramak için öncelikle yeni oluşturduğumuz belgeyi yüklememiz gerekiyor.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Adım 2: Bir Metin Parçası Emici Oluşturun
 Biz kullanacağız`TextFragmentAbsorber` PDF'deki tüm metin parçalarını yakalamak için.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Burada ilk sayfadaki tüm metin parçalarını özümsemek istediğimizi belirtiyoruz.

### Adım 3: Parçalar Arasında Yineleme Yapın
Artık toplanan metin parçaları arasında gezinerek hangilerinin görünür, hangilerinin gizli olduğunu bulabiliriz.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Bu döngü her metin parçasını kontrol eder ve içeriğini konumu ve görünürlük durumuyla birlikte yazdırır.`fragment.TextState.Invisible` true olarak ayarlandığında, metin gizlenir!

### Adım 4: Belgeyi İmha Edin
Son olarak, işiniz bittiğinde belgeyi tekrar elden çıkarmayı unutmayın.

```csharp
doc.Dispose();
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyalarına gizli metin ekleme ve arama yapma heyecan verici sürecini ele aldık. Hem görünür hem de gizli metin içeren bir PDF belgesinin nasıl oluşturulacağını ve bu gizli metni program aracılığıyla nasıl arayacağınızı öğrendik. Bu yetenek, ister gizli bilgileri depolamanız, ister belgelerinizde benzersiz bir kullanıcı deneyimi sağlamanız gereksin, çeşitli uygulamalarda inanılmaz derecede faydalı olabilir.

ASPose.PDF'ye daha aşina oldukça, olasılıklar sonsuz hale gelir. Denemeye devam edin ve PDF belgelerinizle neler başarabileceğinizin sınırlarını zorlayın!

## SSS

### Aspose.PDF şifrelenmiş PDF dosyalarını işleyebilir mi?  
Evet, Aspose.PDF PDF belgelerinin şifrelenmesini ve şifresinin çözülmesini destekler. PDF'lerinizi parolalarla kolayca güvence altına alabilirsiniz.

### Aspose.PDF için deneme sürümü mevcut mu?  
 Kesinlikle! Ücretsiz denemeyi şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).

### Aspose.PDF hangi programlama dillerini destekliyor?  
Aspose.PDF, C#, Java ve Python da dahil olmak üzere birden fazla dili destekler.

### Aspose.PDF'in dokümanlarını nerede bulabilirim?  
 Belgelere erişebilirsiniz[Burada](https://reference.aspose.com/pdf/net/).

### Sorun yaşarsam nasıl destek alabilirim?  
 Destek için Aspose forumlarını ziyaret edebilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).