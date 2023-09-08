---
title: XForm'u Sayfaya Çiz
linktitle: XForm'u Sayfaya Çiz
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir PDF sayfasında XForm formu çizmeye yönelik adım adım kılavuz. Formu sayfaya ekleyin ve konumlandırın.
type: docs
weight: 10
url: /tr/net/programming-with-operators/draw-xform-on-page/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir sayfada XForm'un nasıl çizileceği konusunda adım adım bir kılavuz sunacağız. Aspose.PDF, PDF belgelerini programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. Aspose.PDF tarafından sağlanan operatörleri kullanarak, bir XForm formunu mevcut bir PDF sayfasına ekleyebilir ve konumlandırabilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. .NET framework ile yüklenen Visual Studio.
2. .NET için Aspose.PDF kütüphanesi.

## Adım 1: Proje Kurulumu

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Kütüphaneyi Aspose resmi web sitesinden indirebilir ve makinenize kurabilirsiniz.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını C# kod dosyanıza aktarın:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## 3. Adım: Dosya yollarını ayarlama

Arka plan görüntüsü, giriş PDF dosyası ve çıkış PDF dosyası için dosya yollarını tanımlayın:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Makinenizdeki gerçek dosya yollarını belirttiğinizden emin olun.

## 4. Adım: Giriş PDF dosyasını yükleme

Giriş PDF dosyasını yüklemek için aşağıdaki kodu kullanın:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Aşağıdaki kod GSave/GRestore operatörlerini kullanır
// Kod, XForm'u konumlandırmak için ContatenateMatrix operatörünü kullanır.
// Kod, XForm'u sayfada çizmek için Do operatörünü kullanır
// GSave/GRestore operatörleri mevcut içeriği sarar
// bu, mevcut içeriğin sonundaki ilk grafik durumunu elde etmek için yapılır
// aksi takdirde mevcut operatörler zincirinin sonunda istenmeyen dönüşümler kalabilir
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Yeni komutlardan sonra grafik durumunu düzgün şekilde sıfırlamak için GSave operatörünü ekleyin
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
//XForm'u x=100 ve y=500 koordinatlarına konumlandırın
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Do operatörüyle XForm'u çizin
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// XForm'u x=100 ve y=300 koordinatlarına konumlandırın
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Do operatörüyle XForm'u çizin
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// GSave'den sonra GRestore ile grafik durumunu geri yükleyin
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Gerçek dosya yollarını belirttiğinizden ve sayfa numarasını ve XForm konumlarını gerektiği gibi ayarladığınızdan emin olun.

### Aspose.PDF for .NET kullanarak Draw XForm On Page için örnek kaynak kodu
 
