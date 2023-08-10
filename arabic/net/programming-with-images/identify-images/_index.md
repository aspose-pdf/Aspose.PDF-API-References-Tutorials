---
title: التعرف على الصور في ملف PDF
linktitle: التعرف على الصور في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك التعرف بسهولة على الصور في ملف PDF وتحديد نوع لونها باستخدام Aspose.PDF for .NET.
type: docs
weight: 150
url: /ar/net/programming-with-images/identify-images/
---
سيأخذك هذا الدليل خطوة بخطوة حول كيفية تحديد الصور في ملف PDF باستخدام Aspose.PDF for .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

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

### الأسئلة الشائعة للتعرف على الصور في ملف PDF

#### س: ما هو الغرض من تحديد الصور في مستند PDF؟

ج: يساعد تحديد الصور في مستند PDF المستخدمين على تحليل الصور وتصنيفها بناءً على نوع اللون (تدرج الرمادي أو RGB). يمكن أن تكون هذه المعلومات مفيدة لأغراض مختلفة ، مثل معالجة الصور أو تحليل البيانات أو مراقبة الجودة.

#### س: كيف يساعد Aspose.PDF for .NET في تحديد الصور ضمن مستند PDF؟

 ج: يوفر Aspose.PDF for .NET عملية مباشرة لفتح مستند PDF ، والتكرار من خلال صفحاته ، وتحديد الصور باستخدام`ImagePlacementAbsorber` فصل.

#### س: ما أهمية التفريق بين الصور ذات التدرج الرمادي وصورة RGB؟

ج: يساعد التمييز بين الصور ذات التدرج الرمادي وصور RGB في فهم تكوين ألوان الصور داخل مستند PDF. تحتوي الصور ذات التدرج الرمادي على ظلال من الرمادي فقط ، بينما تتكون صور RGB من قنوات اللون الأحمر والأخضر والأزرق.

#### س: كيف يتم حساب الصور ذات التدرج الرمادي و RGB وتعريفها باستخدام Aspose.PDF لـ .NET؟

 ج: إن`ImagePlacementAbsorber` يتم استخدام class لاسترداد مواضع الصور في كل صفحة. ال`GetColorType()` ثم يتم تطبيق الطريقة على كل موضع صورة لتحديد ما إذا كانت تدرج الرمادي أو RGB.

#### س: هل يمكنني تعديل الكود لأداء إجراءات إضافية بناءً على نوع لون الصورة؟

ج: نعم ، يمكنك تخصيص الكود لتنفيذ إجراءات محددة بناءً على نوع لون الصورة. على سبيل المثال ، يمكنك استخراج الصور ذات التدرج الرمادي لمزيد من المعالجة أو تطبيق تقنيات تحسين مختلفة بناءً على نوع اللون.

####  س: كيف يعمل ملف`ImagePlacementAbsorber` class contribute to identifying images?

 ج: إن`ImagePlacementAbsorber` يقوم class بمسح الصفحة بحثًا عن مواضع الصور ، مما يسمح لك باسترداد معلومات حول الصور ، بما في ذلك نوع ألوانها.

#### س: هل عدد الصور المحددة تراكمي عبر كل صفحات مستند PDF؟

ج: نعم ، عدد الصور تراكمي عبر جميع الصفحات. يتكرر الرمز من خلال كل صفحة من صفحات مستند PDF ويقوم بحساب الصور الموجودة في كل صفحة.

#### س: هل يمكنني استخدام تعريف الصورة هذا لأتمتة المهام المتعلقة بالصور في مستندات PDF؟

ج: نعم ، يمكن أن يكون تحديد الصور في مستندات PDF مفيدًا لأتمتة المهام مثل استخراج الصور أو تحويلها أو معالجتها بناءً على نوع اللون.

#### س: كيف تفيد عملية التعرف على الصور هذه معالجة مستندات PDF؟

ج: يوفر التعرف على الصور رؤى قيمة في تكوين ألوان الصور ، مما يتيح فهمًا أفضل ومعالجة مستندات PDF التي تحتوي على صور.