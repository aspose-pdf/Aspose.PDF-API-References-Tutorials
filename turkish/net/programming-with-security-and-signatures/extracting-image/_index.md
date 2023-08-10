---
title: Görüntü Çıkarılıyor
linktitle: Görüntü Çıkarılıyor
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinden görüntüleri kolayca çıkarın.
type: docs
weight: 70
url: /tr/net/programming-with-security-and-signatures/extracting-image/
---
Bir PDF belgesinden görüntülerin ayıklanması birçok durumda yararlı olabilir. Aspose.PDF for .NET ile, aşağıdaki kaynak kodunu kullanarak görüntüleri kolayca çıkarabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat direktifleri:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, görüntüyü çıkartmak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"`belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## 3. Adım: Görüntüyü PDF belgesinden çıkarın

Şimdi aşağıdaki kodu kullanarak görüntüyü PDF belgesinden çıkaracağız:

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

Bu örnekte, PDF belgesindeki formun her alanında dolaşıyoruz. Bir imza alanı bulunursa, ilgili görüntüyü çıkarır ve bir JPEG dosyasına kaydederiz.

### Aspose.PDF for .NET kullanarak Görüntü Çıkarma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
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

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinden görüntüleri ayıklamak için adım adım bir kılavuza sahipsiniz. Görüntüleri çıkarmak ve gerektiğinde kullanmak için bu kodu kendi projelerinize entegre edebilirsiniz.

Gelişmiş görüntü çıkarma ve PDF belge işleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.


### SSS

#### S: Aspose.PDF for .NET yeni başlayanlar için uygun mu?

Y: C# programlamaya biraz aşina olmak faydalı olsa da eğitimimiz başlangıç seviyesinde olacak şekilde tasarlanmıştır ve her adımda size yol gösterir.

#### S: Aynı anda birden çok görüntüyü çıkarabilir miyim?

C: Kesinlikle! Döngüler uygulayarak ve sağlanan kodu uyarlayarak, tek bir PDF belgesinden birden çok görüntüyü çıkarabilirsiniz.

#### S: Görüntü çıkarma için tek çözüm Aspose.PDF for .NET mi?

Y: Kullanılabilecek başka araçlar olsa da Aspose.PDF for .NET, verimliliği ve kapsamlı özellikleriyle ünlüdür.

#### S: Çıkarılan görüntüleri ticari amaçlarla kullanabilir miyim?

C: Evet, görüntüler çıkarıldıktan sonra, ticari projeler de dahil olmak üzere gerektiğinde kullanmak üzere sizindir.

#### S: Aspose.PDF ile PDF düzenleme konusunda daha fazla kaynağı nerede bulabilirim?

C: Aspose.PDF for .NET ile gelişmiş PDF işleme hakkında zengin kaynaklar ve içgörüler için resmi belgelerimizi ziyaret edin.