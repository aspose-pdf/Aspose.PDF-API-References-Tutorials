---
title: إضافة نص مع ألوان التظليل في ملف PDF
linktitle: إضافة نص مع ألوان التظليل في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة نص بألوان تظليل في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 80
url: /ar/net/programming-with-text/add-text-with-shading-colors/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة نص بألوان تظليل في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إضافة نص فيه بألوان تظليل، أضف ما يلي باستخدام التوجيه الموجود أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: قم بتحميل مستند PDF
 قم بتحميل مستند PDF الموجود باستخدام الملف`Document` منشئ وتوفير المسار إلى ملف الوثيقة.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // الكود يذهب هنا...
}
```

## الخطوة 5: ابحث عن النص المراد تعديله
 يستخدم`TextFragmentAbsorber` للعثور على النص المطلوب داخل المستند. في الكود المقدم، يتم البحث عن النص "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## الخطوة 6: تعيين لون التظليل للنص
 إنشاء جديد`Color` كائن بمساحة ألوان نمطية وحدد ألوان التظليل المتدرجة. تخصيص هذا اللون ل`ForegroundColor` ملكية`TextState` التابع`TextFragment` هدف.

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

## الخطوة 8: احفظ مستند PDF المعدل
 احفظ مستند PDF المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لإضافة نص مع ألوان التظليل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// قم بإنشاء لون جديد باستخدام مساحة ألوان النمط
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## خاتمة
لقد نجحت في إضافة نص بألوان تظليل إلى مستند PDF الخاص بك باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز الرئيسي لهذا البرنامج التعليمي؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية إضافة نص بألوان تظليل إلى ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي مساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية حيث تريد إضافة نص بألوان تظليل، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، حدد موقع السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني تحميل مستند PDF موجود؟

 ج: في الخطوة 4، ستقوم بتحميل مستند PDF موجود باستخدام ملف`Document` المنشئ وتوفير المسار إلى ملف المستند:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // الكود يذهب هنا...
}
```

#### س: كيف يمكنني العثور على نص معين وتعديله داخل مستند PDF؟

 ج: في الخطوة 5، ستستخدم`TextFragmentAbsorber`للعثور على النص المطلوب داخل المستند. ومن ثم يمكنك تعديل خصائصه:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### س: كيف يمكنني ضبط ألوان التظليل للنص؟

 ج: في الخطوة 6، ستقوم بإنشاء ملف جديد`Color` كائن بمساحة ألوان نمطية وحدد ألوان التظليل المتدرجة. تخصيص هذا اللون ل`ForegroundColor` ملكية`TextState` التابع`TextFragment` هدف:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### س: هل يمكنني تطبيق تنسيق إضافي للنص على النص المعدل؟

 ج: نعم، في الخطوة 7، يمكنك تطبيق تنسيق إضافي للنص مثل التسطير عن طريق تعديل خصائص`TextState` هدف:

```csharp
textFragment.TextState.Underline = true;
```

#### س: كيف يمكنني حفظ مستند PDF المعدل؟

 ج: في الخطوة 8، ستحفظ مستند PDF المعدل باستخدام ملف`Save` طريقة`Document` هدف:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية تحسين مستند PDF الخاص بك عن طريق إضافة نص بألوان تظليل باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا مفيدًا بشكل خاص لتسليط الضوء على محتوى نصي معين والتأكيد عليه داخل ملفات PDF الخاصة بك.