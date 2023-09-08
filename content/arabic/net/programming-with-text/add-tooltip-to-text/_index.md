---
title: إضافة تلميح الأدوات إلى النص في ملف PDF
linktitle: إضافة تلميح الأدوات إلى النص في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة تلميحات الأدوات إلى النص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 90
url: /ar/net/programming-with-text/add-tooltip-to-text/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة تلميحات الأدوات إلى النص في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة تلميحات الأدوات إلى النص، قم بإضافة ما يلي باستخدام التوجيهات الموجودة في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء مستند نموذجي يحتوي على نص
 إنشاء جديد`Document` كائن وإضافة صفحات مع أجزاء النص. في الكود المقدم، تتم إضافة جزأين من النص إلى المستند مع نص تلميح الأداة المعني.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## الخطوة 5: افتح المستند وابحث عن أجزاء النص
 قم بتحميل المستند الذي تم إنشاؤه باستخدام ملف`Document` منشئ وابحث عن أجزاء النص التي تحتاج إلى استخدام تلميحات الأدوات`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## الخطوة 6: إضافة تلميحات الأدوات إلى أجزاء النص
 قم بالمرور عبر أجزاء النص المستخرجة وقم بإنشاء أزرار غير مرئية في مواضعها. قم بتعيين نص تلميح الأداة المطلوب إلى`AlternateName` ملكية`ButtonField`. قم بإضافة حقول الزر إلى نموذج المستند.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## الخطوة 7: كرر ذلك مع أجزاء النص الإضافية باستخدام تلميحات الأدوات الطويلة
كرر الخطوتين 5 و6 لأجزاء النص التي تحتوي على تلميحات أدوات طويلة. قم بتعديل معايير البحث ونص تلميح الأدوات وفقًا لذلك.

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
 احفظ مستند PDF المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
document. Save(outputFile);
```

### نموذج التعليمات البرمجية المصدر لإضافة تلميح الأدوات إلى النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// إنشاء وثيقة نموذجية مع النص
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// فتح المستند مع النص
Document document = new Document(outputFile);
// قم بإنشاء كائن TextAbsorter للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// قبول الممتص لصفحات الوثيقة
document.Pages.Accept(absorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragments = absorber.TextFragments;
// حلقة من خلال الشظايا
foreach (TextFragment fragment in textFragments)
{
	// إنشاء زر غير مرئي في موضع جزء النص
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// سيتم عرض قيمة AlternateName كتلميح أداة بواسطة تطبيق العارض
	field.AlternateName = "Tooltip for text.";
	// إضافة حقل زر إلى المستند
	document.Form.Add(field);
}
// التالي سيكون عينة من تلميح الأدوات الطويل جدًا
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// قم بتعيين نص طويل جدًا
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

#### س: ما هو محور هذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على إضافة تلميحات الأدوات إلى النص داخل ملف PDF باستخدام Aspose.PDF لمكتبة .NET. يوضح كود مصدر C# المقدم الخطوات المطلوبة لتحقيق ذلك.

#### س: ما هي مساحات الأسماء التي يجب استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية حيث تريد إضافة تلميحات الأدوات إلى النص، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني إنشاء مستند نموذجي يحتوي على نص؟

 ج: في الخطوة 4، ستقوم بإنشاء ملف جديد`Document` كائن وإضافة صفحات مع أجزاء النص. يضيف الكود المقدم جزأين من النص مع نص تلميح الأداة المعني.

#### س: كيف يمكنني فتح المستند والعثور على أجزاء النص؟

 ج: في الخطوة 5، ستقوم بتحميل المستند الذي تم إنشاؤه باستخدام ملف`Document` منشئ وابحث عن أجزاء النص التي تتطلب تلميحات الأدوات باستخدام ملف`TextFragmentAbsorber`.

#### س: كيف يمكنني إضافة تلميحات الأدوات إلى أجزاء النص؟

 ج: في الخطوة 6، ستتنقل عبر أجزاء النص المستخرجة وتنشئ أزرارًا غير مرئية في مواضعها. يتم تعيين نص تلميح الأداة إلى`AlternateName` ملكية`ButtonField`، والذي يتم إضافته إلى نموذج المستند.

#### س: كيف يمكنني تكرار العملية لأجزاء نصية إضافية ذات تلميحات أدوات طويلة؟

ج: بالنسبة لأجزاء النص التي تحتوي على تلميحات أدوات طويلة، كرر الخطوتين 5 و6. قم بتعديل معايير البحث ونص تلميح الأدوات وفقًا لذلك.

#### س: كيف أحفظ الوثيقة المعدلة؟

 ج: في الخطوة 8، ستحفظ مستند PDF المعدل باستخدام ملف`Save` طريقة`Document` هدف.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية تحسين مستند PDF الخاص بك عن طريق إضافة تلميحات الأدوات إلى النص باستخدام Aspose.PDF لـ .NET. يمكن أن يوفر هذا معلومات إضافية قيمة للقراء عندما يتفاعلون مع محتوى PDF.