---
title: PDF Dosyasındaki Kenarlığı Çıkar
linktitle: PDF Dosyasındaki Kenarlığı Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki kenarlığın nasıl çıkarılacağını öğrenin.
type: docs
weight: 80
url: /tr/net/programming-with-tables/extract-border/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasındaki kenarlığı nasıl çıkaracağımızı öğreneceğiz. Kaynak kodunu adım adım C# dilinde açıklayacağız. Bu eğitimin sonunda, PDF belgesinden kenarlığı nasıl çıkaracağınızı ve bir resim olarak nasıl kaydedeceğinizi öğreneceksiniz. Başlayalım!

## Adım 1: Ortamı kurma
Öncelikle, C# geliştirme ortamınızı .NET için Aspose.PDF ile kurduğunuzdan emin olun. Referansı kütüphaneye ekleyin ve gerekli ad alanlarını içe aktarın.

## Adım 2: PDF Belgesini Yükleme
Bu adımda belirtilen dosyadan PDF belgesini yüklüyoruz.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

"BELGE DİZİNİNİZ" ifadesini PDF dosyanızın bulunduğu gerçek dizinle değiştirdiğinizden emin olun.

## Adım 3: Kenar Çıkarımı
PDF belgesindeki işlemleri yineleyerek kenarlığı çıkaracağız.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Tüm içerik işlemlerini işleyin
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // İşlem türünü kontrol edin
         // ...
         // Her işlemi işlemek için kod ekleyin
     }
}
```

 Biz bir tane yaratıyoruz`graphicsState` grafik durumlarını depolamak için bir yığın, çıkarılan kenarlığı yakalamak için bir bitmap görüntüsü,`GraphicsPath` çizim yollarını ve durum ve renkleri izlemek için diğer değişkenleri depolamak için nesne.

## Adım 4: İşlem İşleme
Bu adımda belgenin her bir işlemini işleyerek kenarlığı çıkarıyoruz.

```csharp
// İşlem türünü kontrol edin
if (opSaveState != null)
{
     // Önceki durumu kaydet ve geçerli durumu yığının en üstüne it
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Mevcut durumu silin ve önceki durumu geri yükleyin
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Mevcut dönüşüm matrisini al
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Mevcut matrisi durum matrisiyle çarpın
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Son çizim noktasını güncelle
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Bir çizginin çizimini işleyin
     // ...
     // Bir çizginin çizilmesini işlemek için kod ekleyin
}
// ...
// Diğer işlemler için else if blokları ekleyin
```

İşlemin türünü koşullar kullanarak kontrol ediyoruz ve her işlem için uygun kodu çalıştırıyoruz.

## Adım 5: Yedekleme Görüntüsü
Son olarak, çıkarılan kenarlığı içeren bitmap görüntüsünü belirtilen dosyaya kaydediyoruz.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Çıktı görüntüsünü kaydetmek için doğru dizini ve dosya adını belirttiğinizden emin olun.

### .NET için Aspose.PDF kullanarak Kenarlığı Çıkarma için örnek kaynak kodu

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Varsayılan ctm matris değeri 1,0,0,1,0,0'dır
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Sistem. Çizim koordinat sistemi sol üst tabanlı iken, pdf koordinat sistemi sol alt tabanlıdır, bu nedenle ters matrisi uygulamamız gerekir
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Tüm içerik komutlarını işle
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//Önceki durumu kaydet ve geçerli durumu yığının en üstüne it
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Mevcut durumu at ve öncekini geri yükle
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
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
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Çözüm
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinden kenarlığın nasıl çıkarılacağını öğrendik. Diğer PDF belgelerinden kenarlığı çıkarmak için bu adım adım kılavuzu kullanabilirsiniz.

### PDF dosyasındaki kenarlığı çıkarmak için SSS

#### S: PDF dosyasından kenarlık çıkarma işleminin amacı nedir?

A: Bir PDF dosyasından kenarlığı çıkarmak çeşitli amaçlar için yararlı olabilir. Tablolar, diyagramlar veya grafiksel öğeler gibi belgenin yapısal öğelerini izole etmenize ve analiz etmenize olanak tanır. Çıkarılan kenarlığı, PDF belgesindeki içeriğin düzenini, boyutlarını ve konumunu belirlemek için kullanabilirsiniz.

#### S: PDF belgesindeki belirli sayfalardan veya alanlardan kenarlıkları çıkarabilir miyim?

A: Evet, PDF belgesindeki belirli sayfalardan veya bölgelerden kenarlığı çıkarmak için sağlanan C# kaynak kodunu değiştirebilirsiniz.`doc.Pages` Özel ölçütleri belirleyerek ve toplayarak, belirli sayfalardan veya ilgi alanlarından kenarlığı çıkarmayı seçebilirsiniz.

#### S: Çıktı görüntü formatını ve kalitesini nasıl özelleştirebilirim?

 A: Sağlanan C# kodunda, çıkarılan kenarlık PNG görüntüsü olarak kaydedilir. Çıktı görüntü biçimini değiştirmek istiyorsanız,`ImageFormat.Png` parametre içinde`bitmap.Save` JPEG, BMP veya GIF gibi diğer desteklenen görüntü biçimlerine yönelik yöntem. Ayrıca, gereksinimlerinize göre görüntü kalitesini veya sıkıştırma ayarlarını ayarlayabilirsiniz.

#### S: Çıkarılan kenarlık üzerinde başka hangi işlemleri yapabilirim?

A: Sınırı bir görüntü olarak çıkardıktan sonra, görüntü işleme kütüphanelerini veya algoritmalarını kullanarak daha fazla işleyebilirsiniz. Görüntüyü analiz edebilir, görüntü filtreleri uygulayabilir, desenleri tespit edebilir veya gerekirse görüntüden metin çıkarmak için OCR (Optik Karakter Tanıma) gerçekleştirebilirsiniz.

#### S: Karmaşık PDF belgelerinden kenarlıkları çıkarırken herhangi bir sınırlama veya dikkat edilmesi gereken husus var mı?

A: Çıkarma işlemi PDF belgesinin karmaşıklığına bağlı olarak değişebilir. Çok katmanlı, şeffaf veya gelişmiş grafiklere sahip karmaşık PDF'ler, kenarlığı doğru bir şekilde çıkarmak için ek işleme veya ayarlamalar gerektirebilir. Güvenilir sonuçlardan emin olmak için çıkarma işlemini çeşitli PDF belgelerinde kapsamlı bir şekilde test etmek önemlidir.