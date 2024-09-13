---
title: إضافة تلميح الأدوات إلى النص في ملف PDF
linktitle: إضافة تلميح الأدوات إلى النص في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة تلميحات الأدوات إلى النص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 90
url: /ar/net/programming-with-text/add-tooltip-to-text/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة تلميحات الأدوات إلى نص في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إضافة تلميحات الأدوات إلى النص فيه، أضف ما يلي باستخدام التوجيهات في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: إنشاء مستند نموذجي يحتوي على نص
 إنشاء جديد`Document`كائن وإضافة صفحات تحتوي على أجزاء نصية. في الكود المقدم، تتم إضافة جزءين نصيين إلى المستند مع نص الإرشاد الخاص بكل منهما.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## الخطوة 5: افتح المستند وابحث عن أجزاء النص
 قم بتحميل المستند الذي تم إنشاؤه باستخدام`Document` منشئ والعثور على أجزاء النص التي تحتاج إلى تلميحات الأدوات باستخدام`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## الخطوة 6: إضافة تلميحات الأدوات إلى أجزاء النص
 قم بالتنقل عبر أجزاء النص المستخرجة وإنشاء أزرار غير مرئية في مواضعها. قم بتعيين نص التلميح المطلوب إلى`AlternateName` ممتلكات`ButtonField`. أضف حقول الأزرار إلى نموذج المستند.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## الخطوة 7: كرر ذلك لأجزاء نصية إضافية تحتوي على تلميحات أدوات طويلة
كرر الخطوتين 5 و6 لأجزاء النص التي تحتوي على تلميحات أدوات طويلة. عدّل معايير البحث ونص التلميح وفقًا لذلك.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## الخطوة 8: احفظ المستند المعدل
 احفظ مستند PDF المعدّل باستخدام`Save` طريقة`Document` هدف.

```csharp
document. Save(outputFile);
```

### عينة من كود المصدر لإضافة تلميح الأدوات إلى النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// إنشاء مستند نموذجي يحتوي على نص
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// فتح مستند يحتوي على نص
Document document = new Document(outputFile);
//إنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// قبول الممتص لصفحات الوثيقة
document.Pages.Accept(absorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragments = absorber.TextFragments;
// التنقل عبر الشظايا
foreach (TextFragment fragment in textFragments)
{
	// إنشاء زر غير مرئي في موضع جزء النص
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// سيتم عرض قيمة AlternateName كإشارة توضيحية بواسطة تطبيق المشاهد
	field.AlternateName = "Tooltip for text.";
	// إضافة حقل الزر إلى المستند
	document.Form.Add(field);
}
// ستكون الخطوة التالية عبارة عن عينة من تلميحات الأدوات الطويلة جدًا
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// تعيين نص طويل جدًا
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// حفظ المستند
document.Save(outputFile);
```

## خاتمة
لقد نجحت في إضافة تلميحات الأدوات إلى النص في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

## الأسئلة الشائعة

#### س: ما هو التركيز في هذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على إضافة تلميحات الأدوات إلى النص داخل ملف PDF باستخدام مكتبة Aspose.PDF for .NET. يوضح كود المصدر C# المقدم الخطوات المطلوبة لتحقيق ذلك.

#### س: ما هي المساحات الأسماء التي تحتاج إلى استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تريد إضافة تلميحات الأدوات إلى النص فيه، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف يمكنني إنشاء مستند نموذجي يحتوي على نص؟

 أ: في الخطوة 4، ستقوم بإنشاء ملف جديد`Document` الكائن وإضافة صفحات تحتوي على أجزاء نصية. يضيف الكود المقدم جزءين نصيين مع نص إرشادي خاص بكل منهما.

#### س: كيف أفتح المستند وأجد أجزاء النص؟

 أ: في الخطوة 5، ستقوم بتحميل المستند الذي تم إنشاؤه باستخدام`Document` المنشئ والعثور على أجزاء النص التي تتطلب تلميحات الأدوات باستخدام`TextFragmentAbsorber`.

#### س: كيف أضيف تلميحات الأدوات إلى أجزاء النص؟

 أ: في الخطوة 6، ستنتقل عبر أجزاء النص المستخرجة وتنشئ أزرارًا غير مرئية في مواضعها. يتم تعيين نص التلميح إلى`AlternateName` ممتلكات`ButtonField`، والتي تتم إضافتها إلى نموذج المستند.

#### س: كيف يمكنني تكرار العملية لأجزاء النص الإضافية ذات تلميحات الأدوات الطويلة؟

أ: بالنسبة لأجزاء النص التي تحتوي على تلميحات أدوات طويلة، كرر الخطوتين 5 و6. عدّل معايير البحث ونص التلميح وفقًا لذلك.

#### س: كيف أحفظ المستند المعدل؟

 أ: في الخطوة 8، ستحفظ مستند PDF المعدّل باستخدام`Save` طريقة`Document` هدف.

#### س: ما هو الدرس الرئيسي المستفاد من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم كيفية تحسين مستند PDF الخاص بك عن طريق إضافة تلميحات الأدوات إلى النص باستخدام Aspose.PDF for .NET. يمكن أن يوفر هذا معلومات إضافية قيمة للقراء عند تفاعلهم مع محتوى PDF.