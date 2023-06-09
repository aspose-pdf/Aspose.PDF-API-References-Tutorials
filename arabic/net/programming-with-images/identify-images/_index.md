---
title: التعرف على الصور
linktitle: التعرف على الصور
second_title: Aspose.PDF لمرجع .NET API
description: تعرف بسهولة على الصور في ملف PDF وحدد نوع لونها باستخدام Aspose.PDF for .NET.
type: docs
weight: 150
url: /ar/net/programming-with-images/identify-images/
---

سيأخذك هذا الدليل خطوة بخطوة حول كيفية التعرف على الصور في ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 تأكد من تعيين دليل المستند الصحيح. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تهيئة العدادات

في هذه الخطوة ، سنقوم بتهيئة عدادات الصور ذات التدرج الرمادي وصور RGB.

```csharp
int grayscaled = 0; // عداد للصور ذات التدرج الرمادي
int rdg = 0; // عداد لصور RGB
```

## الخطوة 3: افتح مستند PDF

 في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## الخطوة 4: تصفح صفحات المستند

في هذه الخطوة ، سنتصفح جميع صفحات مستند PDF ونتعرف على الصور الموجودة في كل صفحة.

```csharp
foreach(Page page in document.Pages)
{
```

## الخطوة 5: استرداد مواضع الصور

 في هذه الخطوة ، سوف نستخدم`ImagePlacementAbsorber` لاسترداد مواضع الصور في كل صفحة.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## الخطوة 6: عد الصور وحدد نوع لونها

في هذه الخطوة ، سنقوم بحساب عدد الصور في كل صفحة وتحديد نوع لونها (تدرج الرمادي أو RGB).

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

### عينة من التعليمات البرمجية المصدر لتحديد الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// عداد للصور ذات التدرج الرمادي
int grayscaled = 0;
// عداد لصور RGB
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// احصل على عدد الصور على صفحة معينة
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Document.Pages [29]. قبول (القيمة المطلقة) ؛
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

## خاتمة

تهنئة ! لقد نجحت في تحديد الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. تم عد الصور وتحديد نوع لونها (تدرج الرمادي أو RGB). يمكنك الآن استخدام هذه المعلومات لاحتياجاتك الخاصة.