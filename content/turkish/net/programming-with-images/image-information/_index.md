---
title: PDF Dosyasında Resim Bilgileri
linktitle: PDF Dosyasında Resim Bilgileri
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki resim bilgilerini çıkarın.
type: docs
weight: 160
url: /tr/net/programming-with-images/image-information/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak PDF dosyasındaki resimler hakkında bilgi çıkarmayı adım adım gösterecektir. Ortamınızı önceden ayarladığınızdan ve aşağıdaki adımları izlediğinizden emin olun:

## Adım 1: Belge dizinini tanımlayın

 Doğru belge dizinini ayarladığınızdan emin olun. Değiştir`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynak PDF dosyasını yükleyin

 Bu adımda, kaynak PDF dosyasını kullanarak yükleyeceğiz`Document` Aspose.PDF sınıfı. Kullanın`Document` oluşturucuyu kullanın ve PDF belgesinin yolunu geçirin.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Adım 3: Varsayılan çözünürlüğü ayarlayın

Bu adımda, resimler için varsayılan çözünürlüğü ayarlayacağız. Örnekte, varsayılan çözünürlük 72 olarak ayarlanmıştır.

```csharp
int defaultResolution = 72;
```

## Adım 4: Nesneleri ve sayaçları başlatın

Bu adımda, görüntü bilgilerini almak için gerekli nesneleri ve sayaçları başlatacağız.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Adım 5: Belgenin ilk sayfasındaki operatörler arasında geçiş yapın

Bu adımda, görüntüyle ilgili işlemleri belirlemek için belgenin ilk sayfasındaki operatörleri inceleyeceğiz.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Adım 6: Operatörleri yönetin ve görüntü bilgilerini çıkarın

Bu adımda farklı operatör tiplerini yöneteceğiz ve görüntüler hakkında bilgi çıkaracağız.

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
     // Dönüşüm matrisini uygulayın
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
// Görüntüler için Do işlemini yönetin
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Resmi al
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Resmin boyutlarını al
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Yukarıdaki bilgilere dayanarak çözünürlüğü hesaplayın
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Görüntü bilgilerini görüntüle
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### .NET için Aspose.PDF kullanılarak Görüntü Bilgileri için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Kaynak PDF dosyasını yükleyin
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Görüntü için varsayılan çözünürlüğü tanımlayın
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Resim adlarını tutacak dizi listesi nesnesini tanımlayın
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Yığına bir nesne ekle
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Belgenin ilk sayfasındaki tüm operatörleri alın
foreach (Operator op in doc.Pages[1].Contents)
{
	// Dönüşümleri daha önce ayarlananlara geri döndürmek için GSave/GRestore operatörlerini kullanın
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Geçerli dönüşüm matrisini tanımladığı şekilde ConcatenateMatrix nesnesini örneklendirin.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Kaynaklardan nesneleri çizen Do operatörünü oluşturun. Form nesnelerini ve Görüntü nesnelerini çizer
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Önceki durumu kaydet ve geçerli durumu yığının en üstüne it
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Mevcut durumu at ve öncekini geri yükle
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
		// Eğer bu bir resim çizim operatörü ise
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// İlk pdf sayfasının resimlerini tutmak için XImage nesnesi oluşturun
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Görüntü boyutlarını al
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Resmin Yükseklik ve Genişlik bilgilerini alın
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Yukarıdaki bilgilere dayanarak çözünürlüğü hesaplayın
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Her bir görüntünün Boyut ve Çözünürlük bilgilerini görüntüleyin
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF dosyasındaki görüntü bilgilerini nasıl çıkaracağınızı öğrendiniz. Bu bilgileri uygulamalarınızda çeşitli görüntü işleme görevlerinde kullanabilirsiniz.

### PDF dosyasındaki resim bilgilerine ilişkin SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinden görüntü bilgilerini çıkarmanın amacı nedir?

A: Bir PDF belgesinden görüntü bilgilerinin çıkarılması, belgedeki görüntülerin boyutları, çözünürlüğü ve diğer nitelikleri hakkında fikir verir. Bu bilgiler, görüntü işleme, analiz veya optimizasyon görevleri için kullanılabilir.

#### S: Aspose.PDF for .NET, bir PDF belgesinden görüntü bilgilerinin çıkarılmasına nasıl yardımcı olur?

A: Aspose.PDF for .NET, görüntüleri de dahil olmak üzere bir PDF belgesinin içeriğine erişmek ve onu analiz etmek için araçlar sağlar. Sağlanan kod, çeşitli operatörler kullanılarak görüntü bilgilerinin nasıl çıkarılacağını ve görüntüleneceğini gösterir.

#### S: Bu yöntemle ne tür görüntü bilgileri çıkarılabilir?

A: Bu yöntem, bir PDF belgesindeki resimlerin ölçeklendirilmiş boyutları, çözünürlükleri ve resim adları gibi bilgileri çıkarmanıza ve görüntülemenize olanak tanır.

#### S: Kod, bir PDF belgesindeki görüntüyle ilgili operatörleri nasıl tanımlıyor ve işliyor?

A: Kod, PDF belgesinin belirtilen bir sayfasındaki operatörler arasında yineleme yapar. Görüntü işlemleri, dönüşümler ve işlemeyle ilgili operatörleri tanımlar ve işler.

#### S: Varsayılan çözünürlüğün önemi nedir ve kodda nasıl kullanılır?

A: Varsayılan çözünürlük, görüntülerin gerçek çözünürlüğünü hesaplamak için bir referans noktası olarak kullanılır. Kod, her görüntünün çözünürlüğünü boyutlarına ve varsayılan çözünürlük ayarına göre hesaplar.

#### S: Çıkarılan görüntü bilgileri gerçek dünya senaryolarında nasıl kullanılabilir?

A: Çıkarılan görüntü bilgileri, görüntü kalitesinin değerlendirilmesi, görüntü optimizasyonu, görüntü küçük resimlerinin oluşturulması ve görüntüyle ilgili karar alma süreçlerinin kolaylaştırılması gibi görevlerde kullanılabilir.

#### S: Ek görüntüyle ilgili nitelikleri çıkarmak için kodu değiştirebilir miyim?

C: Evet, renk alanı, piksel derinliği veya görüntü türü gibi görüntülerin ek niteliklerini çıkarmak için kodu özelleştirebilirsiniz.

#### S: Görüntü bilgisi çıkarma işlemi kaynak yoğun veya zaman alıcı mıdır?

A: Görüntü bilgisi çıkarma işlemi verimlidir ve performans açısından optimize edilmiştir; kaynak kullanımı ve işlem süresi üzerinde minimum etki sağlar.

#### S: Geliştiriciler PDF belgelerinden görüntü bilgilerini belirleyip çıkarmaktan nasıl faydalanabilir?

A: Geliştiriciler, PDF belgelerindeki görüntülerin özelliklerine ilişkin bilgi edinebilir ve bu sayede görüntü işleme, düzenleme ve optimizasyon konusunda bilinçli kararlar alabilirler.

#### S: Bu yöntem, resim içeren PDF belgelerinin toplu işlenmesinde kullanılabilir mi?

C: Evet, bu yöntem birden fazla sayfa veya belgede gezinerek, görüntü bilgilerini çıkararak ve görüntüyle ilgili görevleri gerçekleştirerek toplu işleme için genişletilebilir.