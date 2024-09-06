---
title: Sayfada XForm Çiz
linktitle: Sayfada XForm Çiz
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF kullanarak bir PDF sayfasına XForm formu çizmeye yönelik adım adım kılavuz. Formu sayfaya ekleyin ve konumlandırın.
type: docs
weight: 10
url: /tr/net/programming-with-operators/draw-xform-on-page/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir sayfaya XForm çizme konusunda adım adım bir kılavuz sunacağız. Aspose.PDF, PDF belgelerini programatik olarak oluşturmanıza, düzenlemenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. Aspose.PDF tarafından sağlanan operatörleri kullanarak, mevcut bir PDF sayfasına bir XForm formu ekleyebilir ve konumlandırabilirsiniz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. .NET framework ile Visual Studio kuruldu.
2. .NET için Aspose.PDF kütüphanesi.

## Adım 1: Proje Kurulumu

Başlamak için, Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Kütüphaneyi Aspose resmi web sitesinden indirebilir ve makinenize kurabilirsiniz.

## Adım 2: Gerekli ad alanlarını içe aktarın

C# kod dosyanıza, Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını içe aktarın:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Adım 3: Dosya yollarını ayarlama

Arka plan resmi, giriş PDF dosyası ve çıkış PDF dosyası için dosya yollarını tanımlayın:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Makinenizdeki gerçek dosya yollarını belirttiğinizden emin olun.

## Adım 4: Girdi PDF dosyasını yükleme

Giriş PDF dosyasını yüklemek için aşağıdaki kodu kullanın:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Aşağıdaki kod GSave/GRestore operatörlerini kullanır
// Kod, XForm'u konumlandırmak için ContatenateMatrix operatörünü kullanır
// Kod, XForm'u sayfada çizmek için Do operatörünü kullanır
// GSave/GRestore operatörleri mevcut içeriği sarar
//bu, mevcut içeriğin sonunda ilk grafik durumunu elde etmek için yapılır
// aksi takdirde mevcut operatörlerin zincirinin sonunda istenmeyen dönüşümler kalabilir
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Yeni komutlardan sonra grafik durumunu düzgün bir şekilde sıfırlamak için GSave operatörünü ekleyin
pageContents. Add(new GSave());

// XForm'u oluşturun
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Resmin genişliğini ve yüksekliğini ayarlayın
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Görüntüyü bir akışa yükleyin
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Görüntüyü XForm kaynak görüntüleri koleksiyonuna ekleyin
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Do operatörünü kullanma: Bu operatör görüntüyü çizer
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// XForm'u x=100 ve y=500 koordinatlarına yerleştirin
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Do operatörü ile XForm'u çizin
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// XForm'u x=100 ve y=300 koordinatlarına yerleştirin
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Do operatörü ile XForm'u çizin
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// GSave'den sonra GRestore ile grafik durumunu geri yükleyin
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Gerçek dosya yollarını belirttiğinizden ve sayfa numarasını ve XForm konumlarını gerektiği gibi ayarladığınızdan emin olun.

### .NET için Aspose.PDF kullanarak Sayfada XForm Çizmek için örnek kaynak kodu
 
