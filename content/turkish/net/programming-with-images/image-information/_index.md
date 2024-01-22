---
title: PDF Dosyasındaki Görüntü Bilgileri
linktitle: PDF Dosyasındaki Görüntü Bilgileri
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak görüntü bilgilerini PDF dosyasından çıkarın.
type: docs
weight: 160
url: /tr/net/programming-with-images/image-information/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak PDF dosyasındaki görüntüler hakkındaki bilgilerin nasıl çıkarılacağı konusunda size adım adım yol gösterecektir. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Doğru belge dizinini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Kaynak PDF dosyasını yükleyin

 Bu adımda, kaynak PDF dosyasını kullanarak yükleyeceğiz.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcıya gidin ve yolu PDF belgesine iletin.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 3. Adım: Varsayılan çözünürlüğü ayarlayın

Bu adımda görseller için varsayılan çözünürlüğü ayarlayacağız. Örnekte varsayılan çözünürlük 72 olarak ayarlanmıştır.

```csharp
int defaultResolution = 72;
```

## Adım 4: Nesneleri ve sayaçları başlatın

Bu adımda görüntü bilgisini almak için gereken nesneleri ve sayaçları başlatacağız.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Adım 5: Belgenin ilk sayfasındaki operatörler arasında geçiş yapın

Bu adımda görselle ilgili işlemleri belirlemek için belgenin ilk sayfasındaki operatörleri inceleyeceğiz.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## 6. Adım: Operatörleri yönetin ve görüntü bilgilerini çıkarın

Bu adımda farklı operatör türlerini yöneteceğiz ve görüntülerle ilgili bilgileri çıkaracağız.

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
// Dönüşümler için ConcatenateMatrix işlemini gerçekleştirin
else if (opCtm != null)
{
     // Dönüşüm matrisini uygulama
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
// Görüntüler için Yap işlemini gerçekleştirin
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Resmi geri al
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Resmin boyutlarını alın
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Yukarıdaki bilgilere göre çözünürlüğü hesaplayın
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Resim bilgilerini görüntüle
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Aspose.PDF for .NET kullanarak Görüntü Bilgisi için örnek kaynak kodu 
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
// Yığınlanacak bir nesne ekleme
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Tüm operatörleri belgenin ilk sayfasına alın
foreach (Operator op in doc.Pages[1].Contents)
{
	// Dönüşümleri önceden ayarlanan duruma geri döndürmek için GSave/GRestore operatörlerini kullanın
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Geçerli dönüşüm matrisini tanımladığı için ConcatenateMatrix nesnesini örnekleyin.
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
		// Mevcut durumu atın ve öncekini geri yükleyin
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
		// Bunun bir resim çizim operatörü olması durumunda
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
			// Yukarıdaki bilgilere dayanarak hesaplama çözünürlüğü
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

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF dosyasındaki görüntü bilgilerini nasıl çıkaracağınızı öğrendiniz. Bu bilgiyi uygulamalarınızdaki çeşitli görüntü işleme görevleri için kullanabilirsiniz.

### PDF dosyasındaki resim bilgileri için SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinden görüntü bilgisi çıkarmanın amacı nedir?

C: Bir PDF belgesinden görüntü bilgilerinin çıkarılması, belgedeki görüntülerin boyutlarına, çözünürlüğüne ve diğer niteliklerine ilişkin bilgiler sağlar. Bu bilgiler görüntü işleme, analiz veya optimizasyon görevleri için kullanılabilir.

#### S: Aspose.PDF for .NET, bir PDF belgesinden görüntü bilgilerinin çıkarılmasına nasıl yardımcı olur?

C: Aspose.PDF for .NET, bir PDF belgesinin görüntüleri de dahil olmak üzere içeriğine erişmek ve bunları analiz etmek için araçlar sağlar. Sağlanan kod, çeşitli operatörler kullanılarak görüntü bilgilerinin nasıl çıkarılacağını ve görüntüleneceğini gösterir.

#### S: Bu yöntem kullanılarak ne tür görüntü bilgileri çıkarılabilir?

C: Bu yöntem, bir PDF belgesindeki görüntüler için ölçeklendirilmiş boyutlar, çözünürlük ve görüntü adları gibi bilgileri çıkarmanıza ve görüntülemenize olanak tanır.

#### S: Kod, bir PDF belgesindeki görüntüyle ilgili işleçleri nasıl tanımlar ve işler?

C: Kod, PDF belgesinin belirli bir sayfasındaki operatörler arasında yinelenir. Görüntü işlemleri, dönüştürmeler ve işlemeyle ilgili operatörleri tanımlar ve işler.

#### S: Varsayılan çözünürlüğün önemi nedir ve kodda nasıl kullanılır?

C: Varsayılan çözünürlük, görüntülerin gerçek çözünürlüğünü hesaplamak için referans noktası olarak kullanılır. Kod, her görüntünün çözünürlüğünü, boyutlarına ve varsayılan çözünürlük ayarına göre hesaplar.

#### S: Çıkarılan görüntü bilgileri gerçek dünya senaryolarında nasıl kullanılabilir?

C: Çıkarılan görüntü bilgileri, görüntü kalitesi değerlendirmesi, görüntü optimizasyonu, görüntü küçük resimleri oluşturma ve görüntüyle ilgili karar verme süreçlerini kolaylaştırmak gibi görevler için kullanılabilir.

#### S: Görüntüyle ilgili ek nitelikleri çıkarmak için kodu değiştirebilir miyim?

C: Evet, görüntülerin renk alanı, piksel derinliği veya görüntü türü gibi ek niteliklerini çıkarmak için kodu özelleştirebilirsiniz.

#### S: Görüntü bilgisi çıkarma süreci kaynak yoğun mu yoksa zaman alıcı mı?

C: Görüntü bilgisi çıkarma süreci verimlidir ve performans açısından optimize edilmiştir; kaynak kullanımı ve işlem süresi üzerinde minimum etki sağlar.

#### S: Geliştiriciler PDF belgelerinden görüntü bilgilerini tanımlayıp çıkarmaktan nasıl yararlanabilir?

C: Geliştiriciler, PDF belgelerindeki görüntülerin özelliklerine ilişkin içgörüler kazanarak görüntü işleme, işleme ve optimizasyon konusunda bilinçli kararlar almalarını sağlayabilir.

#### S: Bu yöntem, resim içeren PDF belgelerinin toplu işlenmesi için kullanılabilir mi?

C: Evet, bu yöntem birden çok sayfa veya belgeyi yineleyerek, görüntü bilgilerini çıkararak ve görüntüyle ilgili görevleri gerçekleştirerek toplu işleme için genişletilebilir.