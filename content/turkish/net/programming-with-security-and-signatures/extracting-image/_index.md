---
title: Görüntü Çıkarılıyor
linktitle: Görüntü Çıkarılıyor
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgelerinden görüntüleri kolayca çıkarın.
type: docs
weight: 70
url: /tr/net/programming-with-security-and-signatures/extracting-image/
---
Bir PDF belgesinden görüntülerin çıkarılması birçok durumda yararlı olabilir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu kullanarak görüntüleri kolayca çıkarabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifleri şunlardır:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, görüntüyü çıkarmak istediğiniz PDF dosyasının bulunduğu klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## 3. Adım: PDF belgesinden görüntüyü çıkarın

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

Bu örnekte, PDF belgesindeki formun her alanında döngü yapıyoruz. İmza alanı bulunursa ilgili görseli çıkartıp JPEG dosyasına kaydediyoruz.

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

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesinden görüntü ayıklamak için adım adım bir kılavuza sahipsiniz. Görüntüleri çıkarmak ve gerektiğinde kullanmak için bu kodu kendi projelerinize entegre edebilirsiniz.

Gelişmiş görüntü çıkarma ve PDF belge işleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.


### SSS'ler

#### S: Aspose.PDF for .NET yeni başlayanlar için uygun mudur?

C: C# programlamaya biraz aşina olmak faydalı olsa da, eğitimimiz yeni başlayanlar için uygun olacak şekilde tasarlanmıştır ve her adımda size yol gösterir.

#### S: Aynı anda birden fazla görüntüyü çıkarabilir miyim?

C: Kesinlikle! Döngüler uygulayarak ve sağlanan kodu uyarlayarak tek bir PDF belgesinden birden fazla görüntü çıkarabilirsiniz.

#### S: Aspose.PDF for .NET görüntü çıkarma için tek çözüm mü?

C: Başka araçlar da mevcut olsa da Aspose.PDF for .NET, verimliliği ve kapsamlı özellikleriyle ünlüdür.

#### S: Çıkarılan görselleri ticari amaçlarla kullanabilir miyim?

C: Evet, görüntüler çıkarıldıktan sonra ticari projeler de dahil olmak üzere ihtiyaç duyduğunuzda kullanabilirsiniz.

#### S: Aspose.PDF ile PDF manipülasyonu hakkında daha fazla kaynağı nerede bulabilirim?

C: Aspose.PDF for .NET ile gelişmiş PDF manipülasyonu hakkında çok sayıda kaynak ve bilgi için resmi belgelerimizi ziyaret edin.