```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Örnek şunu gösteriyor
	// GSave/GRestore operatörlerinin kullanımı
	// XForm'u konumlandırmak için ContatenateMatrix operatör kullanımı
	// XForm'u sayfada çizmek için operatör kullanımını yapın
	// Mevcut içerikleri GSave/GRestore operatör çiftiyle sarın
	// bu, mevcut içeriklerin başındaki ilk grafik durumunu elde etmektir
	// aksi halde mevcut operatör zincirinin sonunda bazı istenmeyen dönüşümler kalabilir
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Yeni komutlardan sonra grafik durumunu düzgün bir şekilde temizlemek için grafik durumunu kaydetme operatörünü ekleyin
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xForm'u oluştur
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Görüntü genişliğini ve yüksekliğini tanımlayın
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Görüntüyü akışa yükle
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//XForm Kaynaklarının Görseller koleksiyonuna resim ekleyin
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Do operatörünü kullanma: Bu operatör görüntüyü çizer
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Formu x=100 y=500 koordinatlarına yerleştirin
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Do operatörüyle form çizin
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Formu x=100 y=300 koordinatlarına yerleştirin
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Do operatörüyle form çizin
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// GSave'den sonra GRestore ile grafik durumunu geri yükleyin
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF sayfasında XForm formunun nasıl çizileceğini öğrendiniz. Açıklanan adımları izleyerek, mevcut bir sayfaya bir XForm formu ekleyip konumlandırabilecek, böylece PDF belgelerinize daha fazla esneklik kazandırabileceksiniz.

### XForm çizimi için SSS sayfasında

#### S: Aspose.PDF'deki XForm nedir?

C: XForm, PDF belgesindeki yeniden kullanılabilir bir grafik nesnesidir. Farklı sayfalarda birden çok kez yeniden kullanılabilen karmaşık grafikleri, resimleri veya metinleri tanımlamanıza ve çizmenize olanak tanır.

#### S: Aspose.PDF için gerekli ad alanlarını nasıl içe aktarabilirim?

 C: C# kod dosyanızda şunu kullanın:`using` Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişim için gerekli ad alanlarını içe aktarma yönergesi:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### S: GSave ve GRestore operatörlerinin amacı nedir?

 C:`GSave` Ve`GRestore`Aspose.PDF'deki operatörler grafik durumunu kaydetmek ve geri yüklemek için kullanılır. İçeriğin bir bölümüne uygulanan dönüşümlerin ve ayarların sonraki bölümleri etkilememesini sağlamaya yardımcı olurlar.

#### S: Aspose.PDF kullanarak bir XForm'u nasıl tanımlarım?

 C: Bir XForm oluşturmak için`XForm.CreateNewForm` yöntemine ekleyin ve`Resources.Forms` belirli bir sayfanın toplanması. Daha sonra XForm'a içerik ekleyebilirsiniz.`Contents` mülk.

#### S: XForm'da nasıl resim çizebilirim?

 C: Görüntüyü bir akışa yükleyin ve`Resources.Images` XForm koleksiyonu. Kullan`Do` XForm'un içindeki operatör`Contents` görüntüyü çizmek için.

#### S: Bir XForm'u PDF sayfasında nasıl konumlandırırım?

 C: XForm'u bir sayfaya yerleştirmek için`ConcatenateMatrix` sayfanın içindeki operatör`Contents`. XForm'un çevirisini (konumunu) ve ölçeklendirmesini belirtmek için matris parametrelerini ayarlayın.

#### S: Aynı sayfada birden fazla XForm çizebilir miyim?

 C: Evet, aynı sayfada birden fazla XForm çizebilirsiniz.`ConcatenateMatrix`Her XForm'u farklı koordinatlara konumlandırmak için parametreler.

#### S: Bir XForm'un içeriğini oluşturulduktan sonra değiştirebilir miyim?

 C: Evet, XForm'un içeriğini oluşturulduktan sonra ek operatörler ekleyerek değiştirebilirsiniz.`Contents` mülk.

#### S: GSave ve GRestore operatörlerini atlarsam ne olur?

C: GSave ve GRestore operatörlerinin atlanması, istenmeyen dönüşümlerin veya ayarların sonraki içeriğe uygulanmasına yol açabilir. Bunları kullanmak temiz bir grafik durumunun korunmasına yardımcı olur.

#### S: XForms'u PDF belgesinin farklı sayfalarında yeniden kullanabilir miyim?

 C: Evet, aynı XForm'u sayfaya ekleyerek XForms'u birden çok sayfada yeniden kullanabilirsiniz.`Resources.Forms` farklı sayfaların toplanması.

#### S: Oluşturabileceğim XForm sayısında bir sınır var mı?

C: Oluşturabileceğiniz XForm sayısında kesin bir sınır olmasa da çok fazla XForm'un performansı ve bellek kullanımını etkileyebileceğini unutmayın. Bunları akıllıca kullanın.

#### S: Bir XForm'u döndürebilir miyim veya başka dönüşümler uygulayabilir miyim?

 C: Evet, kullanabilirsiniz`ConcatenateMatrix`XForm'a döndürme, ölçekleme ve çeviri gibi dönüşümleri uygulayan operatör.
