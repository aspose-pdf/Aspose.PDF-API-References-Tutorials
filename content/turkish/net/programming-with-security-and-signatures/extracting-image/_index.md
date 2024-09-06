---
title: Görüntüyü Çıkarma
linktitle: Görüntüyü Çıkarma
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinden kolayca resim çıkarın.
type: docs
weight: 70
url: /tr/net/programming-with-security-and-signatures/extracting-image/
---
Bir PDF belgesinden resim çıkarmak birçok durumda yararlı olabilir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu kullanarak resimleri kolayca çıkarabilirsiniz:

## Adım 1: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. İşte gerekli içe aktarma yönergeleri:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Adım 2: Belgeler klasörüne giden yolu ayarlayın

 Bu adımda, görüntüyü çıkarmak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Değiştir`"YOUR DOCUMENTS DIRECTORY"` Aşağıdaki kodda belgeler klasörünüzün gerçek yolunu bulabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Adım 3: PDF belgesinden görseli çıkarın

Şimdi aşağıdaki kodu kullanarak PDF belgesinden görüntüyü çıkaracağız:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

Bu örnekte, PDF belgesindeki formun her alanında döngü gerçekleştiriyoruz. Bir imza alanı bulunursa, ilişkili resmi ayıklayıp bir JPEG dosyasına kaydediyoruz.

### .NET için Aspose.PDF kullanarak Görüntü Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinden resim çıkarmak için adım adım bir kılavuzunuz var. Bu kodu kendi projelerinize entegre ederek resim çıkarabilir ve gerektiğinde kullanabilirsiniz.

Gelişmiş görüntü çıkarma ve PDF belge düzenleme özellikleri hakkında daha fazla bilgi edinmek için resmi Aspose.PDF belgelerine göz atmayı unutmayın.


### SSS

#### S: Aspose.PDF for .NET yeni başlayanlar için uygun mu?

C: C# programlama konusunda bir miktar bilgi sahibi olmak faydalı olacaktır ancak eğitimimiz başlangıç seviyesindekilere uygun olarak tasarlanmıştır ve her adımda size rehberlik eder.

#### S: Birden fazla görseli aynı anda çıkarabilir miyim?

A: Kesinlikle! Döngüleri uygulayarak ve verilen kodu uyarlayarak, tek bir PDF belgesinden birden fazla resim çıkarabilirsiniz.

#### S: Aspose.PDF for .NET görüntü çıkarma için tek çözüm müdür?

C: Başka araçlar da mevcut olsa da Aspose.PDF for .NET, verimliliği ve kapsamlı özellikleriyle ünlüdür.

#### S: Çıkarılan görselleri ticari amaçla kullanabilir miyim?

C: Evet, çıkardığınız görselleri ticari projeleriniz de dahil olmak üzere ihtiyaç duyduğunuzda kullanabilirsiniz.

#### S: Aspose.PDF ile PDF düzenleme hakkında daha fazla kaynağı nerede bulabilirim?

A: Aspose.PDF for .NET ile gelişmiş PDF düzenleme konusunda zengin kaynaklar ve içgörüler için resmi belgelerimizi ziyaret edin.