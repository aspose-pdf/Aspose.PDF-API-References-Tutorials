---
title: PDF Dosyasındaki Metnin Tamamını Değiştir
linktitle: PDF Dosyasındaki Metnin Tamamını Değiştir
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasındaki tüm metni nasıl değiştireceğinizi öğrenin.
type: docs
weight: 350
url: /tr/net/programming-with-text/replace-text-all/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasındaki tüm metni nasıl değiştireceğinizi açıklayacağız. Gerekli C# kaynak koduyla birlikte adım adım bir kılavuz sağlayacağız.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temel anlayışı.

## 1. Adım: Belge Dizinini Ayarlayın

 Giriş PDF dosyasının bulunduğu dizinin yolunu ayarlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` PDF dosyanızın yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: PDF Belgesini Yükleyin

 PDF belgesini kullanarak yükleyin`Document` Aspose.PDF kütüphanesinden sınıf.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## 3. Adım: Metni Arayın ve Değiştirin

 Oluşturmak`TextFragmentAbsorber` Giriş arama ifadesinin tüm örneklerini bulmak için nesne. Metin parçalarını çıkarmak için PDF belgesinin tüm sayfaları için emiciyi kabul edin.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 4. Adım: Metni Değiştir

Çıkarılan metin parçaları arasında dolaşın ve metni gerektiği gibi değiştirin. Metni ve yazı tipi, yazı tipi boyutu, ön plan rengi ve arka plan rengi gibi diğer özellikleri güncelleyin.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## 5. Adım: Değiştirilen PDF'yi kaydedin

Değiştirilen PDF belgesini belirtilen çıktı dosyasına kaydedin.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak Tüm Metni Değiştir için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Tüm sayfalar için emiciyi kabul edin
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Parçalar arasında döngü yapın
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Metni ve diğer özellikleri güncelleme
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Ortaya çıkan PDF belgesini kaydedin.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF belgesindeki tüm metni nasıl değiştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve verilen C# kodunu çalıştırarak bir PDF belgesi yükleyebilir, istediğiniz metni arayabilir, değiştirebilir ve değiştirilen PDF'yi kaydedebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasındaki Tüm Metni Değiştir" öğreticisinin amacı nedir?

C: "PDF Dosyasındaki Tüm Metni Değiştir" eğitimi, bir PDF belgesindeki belirli bir metnin tüm örneklerini değiştirmek için .NET için Aspose.PDF kütüphanesini kullanma sürecinde size rehberlik etmeyi amaçlamaktadır. Örnek C# koduyla birlikte adım adım bir kılavuz sağlar.

#### S: Bir PDF belgesindeki metnin tüm örneklerini neden değiştirmek isteyeyim?

C: Belge genelindeki içeriği güncellemeniz veya standartlaştırmanız gerektiğinde, PDF belgesindeki belirli bir metnin tüm örneklerini değiştirmek gerekli olabilir. Bu süreç özellikle belge içeriğinde ve biçimlendirmesinde tutarlılığın sağlanması açısından yararlı olabilir.

#### S: Belge dizinini nasıl ayarlarım?

C: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` giriş PDF dosyanızın bulunduğu dizinin yolunu içeren değişken.

#### S: Bir PDF belgesindeki metnin tüm örneklerini nasıl değiştiririm?

C: Eğitim aşağıdaki adımlarda size yol gösterir:

1.  PDF belgesini kullanarak yükleyin`Document` sınıf.
2.  Oluşturmak`TextFragmentAbsorber` Giriş arama ifadesinin tüm örneklerini bulmak için nesne. Metin parçalarını çıkarmak için PDF belgesinin tüm sayfaları için emiciyi kabul edin.
3. Çıkarılan metin parçaları arasında dolaşın ve metni değiştirin. Yazı tipi, yazı tipi boyutu, ön plan rengi ve arka plan rengi gibi diğer özellikleri gerektiği gibi güncelleyin.
4. Değiştirilen PDF belgesini kaydedin.

#### S: Büyük/küçük harfe duyarlı aramaya dayalı olarak metni değiştirebilir miyim?

 C: Evet, değiştirebilirsiniz`TextFragmentAbsorber` Büyük/küçük harfe duyarlı bir arama gerçekleştirmek için metni arayın. Aramak istediğiniz metni tam olarak belirtmeniz yeterlidir; emici onu buna göre eşleştirecektir.

#### S: Metni değiştirirken yazı tipini değiştirmek isteğe bağlı mıdır?

C: Evet, yazı tipi değişimi isteğe bağlıdır. Yeni bir yazı tipi belirtmezseniz metin, orijinal metin parçasının yazı tipini koruyacaktır.

#### S: PDF belgesinin belirli bölümlerindeki metni nasıl değiştirebilirim?

C: Metin parçalarının konumuna bağlı olarak koşullu ifadeler içerecek şekilde metin parçaları arasındaki döngüyü uyarlayabilirsiniz. Bu şekilde, PDF'nin yalnızca belirli bölümlerindeki metni değiştirmeyi seçebilirsiniz.

#### S: Sağlanan kodu çalıştırmanın beklenen sonucu nedir?

C: Öğreticiyi takip ederek ve sağlanan C# kodunu çalıştırarak, PDF belgesindeki belirtilen metnin tüm örneklerini değiştireceksiniz. Değiştirilen metin, yazı tipi, yazı tipi boyutu, ön plan rengi ve arka plan rengi gibi belirttiğiniz özelliklere sahip olacaktır.

#### S: Bu yaklaşımı resimler veya ek açıklamalar gibi metin olmayan öğeleri değiştirmek için kullanabilir miyim?

C: Hayır, bu eğitim özellikle bir PDF belgesindeki metni değiştirmeye odaklanmaktadır. Metin olmayan öğeleri değiştirmeniz gerekiyorsa farklı prosedürleri izlemeniz veya diğer Aspose.PDF özelliklerini kullanmanız gerekir.