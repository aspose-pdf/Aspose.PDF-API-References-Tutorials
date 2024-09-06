---
title: تحديد الصور في ملف PDF
linktitle: تحديد الصور في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك التعرف بسهولة على الصور الموجودة في ملف PDF وتحديد نوع لونها باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 150
url: /ar/net/programming-with-images/identify-images/
---
سيرشدك هذا الدليل خطوة بخطوة إلى كيفية التعرف على الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. تأكد من إعداد بيئتك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

 تأكد من تعيين دليل المستند الصحيح. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تهيئة العدادات

في هذه الخطوة، سنقوم بتهيئة العدادات للصور ذات التدرج الرمادي والصور ذات الألوان الأحمر والأخضر والأزرق.

```csharp
int grayscaled = 0; // عداد للصور ذات التدرج الرمادي
int rdg = 0; // عداد لصور RGB
```

## الخطوة 3: افتح مستند PDF

 في هذه الخطوة سوف نقوم بفتح مستند PDF باستخدام`Document` فئة Aspose.PDF. استخدم`Document` منشئ ومرر المسار إلى مستند PDF.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## الخطوة 4: تصفح صفحات المستندات

في هذه الخطوة سوف نقوم بفحص جميع صفحات مستند PDF وتحديد الصور الموجودة في كل صفحة.

```csharp
foreach(Page page in document.Pages)
{
```

## الخطوة 5: استرداد مواضع الصور

 في هذه الخطوة سوف نستخدم`ImagePlacementAbsorber` لاسترجاع مواضع الصور في كل صفحة.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## الخطوة 6: عد الصور وتحديد نوع لونها

في هذه الخطوة سنقوم بحساب عدد الصور في كل صفحة وتحديد نوع لونها (رمادي أو RGB).

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

### عينة من كود المصدر لتحديد الصور باستخدام Aspose.PDF لـ .NET 
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
		// احصل على عدد الصور الموجودة في صفحة معينة
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// المستند.الصفحات[29].قبول(abs);
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

تهانينا! لقد نجحت في التعرف على الصور في ملف PDF باستخدام Aspose.PDF لـ .NET. تم إحصاء الصور وتحديد نوع لونها (تدرج الرمادي أو RGB). يمكنك الآن استخدام هذه المعلومات لتلبية احتياجاتك المحددة.

### الأسئلة الشائعة حول التعرف على الصور في ملف PDF

#### س: ما هو الغرض من التعرف على الصور في مستند PDF؟

أ: يساعد تحديد الصور في مستند PDF المستخدمين على تحليل الصور وتصنيفها بناءً على نوع لونها (تدرج الرمادي أو RGB). يمكن أن تكون هذه المعلومات مفيدة لأغراض مختلفة، مثل معالجة الصور أو تحليل البيانات أو مراقبة الجودة.

#### س: كيف يساعد Aspose.PDF for .NET في تحديد الصور داخل مستند PDF؟

 أ: يوفر Aspose.PDF لـ .NET عملية مباشرة لفتح مستند PDF، والتنقل عبر صفحاته، وتحديد الصور باستخدام`ImagePlacementAbsorber` فصل.

#### س: ما أهمية التمييز بين الصور ذات التدرج الرمادي والصور ذات الألوان الأحمر والأخضر والأزرق؟

ج: يساعد التمييز بين الصور ذات التدرج الرمادي والصور ذات الألوان الأحمر والأخضر والأزرق في فهم تكوين الألوان في الصور داخل مستند PDF. تحتوي الصور ذات التدرج الرمادي على ظلال رمادية فقط، بينما تتكون الصور ذات الألوان الأحمر والأخضر والأزرق من قنوات ألوان حمراء وخضراء وزرقاء.

#### س: كيف يتم حساب وتحديد الصور ذات التدرج الرمادي والألوان RGB باستخدام Aspose.PDF لـ .NET؟

 أ: ال`ImagePlacementAbsorber` يتم استخدام الفئة لاسترداد مواضع الصور في كل صفحة.`GetColorType()` يتم بعد ذلك تطبيق الطريقة على كل موضع للصورة لتحديد ما إذا كانت باللون الرمادي أو RGB.

#### س: هل يمكنني تعديل الكود لأداء إجراءات إضافية بناءً على نوع لون الصورة؟

ج: نعم، يمكنك تخصيص الكود لأداء إجراءات محددة بناءً على نوع لون الصورة. على سبيل المثال، يمكنك استخراج الصور ذات التدرج الرمادي لمزيد من المعالجة أو تطبيق تقنيات تحسين مختلفة بناءً على نوع اللون.

####  س: كيف يتم ذلك؟`ImagePlacementAbsorber` class contribute to identifying images?

 أ: ال`ImagePlacementAbsorber` تقوم الفئة بمسح الصفحة بحثًا عن مواضع الصور، مما يسمح لك باسترجاع المعلومات حول الصور، بما في ذلك نوع لونها.

#### س: هل عدد الصور التي تم تحديدها تراكمي في جميع صفحات مستند PDF؟

ج: نعم، يتم حساب عدد الصور بشكل تراكمي عبر جميع الصفحات. يتكرر الكود في كل صفحة من مستند PDF ويحسب عدد الصور في كل صفحة.

#### س: هل يمكنني استخدام تعريف الصورة هذا لأتمتة المهام المتعلقة بالصور في مستندات PDF؟

ج: نعم، يمكن أن يكون التعرف على الصور في مستندات PDF مفيدًا لأتمتة المهام مثل استخراج الصور أو تحويلها أو معالجتها بناءً على نوع اللون.

#### س: كيف يمكن لعملية التعرف على الصورة أن تفيد معالجة مستندات PDF؟

أ: يوفر التعرف على الصور معلومات قيمة حول تكوين الألوان في الصور، مما يتيح فهم ومعالجة مستندات PDF التي تحتوي على صور بشكل أفضل.