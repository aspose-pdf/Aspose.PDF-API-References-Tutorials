---
title: وضع علامة على الصورة في ملف PDF الموجود
linktitle: وضع علامة على الصورة في ملف PDF الموجود
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية وضع علامات على الصور في ملفات PDF الموجودة باستخدام Aspose.PDF لـ .NET. دليل خطوة بخطوة لتحسين إمكانية الوصول من خلال التوافق مع PDF/UA.
type: docs
weight: 210
url: /ar/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## مقدمة

في هذا البرنامج التعليمي، سنوضح لك كيفية وضع علامة على صورة في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. بحلول نهاية هذا الدليل، ستتمكن من تعيين نص بديل للصور، وضبط سمات التخطيط، وضمان امتثال ملف PDF الخاص بك لمعايير إمكانية الوصول.

## المتطلبات الأساسية

قبل أن نبدأ، دعنا نستعرض ما ستحتاجه للبدء:

-  Aspose.PDF لـ .NET: تأكد من تنزيل أحدث إصدار من Aspose.PDF لـ .NET وتثبيته.[تحميل هنا](https://releases.aspose.com/pdf/net/).
- .NET Framework: تأكد من أن لديك بيئة تطوير .NET مثل Visual Studio.
- الفهم الأساسي لبنية PDF: التعرف على عناصر بنية PDF مثل الفقرات والامتدادات والجداول والصور.
-  ترخيص صالح: يمكنك شراء ترخيص[هنا](https://purchase.aspose.com/buy) أو استخدم واحدة مؤقتة[هنا](https://purchase.aspose.com/temporary-license/).

## استيراد الحزم

للبدء في الترميز، تحتاج إلى استيراد مساحات الأسماء الأساسية من Aspose.PDF لـ .NET. سيتيح لك ذلك الوصول إلى الفئات والطرق اللازمة للتعامل مع مستند PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

الآن بعد أن هيأنا المسرح، دعنا نقسم عملية وضع العلامات على الصورة إلى خطوات متعددة.

## الخطوة 1: تحميل مستند PDF الموجود

الخطوة الأولى هي تحميل ملف PDF الذي تريد العمل عليه. يمكن أن يكون هذا أي ملف PDF يحتوي على صورة ترغب في وضع علامة عليها.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// افتح المستند
Document document = new Document(inFile);
```

-  يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لملفك.
-  ال`Document` تتيح لك الفئة تحميل ملف PDF موجود. ستقوم بتعديل ملف PDF هذا لوضع علامة على الصورة.

## الخطوة 2: الوصول إلى المحتوى المُوسوم وعناصر البنية الجذرية

بمجرد فتح ملف PDF، فإن الخطوة التالية هي الوصول إلى المحتوى المُوسوم وتحديد عنصر البنية الجذرية. وهذا أمر بالغ الأهمية لأنه يسمح لك بالتنقل عبر العناصر الموجودة في ملف PDF وإجراء التعديلات.

```csharp
// احصل على محتوى مميز وعناصر هيكل الجذر
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` يتيح الوصول إلى العناصر المنظمة في ملف PDF.
-  ال`RootElement` هو العنصر الهيكلي الأعلى، والذي يمكنك من خلاله الانتقال إلى عناصر أخرى مثل الفقرات والجداول والصور.

## الخطوة 3: تعيين عنوان مستند PDF المُوسوم

إن إضافة عنوان إلى مستند PDF المُوسوم يضمن تصنيف مستندك بشكل صحيح، وهو أمر مفيد لإمكانية الوصول إليه والامتثال لمعايير PDF/UA.

```csharp
// تعيين عنوان لمستند PDF المُوسوم
taggedContent.SetTitle("Document with images");
```

- يساعد تعيين عنوان لملف PDF الذي قمت بوضع علامة عليه على تحسين إمكانية الوصول إليه وتحسين وضوح المستند بالنسبة لقارئات الشاشة وتقنيات المساعدة.

## الخطوة 4: ابحث عن الصورة وقم بوضع علامة عليها

 الآن، دعنا نجد عنصر الصورة (المشار إليه باسم`FigureElement` في Aspose.PDF، قم بتعيين نص بديل له، وقم بتكوين سمات تخطيطه.

```csharp
// قم بالمرور عبر جميع عناصر الشكل (الصور) وقم بتعيين النص البديل وسمات التخطيط
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // تعيين نص بديل للشكل
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // إنشاء وتعيين سمة BBox (المربع المحيط)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // تعيين سمات التخطيط للشكل
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  هذا الكود يتكرر خلال كل`FigureElement` الأشياء الموجودة في البنية الجذرية، والتي تمثل الصور.
- يحدد النص البديل لإمكانية الوصول (سيستخدم قارئو الشاشة هذا لوصف الصورة).
- المربع المحدد (`BBox`تحدد إحداثيات تخطيط الصورة، مما يضمن عرضها بشكل صحيح في المستند.

## الخطوة 5: تعديل عناصر النطاق داخل الجدول

 في بعض الحالات، قد تحتاج إلى تعديل عناصر النطاق داخل جدول. هنا، سنوضح كيفية العثور على`SpanElement` ونقلها إلى فقرة.

```csharp
// العثور على عناصر الجدول والنطاق والفقرة
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// نقل عنصر الامتداد إلى الفقرة
spanElement.ChangeParentElement(paragraph);
```

-  هنا، نجد`TableElement`, `SpanElement` ، و`ParagraphElement` ضمن ملف PDF.
-  استخدام`ChangeParentElement` الطريقة هي أننا نقوم بنقل الامتداد إلى الفقرة لضمان وضع العلامات والبنية المناسبة.

## الخطوة 6: احفظ المستند وتحقق من توافقه مع PDF/UA

بمجرد إجراء كافة التغييرات، تكون الخطوة الأخيرة هي حفظ ملف PDF المحدث والتحقق مما إذا كان متوافقًا مع معايير PDF/UA.

```csharp
// احفظ مستند PDF المحدث
document.Save(outFile);

// التحقق من صحة توافق PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  ال`Validate` تتحقق الطريقة من مستند PDF مقابل معايير PDF/UA وتسجل النتائج.
- يساعد ضمان الامتثال على تحسين إمكانية الوصول وتلبية المتطلبات التنظيمية لنشر المستندات.

## خاتمة

في هذا البرنامج التعليمي، أوضحنا لك كيفية وضع علامات على الصور في ملف PDF موجود باستخدام Aspose.PDF لـ .NET. من خلال تعيين نص بديل وتعديل سمات التخطيط والتحقق من صحة المستند للتوافق مع PDF/UA، يمكنك التأكد من إمكانية الوصول إلى ملفات PDF الخاصة بك وتلبية المعايير الحديثة. يجعل Aspose.PDF من السهل العمل مع العناصر المنظمة، مما يمنحك التحكم في تخطيط المستند وإمكانية الوصول إليه.

## الأسئلة الشائعة

### ما هو استخدام Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة قوية تستخدم لإنشاء وتحرير ومعالجة مستندات PDF برمجيًا في بيئة .NET.

### كيف يمكنني التأكد من التوافق مع PDF/UA؟
 يمكنك استخدام Aspose.PDF`Validate` طريقة للتحقق من توافق PDF/UA بعد إجراء تعديلات على المستند.

### ما هو النص البديل في ملفات PDF؟
النص البديل هو وصف يضاف إلى الصور في ملفات PDF لتحسين إمكانية الوصول إليها، وخاصة للمستخدمين الذين يعتمدون على برامج قراءة الشاشة.

### هل يمكنني معالجة الجداول والامتدادات في ملف PDF باستخدام Aspose.PDF؟
نعم، يسمح لك Aspose.PDF بالتعامل مع الجداول والامتدادات والعناصر المنظمة الأخرى داخل مستند PDF.

### أين يمكنني تنزيل Aspose.PDF لـ .NET؟
 يمكنك تنزيل أحدث إصدار من Aspose.PDF لـ .NET[هنا](https://releases.aspose.com/pdf/net/).