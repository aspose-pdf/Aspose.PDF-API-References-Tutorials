---
title: وضع الصور
linktitle: وضع الصور
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لوضع الصور في مستند PDF.
type: docs
weight: 170
url: /ar/net/programming-with-images/image-placements/
---
في هذا البرنامج التعليمي، سنستخدم مكتبة Aspose.PDF لـ .NET للعمل مع مستندات PDF وإجراء عمليات على الصور. سنقوم بتحميل مستند PDF واستخراج معلومات وضع الصورة واسترداد الصور بأبعادها المرئية.

## الخطوة 1: إعداد البيئة
قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك بما يلي:
- تم تثبيت Aspose.PDF لـ .NET على جهازك.
- مشروع AC# جاهز للاستخدام.

## الخطوة 2: تحميل مستند PDF
للبدء، نحتاج إلى تحميل مستند PDF الذي نريد معالجته. تأكد من أن لديك المسار الصحيح للدليل الذي يحتوي على مستند PDF.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// تحميل مستند PDF المصدر
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 تأكد من الاستبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الذي يحتوي على ملف PDF.

## الخطوة 3: استخراج معلومات الموضع من الصور
 الآن بعد أن قمنا بتحميل مستند PDF، يمكننا استخراج معلومات الموضع من الصور. سنستخدم`ImagePlacementAbsorber`لاستيعاب مواقع الصور من الصفحة الأولى للمستند.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// تحميل محتوى الصفحة الأولى
doc.Pages[1].Accept(abs);
```

لقد قمنا الآن باستخراج معلومات وضع الصورة من الصفحة الأولى للمستند.

## الخطوة 4: استرداد الصور ذات الأبعاد المرئية
سنقوم الآن باسترجاع الصور مع أبعادها المرئية من معلومات الموضع التي استخرجناها سابقًا.

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

     // استرداد الصورة ذات الأبعاد المرئية
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // احصل على الصورة من المصادر
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // إنشاء صورة بأبعاد فعلية
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

في هذه الحلقة، نسترد خصائص كل صورة، مثل العرض والارتفاع وإحداثيات X وY للزاوية اليسرى السفلية والدقة الأفقية والرأسية. ثم نسترد كل صورة بأبعادها المرئية باستخدام معلومات الموضع.

### عينة من كود المصدر لوضع الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل مستند PDF المصدر
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
	// استرداد الصورة ذات الأبعاد المرئية
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// استرجاع الصورة من المصادر
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//إنشاء خريطة نقطية بأبعاد فعلية
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## خاتمة
تهانينا! لقد تعلمت الآن كيفية استخدام Aspose.PDF لـ .NET لإجراء عمليات وضع الصور في مستند PDF. لقد شرحنا الكود المصدري C# المقدم، والذي يسمح لك بتحميل مستند PDF، واستخراج معلومات الوضع من الصور، واسترداد الصور بأبعادها المرئية. لا تتردد في تجربة المزيد مع Aspose.PDF لاستكشاف العديد من ميزاته الأخرى.

### الأسئلة الشائعة

#### س: ما هو الغرض من استخراج معلومات وضع الصورة من مستند PDF باستخدام Aspose.PDF لـ .NET؟

أ: يتيح لك استخراج معلومات وضع الصورة استرجاع موضع الصور وأبعادها ودقتها داخل مستند PDF. تعد هذه المعلومات ضرورية لمعالجة الصور وتحليلها بدقة.

#### س: كيف يسهل Aspose.PDF for .NET استخراج معلومات وضع الصورة من مستند PDF؟

 أ: يوفر Aspose.PDF لـ .NET`ImagePlacementAbsorber`فئة يمكن استخدامها لاستيعاب تفاصيل وضع الصورة من مستند PDF. يوضح الكود المقدم كيفية استخدام هذه الفئة لاسترجاع معلومات وضع الصورة.

#### س: ما هي المعلومات التي يمكن استخدامها لتحديد موضع الصورة في السيناريوهات الواقعية؟

أ: تُعد معلومات وضع الصورة مفيدة للمهام مثل ضمان محاذاة الصورة بدقة، وحساب أبعاد الصورة، والتحقق من جودة الصورة، وإنشاء تقارير حول استخدام الصورة داخل مستند PDF.

#### س: كيف تضمن عينة التعليمات البرمجية استخراجًا دقيقًا لمعلومات وضع الصورة؟

 أ: تستخدم عينة التعليمات البرمجية`ImagePlacementAbsorber` فئة لاجتياز محتويات صفحة محددة، وتحديد مواضع الصور، واسترجاع سماتها، مثل العرض والارتفاع والإحداثيات والدقة.

#### س: هل يمكن توسيع الكود لمعالجة الصور عبر صفحات أو مستندات متعددة؟

ج: نعم، يمكن توسيع الكود عن طريق التكرار عبر صفحات أو مستندات متعددة لاستخراج معلومات وضع الصورة وأداء المهام المتعلقة بالصورة.

#### س: كيف يقوم الكود باسترجاع الصور مع أبعادها المرئية بناءً على معلومات الموضع؟

أ: تقوم عينة التعليمات البرمجية باستخراج بيانات الصورة من الموارد، وإنشاء صورة نقطية بالأبعاد الفعلية، وتوفير خصائص مثل العرض والارتفاع والإحداثيات والدقة.

#### س: هل هذا النهج فعال لمستندات PDF الكبيرة التي تحتوي على عدد كبير من الصور؟

ج: نعم، تم تحسين Aspose.PDF for .NET لتحسين الأداء واستخدام الموارد. فهو يستخرج معلومات وضع الصور بكفاءة حتى من مستندات PDF كبيرة الحجم.

#### س: كيف يمكن للمطورين الاستفادة من فهم معلومات وضع الصور والاستفادة منها؟

أ: يمكن للمطورين ضمان معالجة الصور ومحاذاتها وتحليلها بدقة داخل مستندات PDF. تمكنهم هذه المعلومات من إنشاء تطبيقات لمعالجة الصور وإعداد التقارير وضمان الجودة.

#### س: هل يمكن تخصيص الكود لاستخراج سمات أو بيانات وصفية إضافية متعلقة بالصورة؟

ج: بالتأكيد، يمكن تحسين الكود لاستخراج سمات إضافية، مثل نوع الصورة، ومساحة اللون، والضغط، والمزيد، من خلال الاستفادة من الفئات والطرق المناسبة التي يوفرها Aspose.PDF لـ .NET.

#### س: ما أهمية الاستنتاج المقدم في هذا البرنامج التعليمي؟

أ: يلخص الاستنتاج محتوى البرنامج التعليمي ويشجع على المزيد من الاستكشاف لـ Aspose.PDF لـ .NET للاستفادة من قدراته التي تتعدى وضع الصور، مما يفتح الأبواب أمام العديد من المهام المتعلقة بـ PDF.