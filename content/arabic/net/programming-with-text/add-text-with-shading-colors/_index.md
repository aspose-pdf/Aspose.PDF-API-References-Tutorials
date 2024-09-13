---
title: إضافة نص بألوان التظليل في ملف PDF
linktitle: إضافة نص بألوان التظليل في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة نص بألوان التظليل في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 80
url: /ar/net/programming-with-text/add-text-with-shading-colors/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة نص بألوان تظليل في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إضافة نص بألوان التظليل فيه، أضف التوجيه التالي باستخدام في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: تحميل مستند PDF
 قم بتحميل مستند PDF الموجود باستخدام`Document` المنشئ وتوفير المسار إلى ملف المستند.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // الكود يذهب هنا...
}
```

## الخطوة 5: ابحث عن النص الذي تريد تعديله
يستخدم`TextFragmentAbsorber` للعثور على النص المطلوب داخل المستند، في الكود المقدم، يبحث عن النص "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## الخطوة 6: تعيين لون التظليل للنص
 إنشاء جديد`Color` كائن به مساحة ألوان نمطية وحدد ألوان التظليل المتدرجة. قم بتعيين هذا اللون إلى`ForegroundColor` ممتلكات`TextState` التابع`TextFragment` هدف.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## الخطوة 7: تطبيق تنسيق النص الإضافي (اختياري)
 يمكنك تطبيق تنسيق إضافي على جزء النص، مثل التسطير، عن طريق تعديل خصائص`TextState` هدف.

```csharp
textFragment.TextState.Underline = true;
```

## الخطوة 8: احفظ مستند PDF المعدّل
 احفظ مستند PDF المعدّل باستخدام`Save` طريقة`Document` هدف.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### عينة من كود المصدر لإضافة نص بألوان التظليل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// إنشاء لون جديد باستخدام مساحة الألوان النمطية
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## خاتمة
لقد نجحت في إضافة نص بألوان تظليل إلى مستند PDF الخاص بك باستخدام Aspose.PDF لـ .NET. يمكنك الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز الرئيسي لهذا البرنامج التعليمي؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية إضافة نص بألوان تظليل إلى ملف PDF باستخدام مكتبة Aspose.PDF for .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي المساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تريد إضافة نص بألوان التظليل فيه، قم باستيراد المساحات التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، حدد السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف يمكنني تحميل مستند PDF موجود؟

 أ: في الخطوة 4، ستقوم بتحميل مستند PDF موجود باستخدام`Document` المنشئ وتوفير المسار إلى ملف المستند:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // الكود يذهب هنا...
}
```

#### س: كيف يمكنني العثور على نص معين وتعديله داخل مستند PDF؟

 أ: في الخطوة 5، سوف تستخدم`TextFragmentAbsorber` للعثور على النص المطلوب داخل المستند، ثم يمكنك تعديل خصائصه:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### س: كيف يمكنني تعيين ألوان التظليل للنص؟

 أ: في الخطوة 6، ستقوم بإنشاء ملف جديد`Color` كائن به مساحة ألوان نمطية وحدد ألوان التظليل المتدرجة. قم بتعيين هذا اللون إلى`ForegroundColor` ممتلكات`TextState` التابع`TextFragment` هدف:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### س: هل يمكنني تطبيق تنسيق نص إضافي على النص المعدل؟

ج: نعم، في الخطوة 7، يمكنك تطبيق تنسيق نص إضافي مثل التسطير عن طريق تعديل خصائص`TextState` هدف:

```csharp
textFragment.TextState.Underline = true;
```

#### س: كيف أحفظ مستند PDF المعدل؟

 أ: في الخطوة 8، ستحفظ مستند PDF المعدّل باستخدام`Save` طريقة`Document` هدف:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### س: ما هو الدرس الرئيسي المستفاد من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية تحسين مستند PDF الخاص بك عن طريق إضافة نص بألوان تظليل باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا مفيدًا بشكل خاص لتسليط الضوء على محتوى نصي معين داخل ملفات PDF الخاصة بك والتأكيد عليه.