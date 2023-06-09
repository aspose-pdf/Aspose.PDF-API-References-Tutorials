---
title: Görüntüleri Tanımlayın
linktitle: Görüntüleri Tanımlayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF dosyasındaki görüntüleri kolayca tanımlayın ve renk türlerini belirleyin.
type: docs
weight: 150
url: /tr/net/programming-with-images/identify-images/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki görüntüleri nasıl tanımlayacağınızı adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Doğru belge dizinini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF belgenizin bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Sayaçları başlatın

Bu adımda, gri tonlamalı görüntüler ve RGB görüntüler için sayaçları başlatacağız.

```csharp
int grayscaled = 0; // Gri tonlamalı görüntüler için sayaç
int rdg = 0; // RGB görüntüleri için sayaç
```

## 3. Adım: PDF belgesini açın

 Bu adımda, PDF belgesini kullanarak açacağız.`Document` Aspose.PDF sınıfı. Kullan`Document` yapıcı ve yolu PDF belgesine iletin.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## 4. Adım: Belge Sayfalarına Göz Atın

Bu adımda, PDF belgesinin tüm sayfalarını inceleyeceğiz ve her sayfadaki resimleri belirleyeceğiz.

```csharp
foreach(Page page in document.Pages)
{
```

## 5. Adım: Görüntü yerleşimlerini alın

 Bu adımda kullanacağımız`ImagePlacementAbsorber` her sayfadaki görüntü yerleşimlerini almak için.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## 6. Adım: Görüntüleri sayın ve renk türlerini belirleyin

Bu adımda, her sayfadaki görüntü sayısını sayacağız ve renk türlerini (gri tonlama veya RGB) belirleyeceğiz.

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### Aspose.PDF for .NET kullanarak Görüntüleri Tanımlamak için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Gri tonlamalı görüntüler için sayaç
int grayscaled = 0;
// RGB görüntüleri için sayaç
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// Belirli bir sayfadaki görüntülerin sayısını alın
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Document.Pages[29].Accept(mutlak);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF'deki görüntüleri başarıyla tanımladınız. Görüntüler sayıldı ve renk türleri (gri tonlama veya RGB) tanımlandı. Artık bu bilgileri özel ihtiyaçlarınız için kullanabilirsiniz.