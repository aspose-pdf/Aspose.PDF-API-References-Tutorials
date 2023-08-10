---
title: PDF Dosyasındaki Görüntü Bilgileri
linktitle: PDF Dosyasındaki Görüntü Bilgileri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki görüntü bilgilerini çıkarın.
type: docs
weight: 160
url: /tr/net/programming-with-images/image-information/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak PDF dosyasındaki resimlerle ilgili bilgileri nasıl çıkaracağınızı adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Doğru belge dizinini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Kaynak PDF dosyasını yükleyin

 Bu adımda, kaynak PDF dosyasını kullanarak yükleyeceğiz.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 3. Adım: Varsayılan çözünürlüğü ayarlayın

Bu adımda, görüntüler için varsayılan çözünürlüğü ayarlayacağız. Örnekte, varsayılan çözünürlük 72 olarak ayarlanmıştır.

```csharp
int defaultResolution = 72;
```

## 4. Adım: Nesneleri ve sayaçları başlatın

Bu adımda, görüntü bilgilerini almak için gereken nesneleri ve sayaçları başlatacağız.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## 5. Adım: Belgenin ilk sayfasında operatörler arasında geçiş yapın

Bu adımda, görüntü ile ilgili işlemleri belirlemek için belgenin ilk sayfasındaki operatörleri gözden geçireceğiz.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## 6. Adım: Operatörleri yönetin ve görüntü bilgilerini çıkarın

Bu adımda, farklı operatör türlerini yöneteceğiz ve görüntülerle ilgili bilgileri çıkaracağız.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Dönüşümler için GSave ve GRestore işlemlerini yönetin
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Dönüşümler için ConcatenateMatrix işlemini yönetin
else if (opCtm != null)
{
     // Dönüşüm matrisini uygula
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Görüntüler için Do işlemini gerçekleştirin
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // görüntüyü al
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Resmin boyutlarını al
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Yukarıdaki bilgilere göre çözünürlüğü hesaplayın
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Görüntü bilgilerini göster
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Aspose.PDF for .NET kullanan Image Information için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF dosyasını yükleyin
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Görüntü için varsayılan çözünürlüğü tanımlayın
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Görüntü adlarını tutacak dizi listesi nesnesini tanımlayın
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// İstiflenecek bir nesne ekle
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Belgenin ilk sayfasında tüm operatörleri alın
foreach (Operator op in doc.Pages[1].Contents)
{
	// Dönüşümleri önceden ayarlanana geri döndürmek için GSave/GRestore işleçlerini kullanın
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Geçerli dönüştürme matrisini tanımladığı şekliyle ConcatenateMatrix nesnesini oluşturun.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Kaynaklardan nesneleri çeken Do operatörü oluşturun. Form nesnelerini ve Görüntü nesnelerini çizer
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Önceki durumu kaydedin ve mevcut durumu yığının en üstüne itin
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Mevcut durumu atın ve bir öncekini geri yükleyin
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Mevcut matrisi durum matrisiyle çarpın
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Bunun bir görüntü çizim operatörü olması durumunda
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// İlk pdf sayfasının resimlerini tutmak için XImage nesnesi oluşturun
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Resim boyutlarını al
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Resmin Yükseklik ve Genişlik bilgilerini alın
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Yukarıdaki bilgilere dayalı hesaplama çözünürlüğü
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Her görüntünün Boyut ve Çözünürlük bilgilerini görüntüleyin
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF dosyasındaki görüntü bilgilerini nasıl çıkaracağınızı öğrendiniz. Bu bilgileri, uygulamalarınızdaki çeşitli görüntü işleme görevleri için kullanabilirsiniz.

### PDF dosyasındaki resim bilgileri için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinden görüntü bilgisi çıkarmanın amacı nedir?

Y: Bir PDF belgesinden görüntü bilgilerinin ayıklanması, belgedeki görüntülerin boyutları, çözünürlüğü ve diğer nitelikleri hakkında bilgi sağlar. Bu bilgi görüntü işleme, analiz veya optimizasyon görevleri için kullanılabilir.

#### S: Aspose.PDF for .NET, bir PDF belgesinden resim bilgilerinin çıkarılmasına nasıl yardımcı olur?

Y: Aspose.PDF for .NET, görüntüleri dahil olmak üzere bir PDF belgesinin içeriğine erişmek ve bunları analiz etmek için araçlar sağlar. Sağlanan kod, çeşitli işleçler kullanılarak görüntü bilgilerinin nasıl çıkarılacağını ve görüntüleneceğini gösterir.

#### S: Bu yöntem kullanılarak ne tür görüntü bilgileri çıkarılabilir?

Y: Bu yöntem, bir PDF belgesindeki görüntüler için ölçeklenmiş boyutlar, çözünürlük ve görüntü adları gibi bilgileri ayıklamanıza ve görüntülemenize olanak tanır.

#### S: Kod, bir PDF belgesindeki görüntüyle ilgili işleçleri nasıl tanımlar ve işler?

C: Kod, PDF belgesinin belirli bir sayfasında işleçler aracılığıyla yinelenir. Görüntü işlemleri, dönüştürmeler ve işleme ile ilgili operatörleri tanımlar ve işler.

#### S: Varsayılan çözünürlüğün önemi nedir ve kodda nasıl kullanılır?

A: Varsayılan çözünürlük, görüntülerin gerçek çözünürlüğünü hesaplamak için bir referans noktası olarak kullanılır. Kod, boyutlarına ve varsayılan çözünürlük ayarına göre her görüntünün çözünürlüğünü hesaplar.

#### S: Çıkarılan görüntü bilgileri gerçek dünya senaryolarında nasıl kullanılabilir?

C: Ayıklanan görüntü bilgileri, görüntü kalitesi değerlendirmesi, görüntü optimizasyonu, görüntü küçük resimleri oluşturma ve görüntüyle ilgili karar verme süreçlerini kolaylaştırma gibi görevler için kullanılabilir.

#### S: Görüntüyle ilgili ek öznitelikler çıkarmak için kodu değiştirebilir miyim?

C: Evet, kodu, görüntülerin renk alanı, piksel derinliği veya görüntü türü gibi ek niteliklerini çıkarmak için özelleştirebilirsiniz.

#### S: Görüntü bilgisi çıkarma işlemi kaynak yoğun mu yoksa zaman alıcı mı?

Y: Görüntü bilgisi çıkarma işlemi verimlidir ve performans için optimize edilmiştir, bu da kaynak kullanımı ve işlem süresi üzerinde minimum etki sağlar.

#### S: Geliştiriciler, PDF belgelerinden görüntü bilgilerini belirleme ve ayıklamadan nasıl yararlanabilir?

C: Geliştiriciler, PDF belgelerindeki görüntülerin özelliklerine ilişkin içgörüler elde ederek görüntü işleme, işleme ve optimizasyon konusunda bilinçli kararlar almalarını sağlayabilir.

#### S: Bu yöntem, resim içeren PDF belgelerinin toplu işlenmesi için kullanılabilir mi?

C: Evet, bu yöntem birden çok sayfa veya belgeyi yineleyerek, görüntü bilgilerini çıkararak ve görüntüyle ilgili görevleri gerçekleştirerek toplu işleme için genişletilebilir.