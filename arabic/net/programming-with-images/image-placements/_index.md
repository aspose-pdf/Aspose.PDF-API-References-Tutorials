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

### التعليمات

#### س: ما هو الغرض من استخراج معلومات موضع الصورة من مستند PDF باستخدام Aspose.PDF for .NET؟

ج: يتيح لك استخراج معلومات موضع الصورة استرداد موضع الصور وأبعادها ودقتها داخل مستند PDF. هذه المعلومات ضرورية لمعالجة الصور وتحليلها بدقة.

#### س: كيف يسهل Aspose.PDF for .NET استخراج معلومات موضع الصورة من مستند PDF؟

 ج: يوفر Aspose.PDF for .NET الامتداد`ImagePlacementAbsorber`class ، والتي يمكن استخدامها لاستيعاب تفاصيل موضع الصورة من مستند PDF. يوضح الكود المقدم كيفية استخدام هذه الفئة لاسترداد معلومات وضع الصورة.

#### س: ما الذي يمكن استخدام معلومات موضع الصورة في سيناريوهات العالم الحقيقي؟

ج: تعتبر معلومات وضع الصورة ذات قيمة لمهام مثل ضمان محاذاة الصورة الدقيقة ، وحساب أبعاد الصورة ، والتحقق من جودة الصورة ، وإنشاء تقارير عن استخدام الصورة في مستند PDF.

#### س: كيف يضمن نموذج الشفرة الاستخراج الدقيق لمعلومات موضع الصورة؟

 ج: نموذج التعليمات البرمجية يستخدم`ImagePlacementAbsorber` فئة لاجتياز محتويات صفحة محددة ، وتحديد مواضع الصور ، واسترداد سماتها ، مثل العرض والارتفاع والإحداثيات والدقة.

#### س: هل يمكن تمديد الكود لمعالجة الصور عبر صفحات أو مستندات متعددة؟

ج: نعم ، يمكن تمديد الكود عن طريق التكرار عبر صفحات أو مستندات متعددة لاستخراج معلومات موضع الصورة وأداء المهام المتعلقة بالصور.

#### س: كيف يسترد الرمز الصور بأبعادها المرئية بناءً على معلومات الموضع؟

ج: يستخرج نموذج الكود بيانات الصورة من الموارد ، وينشئ صورة نقطية بالأبعاد الفعلية ، ويوفر خصائص مثل العرض والارتفاع والإحداثيات والدقة.

#### س: هل هذا الأسلوب فعال لمستندات PDF الكبيرة التي تحتوي على صور متعددة؟

ج: نعم ، تم تحسين Aspose.PDF for .NET للأداء واستخدام الموارد. يقوم باستخراج معلومات وضع الصور بكفاءة حتى من مستندات PDF الكبيرة.

#### س: كيف يمكن للمطورين الاستفادة من فهم واستخدام معلومات وضع الصورة؟

ج: يمكن للمطورين ضمان المعالجة الدقيقة للصور والمحاذاة والتحليل داخل مستندات PDF. تمكنهم هذه المعلومات من إنشاء تطبيقات لمعالجة الصور وإعداد التقارير وضمان الجودة.

#### س: هل يمكن تخصيص الكود لاستخراج سمات أو بيانات وصفية إضافية متعلقة بالصورة؟

ج: بالتأكيد ، يمكن تحسين الكود لاستخراج سمات إضافية ، مثل نوع الصورة ، ومساحة اللون ، والضغط ، وغير ذلك ، من خلال استخدام الفئات والطرق المناسبة التي يوفرها Aspose.PDF لـ .NET.

#### س: ما هي أهمية الاستنتاج المقدم في هذا البرنامج التعليمي؟

ج: تلخص الخاتمة محتوى البرنامج التعليمي وتشجع على المزيد من الاستكشاف لـ Aspose.PDF لـ .NET للاستفادة من إمكانياتها بما يتجاوز مواضع الصور ، مما يفتح الأبواب أمام المهام المختلفة المتعلقة بـ PDF.