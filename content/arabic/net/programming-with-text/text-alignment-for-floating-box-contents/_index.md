---
title: محاذاة النص لمحتويات المربع العائم في ملف PDF
linktitle: محاذاة النص لمحتويات المربع العائم في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية محاذاة النص داخل المربعات العائمة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 520
url: /ar/net/programming-with-text/text-alignment-for-floating-box-contents/
---
يشرح هذا البرنامج التعليمي كيفية محاذاة النص داخل المربعات العائمة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل متابعة البرنامج التعليمي، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف ما يلي باستخدام التوجيهات في بداية ملف C# الخاص بك لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: إنشاء مستند جديد

 إنشاء جديد`Document` هدف:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## الخطوة 5: إنشاء مربعات عائمة تحتوي على أجزاء نصية

 إنشاء متعددة`FloatingBox` كائنات ذات محاذاة رأسية ومحاذاة أفقية مختلفة:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 تعديل النص والنمط من`TextFragment` الكائنات حسب الرغبة.

## الخطوة 6: احفظ مستند PDF

احفظ مستند PDF المعدل:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 تأكد من استبدال`"FloatingBox_alignment_review_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لمحاذاة النص لمحتويات المربع العائم باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية محاذاة النص داخل المربعات العائمة في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من إعداد المشروع وحتى حفظ المستند المعدل. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لتخصيص محاذاة النص داخل المربعات العائمة في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "محاذاة النص لمحتويات المربع العائم في ملف PDF"؟

ج: يهدف البرنامج التعليمي "محاذاة النص لمحتويات المربع العائم في ملف PDF" إلى توجيه المستخدمين حول كيفية محاذاة النص داخل المربعات العائمة في مستند PDF باستخدام Aspose.PDF لـ .NET. يوفر البرنامج التعليمي إرشادات خطوة بخطوة ونماذج تعليمات برمجية C# لتوضيح العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في محاذاة النص داخل المربعات العائمة؟

ج: يساعد هذا البرنامج التعليمي المستخدمين على فهم كيفية استخدام Aspose.PDF لـ .NET لمحاذاة النص داخل المربعات العائمة في مستند PDF. باتباع الخطوات المتوفرة وأمثلة التعليمات البرمجية، يمكن للمستخدمين تخصيص المحاذاة الرأسية والأفقية للنص داخل المربعات العائمة.

#### س: ما هي المتطلبات الأساسية المطلوبة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، تحتاج إلى تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو تثبيته في مشروعك باستخدام NuGet.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET. يمكّنك هذا من الاستفادة من ميزات المكتبة للعمل مع مستندات PDF ومحاذاة النص داخل المربعات العائمة.

#### س: هل يمكنني استخدام هذا البرنامج التعليمي لمحاذاة النص داخل أي نوع من المربعات العائمة؟

ج: نعم، يوفر هذا البرنامج التعليمي إرشادات حول كيفية محاذاة النص داخل المربعات العائمة في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام نماذج التعليمات البرمجية المتوفرة لتخصيص المحاذاة الرأسية والأفقية للنص داخل المربعات العائمة.

#### س: كيف يمكنني تحديد محاذاة النص داخل مربع عائم؟

 ج: يوضح البرنامج التعليمي كيفية الإنشاء`FloatingBox`الكائنات وتعيينها`VerticalAlignment` و`HorizontalAlignment` خصائص للتحكم في محاذاة النص الموجود. يمكنك ضبط هذه الخصائص وفقًا لمتطلباتك.

#### س: كيف يمكنني تخصيص مظهر الصناديق العائمة؟

 ج: يمكنك تخصيص مظهر المربعات العائمة عن طريق تعديل خصائص مثل الحد والحجم ومحتوى النص. يوفر البرنامج التعليمي نماذج تعليمات برمجية توضح كيفية إنشاء وتصميم ملف`FloatingBox` أشياء.

#### س: هل يمكنني إضافة مربعات عائمة متعددة بمحاذاة مختلفة في نفس مستند PDF؟

 ج: نعم، يوضح البرنامج التعليمي كيفية إنشاء عدة`FloatingBox` كائنات ذات محاذاة رأسية وأفقية مختلفة وإضافتها إلى نفس مستند PDF. يتيح لك هذا رؤية تأثيرات المحاذاة المختلفة داخل نفس المستند.

#### س: كيف يمكنني حفظ مستند PDF المعدل؟

 ج: لحفظ مستند PDF المعدل، يمكنك استخدام الملف`Save` طريقة`Document` هدف. يوفر البرنامج التعليمي نماذج تعليمات برمجية توضح كيفية حفظ مستند PDF الناتج.