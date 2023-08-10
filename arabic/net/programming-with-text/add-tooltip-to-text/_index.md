---
title: إضافة تلميح إلى نص
linktitle: إضافة تلميح إلى نص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة تلميحات الأدوات إلى نص في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-text/add-tooltip-to-text/
---

سيرشدك هذا البرنامج التعليمي خلال عملية إضافة تلميحات الأدوات إلى نص في مستند PDF باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد إضافة تلميحات الأدوات إلى النص ، أضف ما يلي باستخدام التوجيهات في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: قم بإنشاء نموذج مستند بنص
 إنشاء ملف`Document` الكائن وإضافة صفحات بها أجزاء نصية. في الكود المتوفر ، تمت إضافة جزأين نصيين إلى المستند مع نص تلميح الأدوات الخاص بهما.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## الخطوة 5: افتح المستند وابحث عن أجزاء النص
 قم بتحميل المستند الذي تم إنشاؤه باستخدام ملف`Document` المنشئ والعثور على أجزاء النص التي تحتاج إلى استخدام تلميحات الأدوات`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## الخطوة 6: أضف تلميحات الأدوات إلى أجزاء النص
 قم بالتكرار خلال أجزاء النص المستخرجة وأنشئ أزرارًا غير مرئية في مواضعها. قم بتعيين نص تلميح الأداة المطلوب إلى ملف`AlternateName` ممتلكات`ButtonField`. أضف حقول الزر إلى نموذج المستند.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## الخطوة 7: كرر العملية للحصول على أجزاء نصية إضافية باستخدام تلميحات أدوات طويلة
كرر الخطوتين 5 و 6 لأجزاء النص باستخدام التلميحات الطويلة. قم بتعديل معايير البحث ونص تلميح الأدوات وفقًا لذلك.

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
 احفظ مستند PDF المعدل باستخدام ملف`Save` طريقة`Document` هدف.

```csharp
document. Save(outputFile);
```

### نموذج التعليمات البرمجية المصدر لـ Add Tooltip To Text باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// إنشاء وثيقة مع النص
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// افتح المستند مع النص
Document document = new Document(outputFile);
// قم بإنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// تقبل الممتص لصفحات الوثيقة
document.Pages.Accept(absorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragments = absorber.TextFragments;
// حلقة من خلال الأجزاء
foreach (TextFragment fragment in textFragments)
{
	// إنشاء زر غير مرئي في موضع جزء النص
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// سيتم عرض قيمة AlternateName كتلميح أداة بواسطة تطبيق عارض
	field.AlternateName = "Tooltip for text.";
	// أضف حقل الزر إلى المستند
	document.Form.Add(field);
}
// التالي سيكون قطعة من تلميح الأدوات الطويل جدًا
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
// احفظ المستند
document.Save(outputFile);
```

## خاتمة
لقد نجحت في إضافة تلميحات أدوات إلى نص في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.