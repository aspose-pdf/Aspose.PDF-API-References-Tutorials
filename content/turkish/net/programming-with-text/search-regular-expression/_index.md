---
title: PDF Dosyasında Düzenli İfade Arama
linktitle: PDF Dosyasında Düzenli İfade Arama
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimde Aspose.PDF for .NET kullanarak PDF dosyalarında düzenli ifadeleri nasıl arayacağınızı öğrenin. Regex ile üretkenliğinizi artırın.
type: docs
weight: 440
url: /tr/net/programming-with-text/search-regular-expression/
---
## giriiş

Büyük PDF belgeleriyle uğraşırken, tarihler, telefon numaraları veya diğer yapılandırılmış veriler gibi belirli desenleri veya biçimleri aradığınızı görebilirsiniz. PDF'yi manuel olarak incelemek sıkıcı olabilir, değil mi? İşte bu noktada düzenli ifade (regex) kullanmak işe yarar. Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF dosyasında düzenli ifade deseninin nasıl aranacağını inceleyeceğiz. Bu kılavuz, .NET uygulamanızda kolayca uygulayabilmeniz için her adımda size yol gösterecektir.

## Ön koşullar

Adım adım eğitime geçmeden önce, neye ihtiyacınız olduğunu gözden geçirelim:

-  .NET için Aspose.PDF: Bu kütüphanenin kurulu olması gerekir. Henüz kurmadıysanız,[buradan indirin](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio veya herhangi bir C# uyumlu IDE.
- .NET Framework: Projenizin .NET Framework'ün uygun sürümüyle kurulduğundan emin olun.
- Temel C# bilgisi: Bu rehber ayrıntılı olsa da, C# hakkında temel bir anlayışa sahip olmak faydalı olacaktır.

### Paketleri İçe Aktar

Başlamak için, Aspose.PDF for .NET'ten projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu paketler PDF'lerle çalışmak ve regex kullanarak arama işlemleri gerçekleştirmek için gereklidir.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Aspose.PDF kullanarak bir PDF dosyasında düzenli ifadeleri arama sürecini birden fazla adıma bölelim.

## Adım 1: Belge Dizinini Ayarlayın

 Her PDF işlemi, belgenizin nerede bulunduğunu belirtmekle başlar. PDF dosyanızın yolunu tanımlamanız gerekir; bu,`dataDir` değişken.

### Adım 1.1: Belge Yolunuzu Tanımlayın

```csharp
// PDF belgenize giden yolu tanımlayın
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın gerçek yolu ile. Bu adım, kodunuzu çalışmak istediğiniz dosyaya yönlendirdiği için önemlidir.

### Adım 1.2: PDF Belgesini açın

 Daha sonra, PDF belgesini şu şekilde açmanız gerekir:`Document` Aspose.PDF'den sınıf.

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Burada,`"SearchRegularExpressionAll.pdf"` regex araması yapacağımız örnek PDF dosyasıdır.

## Adım 2: TextFragmentAbsorber'ı Ayarlayın

 İşte sihir burada gerçekleşiyor!`TextFragmentAbsorber` sınıf, belirli bir desene veya düzenli ifadeye uyan metin parçalarının yakalanmasına yardımcı olur.

Bir regex kullanarak desenleri bulmak için emiciyi ayarlayalım. Bu durumda, "1999-2000" gibi yılların bir desenini arıyoruz.

```csharp
// Düzenli ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000 gibi
```

 Düzenli ifade`\\d{4}-\\d{4}` Tipik olarak yıl aralıkları için geçerli olan, dört rakamdan oluşan, ardından bir tire ve dört rakam daha gelen bir örüntü arar.

## Adım 3: Düzenli İfade Aramasını Etkinleştirin

 Arama işleminin deseni düzenli bir ifade olarak yorumlamasını sağlamak için, arama seçeneklerini kullanarak yapılandırmanız gerekir.`TextSearchOptions` sınıf.

```csharp
// Düzenli ifade kullanımını belirtmek için metin arama seçeneğini ayarlayın
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

 Ayarlama`TextSearchOptions` ile`true` emicinin düz metin yerine düzenli ifade tabanlı arama kullanmasını sağlar.

## Adım 4: Metin Emiciyi Kabul Edin

 Bu aşamada, arama işlemini gerçekleştirebilmesi için metin emiciyi PDF belgesine uygularsınız. Bu, şu şekilde yapılır:`Accept` yöntem üzerinde`Pages` PDF belgesinin nesnesi.

```csharp
// Tüm sayfalar için emiciyi kabul et
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

Bu komut, PDF'in tüm sayfalarını işler ve düzenli ifadeyle eşleşen herhangi bir metin arar.

## Adım 5: Sonuçları Çıkarın ve Görüntüleyin

 Arama tamamlandıktan sonra sonuçları çıkarmanız gerekir.`TextFragmentAbsorber` bu sonuçları bir`TextFragmentCollection`Her eşleşen metin parçasına erişmek ve görüntülemek için bu koleksiyonda dolaşabilirsiniz.

### Adım 5.1: Çıkarılan Metin Parçalarını Alın

```csharp
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

Artık parçaları topladığınıza göre, bunlar arasında dolaşıp metin, konum, yazı tipi ayrıntıları gibi ilgili ayrıntıları görüntülemenin zamanı geldi.

### Adım 5.2: Parçalar Arasında Döngü

```csharp
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

 Her biri için`TextFragment`, yazı tipi boyutu, yazı tipi adı ve konumu gibi ayrıntılar yazdırılır. Bu yalnızca metni bulmanıza yardımcı olmakla kalmaz, aynı zamanda tam biçimlendirmesini ve konumunu da verir.

## Çözüm

İşte bu kadar! Düzenli ifadeler kullanarak bir PDF dosyasında desenler aramak inanılmaz derecede güçlüdür, özellikle tarihler, telefon numaraları ve benzeri desenler gibi yapılandırılmış metinler için. Aspose.PDF for .NET bu tür işlemleri kolaylıkla gerçekleştirmenin kusursuz bir yolunu sunar. Artık düzenli ifadelerin gücünden yararlanarak PDF metin aramasını otomatikleştirebilir ve iş akışınızı daha verimli hale getirebilirsiniz.

## SSS

### Tek bir PDF'de birden fazla deseni arayabilir miyim?
 Evet, birden fazla çalıştırabilirsiniz`TextFragmentAbsorber` Aynı PDF üzerinde, her biri farklı regex desenlerine sahip nesneler.

### Aspose.PDF büyük/küçük harfe duyarlı olmayan desenlerin aranmasını destekliyor mu?
 Kesinlikle! Şunu yapılandırabilirsiniz:`TextSearchOptions` aramayı büyük/küçük harfe duyarlı hale getirmek için.

### İçinde arama yapabileceğim PDF dosyalarının boyutunda bir sınır var mı?
Kesin bir sınır yoktur, ancak performans PDF'in boyutuna ve regex deseninin karmaşıklığına bağlı olarak değişebilir.

### PDF'de bulunan metni vurgulayabilir miyim?
Evet, Aspose.PDF emiciyi kullanarak bulunan metni vurgulamanıza ve hatta değiştirmenize olanak tanır.

### Desen bulunamazsa hataları nasıl hallederim?
 Eşleşme bulunmazsa,`TextFragmentCollection` boş olacaktır. Bu senaryoyu, sonuçları döngüye almadan önce basit bir kontrolle halledebilirsiniz.