---
title: أضف نصًا بألوان التظليل
linktitle: أضف نصًا بألوان التظليل
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة نص بألوان التظليل إلى مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-text/add-text-with-shading-colors/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إضافة نص بألوان تظليل باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة نص بألوان التظليل ، أضف ما يلي باستخدام التوجيه في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: قم بتحميل مستند PDF
 قم بتحميل مستند PDF الحالي باستخدام ملف`Document` المُنشئ وتوفير المسار إلى ملف المستند.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // يظهر الرمز هنا ...
}
```

## الخطوة 5: ابحث عن النص المراد تعديله
 يستخدم`TextFragmentAbsorber` للعثور على النص المطلوب داخل المستند. في الكود المقدم ، يتم البحث عن النص "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## الخطوة 6: تعيين لون التظليل للنص
 إنشاء ملف`Color` كائن مع مساحة ألوان نمط وحدد ألوان تظليل التدرج. قم بتعيين هذا اللون لملف`ForegroundColor` ممتلكات`TextState` التابع`TextFragment` هدف.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## الخطوة 7: تطبيق تنسيق نص إضافي (اختياري)
 يمكنك تطبيق تنسيق إضافي على جزء النص ، مثل التسطير ، عن طريق تعديل خصائص ملف`TextState` هدف.

```csharp
textFragment.TextState.Underline = true;
```

## الخطوة 8: احفظ مستند PDF المعدل
 احفظ مستند PDF المعدل باستخدام ملف`Save` طريقة`Document` هدف.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Add Text With Shading Colors باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// إنشاء لون جديد مع مساحة ألوان النمط
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## خاتمة
لقد نجحت في إضافة نص بألوان تظليل إلى مستند PDF الخاص بك باستخدام Aspose.PDF for .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.