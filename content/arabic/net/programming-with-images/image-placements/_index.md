---
title: مواضع الصور
linktitle: مواضع الصور
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لوضع الصور في مستند PDF.
type: docs
weight: 170
url: /ar/net/programming-with-images/image-placements/
---
في هذا البرنامج التعليمي، سنستخدم مكتبة Aspose.PDF لـ .NET للعمل مع مستندات PDF وتنفيذ العمليات على الصور. سنقوم بتحميل مستند PDF، واستخراج معلومات موضع الصورة، واسترجاع الصور بأبعادها المرئية.

## الخطوة 1: تهيئة البيئة
قبل البدء، تأكد من إعداد بيئة التطوير الخاصة بك بما يلي:
- Aspose.PDF لـ .NET مثبت على جهازك.
- مشروع AC# جاهز للاستخدام.

## الخطوة 2: تحميل مستند PDF
للبدء، نحتاج إلى تحميل مستند PDF الذي نريد معالجته. تأكد من أن لديك المسار الصحيح للدليل الذي يحتوي على مستند PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل مستند PDF المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الذي يحتوي على ملف PDF.

## الخطوة 3: استخراج معلومات الموضع من الصور
 الآن بعد أن قمنا بتحميل مستند PDF، يمكننا استخراج معلومات الموضع من الصور. سوف نستخدم`ImagePlacementAbsorber`لاستيعاب مواقع الصور من الصفحة الأولى من المستند.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// قم بتحميل محتوى الصفحة الأولى
doc.Pages[1].Accept(abs);
```

لقد استخرجنا الآن معلومات موضع الصورة من الصفحة الأولى من المستند.

## الخطوة الرابعة: استرجاع الصور ذات الأبعاد المرئية
الآن سوف نقوم باسترجاع الصور بأبعادها المرئية من معلومات الموضع التي استخرجناها سابقا.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // الحصول على خصائص الصورة
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // استرجاع الصورة ذات الأبعاد المرئية
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // الحصول على الصورة من الموارد
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // قم بإنشاء صورة بأبعاد فعلية
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

في هذه الحلقة، نقوم باسترداد خصائص كل صورة، مثل العرض والارتفاع وإحداثيات X وY للزاوية اليسرى السفلية، والدقة الأفقية والرأسية. ومن ثم نقوم باسترجاع كل صورة بأبعادها الظاهرة باستخدام معلومات الموضع.

### نموذج التعليمات البرمجية المصدر لمواضع الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل مستند PDF المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// تحميل محتويات الصفحة الأولى
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// الحصول على خصائص الصورة
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// استرجاع الصورة ذات الأبعاد المرئية
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
تهنئة ! لقد تعلمت الآن كيفية استخدام Aspose.PDF لـ .NET لتنفيذ مواضع الصور في مستند PDF. لقد شرحنا كود مصدر C# المقدم، والذي يسمح لك بتحميل مستند PDF، واستخراج معلومات الموضع من الصور، واسترداد الصور بأبعادها المرئية. لا تتردد في تجربة المزيد مع Aspose.PDF لاستكشاف ميزاته العديدة الأخرى.

### الأسئلة الشائعة

#### س: ما هو الغرض من استخراج معلومات موضع الصورة من مستند PDF باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك استخراج معلومات موضع الصورة استرداد موضع الصور وأبعادها ودقتها داخل مستند PDF. هذه المعلومات ضرورية لمعالجة الصور وتحليلها بدقة.

#### س: كيف يسهل Aspose.PDF for .NET استخراج معلومات موضع الصورة من مستند PDF؟

 ج: يوفر Aspose.PDF لـ .NET`ImagePlacementAbsorber`فئة، والتي يمكن استخدامها لاستيعاب تفاصيل موضع الصورة من مستند PDF. يوضح الكود المقدم كيفية استخدام هذه الفئة لاسترداد معلومات موضع الصورة.

#### س: ما الذي يمكن استخدام معلومات موضع الصورة فيه في سيناريوهات العالم الحقيقي؟

ج: تعتبر معلومات موضع الصورة ذات قيمة لمهام مثل ضمان المحاذاة الدقيقة للصورة، وحساب أبعاد الصورة، والتحقق من جودة الصورة، وإنشاء تقارير حول استخدام الصورة داخل مستند PDF.

#### س: كيف تضمن عينة التعليمات البرمجية الاستخراج الدقيق لمعلومات موضع الصورة؟

 ج: يستخدم نموذج التعليمات البرمجية`ImagePlacementAbsorber` فئة لاجتياز محتويات صفحة محددة، وتحديد مواضع الصور، واسترداد سماتها، مثل العرض والارتفاع والإحداثيات والدقة.

#### س: هل يمكن توسيع الكود لمعالجة الصور عبر صفحات أو مستندات متعددة؟

ج: نعم، يمكن توسيع التعليمات البرمجية من خلال التكرار عبر صفحات أو مستندات متعددة لاستخراج معلومات موضع الصورة وتنفيذ المهام المتعلقة بالصورة.

#### س: كيف يقوم الكود باسترجاع الصور بأبعادها المرئية بناء على معلومات الموضع؟

ج: يستخرج نموذج التعليمات البرمجية بيانات الصورة من الموارد، وينشئ صورة نقطية بأبعاد فعلية، ويوفر خصائص مثل العرض والارتفاع والإحداثيات والدقة.

#### س: هل هذا الأسلوب فعال بالنسبة لمستندات PDF الكبيرة التي تحتوي على العديد من الصور؟

ج: نعم، تم تحسين Aspose.PDF for .NET للأداء واستخدام الموارد. فهو يستخرج معلومات موضع الصورة بكفاءة حتى من مستندات PDF الكبيرة.

#### س: كيف يمكن للمطورين الاستفادة من فهم معلومات موضع الصورة واستخدامها؟

ج: يمكن للمطورين ضمان معالجة الصور ومواءمتها وتحليلها بشكل دقيق داخل مستندات PDF. تمكنهم هذه المعلومات من إنشاء تطبيقات لمعالجة الصور وإعداد التقارير وضمان الجودة.

#### س: هل يمكن تخصيص الكود لاستخراج سمات أو بيانات وصفية إضافية متعلقة بالصورة؟

ج: بالتأكيد، يمكن تحسين التعليمات البرمجية لاستخراج سمات إضافية، مثل نوع الصورة ومساحة اللون والضغط والمزيد، من خلال استخدام الفئات والأساليب المناسبة التي يوفرها Aspose.PDF لـ .NET.

#### س: ما أهمية الاستنتاج المقدم في هذا البرنامج التعليمي؟

ج: يلخص الاستنتاج محتوى البرنامج التعليمي ويشجع على المزيد من الاستكشاف لـ Aspose.PDF لـ .NET للاستفادة من إمكاناته بما يتجاوز مواضع الصور، مما يفتح الأبواب أمام العديد من المهام المتعلقة بـ PDF.