---
title: مواضع الصور
linktitle: مواضع الصور
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET لوضع الصور في مستند PDF.
type: docs
weight: 170
url: /ar/net/programming-with-images/image-placements/
---

في هذا البرنامج التعليمي ، سنستخدم مكتبة Aspose.PDF لـ .NET للعمل مع مستندات PDF وتنفيذ العمليات على الصور. سنقوم بتحميل مستند PDF ، واستخراج معلومات وضع الصورة ، واسترداد الصور بأبعادها المرئية.

## الخطوة الأولى: تهيئة البيئة
قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك بما يلي:
- Aspose.PDF for .NET مثبتة على جهازك.
- مشروع AC # جاهز للاستخدام.

## الخطوة الثانية: تحميل مستند PDF
للبدء ، نحتاج إلى تحميل مستند PDF الذي نريد معالجته. تأكد من أن لديك المسار الصحيح للدليل الذي يحتوي على مستند PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل ملف PDF المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك الذي يحتوي على ملف PDF.

## الخطوة 3: استخراج معلومات الموضع من الصور
 الآن بعد أن قمنا بتحميل مستند PDF ، يمكننا استخراج معلومات الموضع من الصور. سوف نستخدم`ImagePlacementAbsorber`لاستيعاب مواقع الصور من الصفحة الأولى من المستند.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// قم بتحميل محتوى الصفحة الأولى
doc.Pages[1].Accept(abs);
```

لقد استخرجنا الآن معلومات موضع الصورة من الصفحة الأولى من المستند.

## الخطوة 4: استرجاع الصور ذات الأبعاد المرئية
سنقوم الآن باسترداد الصور بأبعادها المرئية من معلومات الموضع التي استخرجناها سابقًا.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // احصل على خصائص الصورة
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // استرجع الصورة بأبعاد مرئية
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // احصل على الصورة من الموارد
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // قم بإنشاء صورة ذات أبعاد فعلية
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

في هذه الحلقة ، نسترجع خصائص كل صورة ، مثل العرض والارتفاع وإحداثيات X و Y للركن الأيسر السفلي ، والدقة الأفقية والرأسية. ثم نسترجع كل صورة بأبعادها المرئية باستخدام معلومات الموضع.

### نموذج التعليمات البرمجية المصدر لمواضع الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل ملف PDF المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// قم بتحميل محتويات الصفحة الأولى
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// احصل على خصائص الصورة
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// استرجع الصورة ذات الأبعاد المرئية
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// استرجاع الصورة من الموارد
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//إنشاء صورة نقطية بأبعاد فعلية
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية استخدام Aspose.PDF لـ .NET لتنفيذ مواضع الصور في مستند PDF. أوضحنا كود المصدر C # المقدم ، والذي يسمح لك بتحميل مستند PDF ، واستخراج معلومات الموضع من الصور ، واسترداد الصور بأبعادها المرئية. لا تتردد في تجربة المزيد مع Aspose.PDF لاستكشاف ميزاته العديدة الأخرى.