```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Örnek şunu gösteriyor
	// GSave/GRestore operatörlerinin kullanımı
	// xForm'u konumlandırmak için ContatenateMatrix operatörü kullanımı
	//Sayfada xForm çizmek için operatör kullanımı
	// Mevcut içerikleri GSave/GRestore operatör çiftiyle sarın
	// bu, mevcut içeriklerin sonunda ilk grafik durumunu elde etmek içindir
	// Aksi takdirde mevcut operatör zincirinin sonunda bazı istenmeyen dönüşümler kalabilir
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Yeni komutlardan sonra grafik durumunu düzgün bir şekilde temizlemek için grafik durumu kaydetme operatörünü ekleyin
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xForm'u Oluştur
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Görüntü genişliğini ve yüksekliğini tanımlayın
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Görüntüyü akışa yükle
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// XForm Kaynaklarının Görüntüler koleksiyonuna görüntü ekleyin
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Do operatörünü kullanma: bu operatör görüntü çizer
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Formu x=100 y=500 koordinatlarına yerleştirin
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Do operatörü ile çizim formu
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Formu x=100 y=300 koordinatlarına yerleştirin
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Do operatörü ile çizim formu
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// GSave'den sonra GRestore ile grafik durumunu geri yükleyin
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF sayfasına XForm formunun nasıl çizileceğini öğrendiniz. Açıklanan adımları izleyerek, mevcut bir sayfaya bir XForm formu ekleyebilir ve konumlandırabilir, böylece PDF belgelerinize daha fazla esneklik kazandırabilirsiniz.

### Sayfadaki XForm çizimi için SSS

#### S: Aspose.PDF'de XForm nedir?

A: XForm, PDF belgesinde yeniden kullanılabilir bir grafik nesnesidir. Farklı sayfalarda birden çok kez yeniden kullanılabilen karmaşık grafikler, resimler veya metinler tanımlamanıza ve çizmenize olanak tanır.

#### S: Aspose.PDF için gerekli ad alanlarını nasıl içe aktarabilirim?

 A: C# kod dosyanızda şunu kullanın:`using` Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişim için gerekli ad alanlarını içe aktarma yönergesi:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### S: GSave ve GRestore operatörlerinin amacı nedir?

 A:`GSave` Ve`GRestore` Aspose.PDF'deki operatörler grafik durumunu kaydetmek ve geri yüklemek için kullanılır. İçeriğin bir bölümüne uygulanan dönüşümlerin ve ayarların sonraki bölümleri etkilememesini sağlamaya yardımcı olurlar.

#### S: Aspose.PDF kullanarak bir XForm'u nasıl tanımlarım?

 A: Bir XForm oluşturmak için şunu kullanın:`XForm.CreateNewForm` yöntemini kullanın ve ekleyin`Resources.Forms` belirli bir sayfanın koleksiyonu. Daha sonra XForm'un içeriğine ekleyebilirsiniz`Contents` mülk.

#### S: XForm içerisinde nasıl resim çizebilirim?

A: Görüntüyü bir akışa yükleyin ve ekleyin`Resources.Images` XForm koleksiyonu. Kullanın`Do` XForm'un içindeki operatör`Contents` Resmi çizmek için.

#### S: Bir XForm'u PDF sayfasına nasıl yerleştiririm?

 A: Bir XForm'u bir sayfaya yerleştirmek için şunu kullanın:`ConcatenateMatrix` sayfanın içindeki operatör`Contents`. XForm'un çevirisini (pozisyonunu) ve ölçeklemesini belirtmek için matris parametrelerini ayarlayın.

#### S: Aynı sayfada birden fazla XForm çizebilir miyim?

 A: Evet, aynı sayfada birden fazla XForm'u ayarlayarak çizebilirsiniz.`ConcatenateMatrix` Her XForm'u farklı koordinatlara yerleştirmek için parametreler.

#### S: Bir XForm oluşturulduktan sonra içeriğini değiştirebilir miyim?

 A: Evet, XForm'un içeriğini, ek operatörler ekleyerek oluşturduktan sonra değiştirebilirsiniz.`Contents` mülk.

#### S: GSave ve GRestore operatörlerini atlarsam ne olur?

A: GSave ve GRestore operatörlerini atlamak, sonraki içeriklere istenmeyen dönüşümlerin veya ayarların uygulanmasına yol açabilir. Bunları kullanmak, temiz bir grafik durumunun korunmasına yardımcı olur.

#### S: XForms'u PDF belgesinin farklı sayfalarında yeniden kullanabilir miyim?

 A: Evet, aynı XForm'u birden fazla sayfada yeniden kullanarak XForm'u kullanabilirsiniz.`Resources.Forms` farklı sayfaların koleksiyonu.

#### S: Oluşturabileceğim XForm sayısının bir sınırı var mı?

A: Oluşturabileceğiniz XForms sayısı için kesin bir sınır olmasa da, çok fazla XForms'un performansı ve bellek kullanımını etkileyebileceğini unutmayın. Bunları dikkatli kullanın.

#### S: Bir XForm'u döndürebilir veya başka dönüşümler uygulayabilir miyim?

 A: Evet, kullanabilirsiniz`ConcatenateMatrix` XForm'a döndürme, ölçekleme ve çeviri gibi dönüşümleri uygulamak için operatör.
