---
title: استبدال صفحة النص
linktitle: استبدال صفحة النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استبدال النص في صفحة معينة من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 370
url: /ar/net/programming-with-text/replace-text-page/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لاستبدال النص في صفحة معينة من مستند PDF. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل الشروع في البرنامج التعليمي ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: قم بإعداد المشروع

ابدأ بإنشاء مشروع C # جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف التعليمات التالية باستخدام التوجيهات في بداية ملف C # لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتحميل مستند PDF

 عيّن المسار إلى دليل مستند PDF الخاص بك وقم بتحميل المستند باستخدام ملف`Document` فصل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

 تأكد من استبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: البحث عن النص واستبداله

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات إدخال عبارة البحث:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 يستبدل`"text"` بالنص الفعلي الذي تريد البحث عنه واستبداله.

## الخطوة 5: حدد الصفحة الهدف

 قبول الممتص لصفحة معينة عن طريق الوصول إلى`Pages` جمع`pdfDocument` وجوه واستدعاء`Accept` طريقة:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 يستبدل`2` برقم الصفحة حيث تريد استبدال النص. لاحظ أن أرقام الصفحات تستند إلى الصفر ، لذلك`0` يمثل الصفحة الأولى.

## الخطوة 6: استرجاع أجزاء النص المستخرجة

احصل على أجزاء النص المستخرجة باستخدام ملحق`TextFragments` ممتلكات`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 7: كرر خلال أجزاء النص

قم بالتكرار خلال أجزاء النص المستردة وقم بتحديث النص والخصائص الأخرى حسب الرغبة:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 في مقتطف الشفرة أعلاه ، استبدل`"New Phrase"` مع النص البديل الذي تريد استخدامه. يمكنك أيضًا تخصيص خصائص أخرى مثل الخط وحجم الخط ولون المقدمة ولون الخلفية.

## الخطوة 8: احفظ ملف PDF المعدل

 احفظ مستند PDF المعدل في ملف جديد باستخدام امتداد`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

 تأكد من استبداله`"ReplaceTextPage_out.pdf"` باسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لـ Replace Text Page باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
//قم بإنشاء كائن TextAbsorber للعثور على جميع مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//تقبل الممتص لصفحة معينة
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الأجزاء
foreach (TextFragment textFragment in textFragmentCollection)
{
	// تحديث النص وخصائص أخرى
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية استبدال النص في صفحة معينة من مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً تفصيليًا ، بدءًا من تحميل المستند وحتى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لأتمتة استبدال النص في ملفات PDF.