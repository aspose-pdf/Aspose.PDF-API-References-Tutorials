---
title: تضمين الخطوط القياسية من النوع 1 في ملف PDF
linktitle: تضمين الخطوط القياسية من النوع 1 في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تضمين الخطوط القياسية من النوع 1 في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 140
url: /ar/net/programming-with-text/embed-standard-type-1fonts/
---
سيرشدك هذا البرنامج التعليمي خلال عملية تضمين الخطوط القياسية من النوع 1 في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد تضمين الخطوط القياسية من النوع 1 فيه، أضف ما يلي باستخدام التوجيه الموجود في أعلى الملف:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: قم بتحميل مستند PDF الموجود
 قم بتحميل مستند PDF موجود باستخدام الملف`Document`منشئ وتمرير المسار إلى ملف PDF الإدخال.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## الخطوة 5: قم بتعيين خاصية EmbedStandardFonts
 تعيين`EmbedStandardFonts` خاصية الوثيقة ل`true` لتمكين تضمين الخطوط القياسية من النوع 1.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## الخطوة 6: تضمين الخطوط في كل صفحة
 قم بالمراجعة خلال كل صفحة من مستند PDF وتحقق مما إذا كانت الخطوط مضمنة بالفعل. إذا لم يكن الأمر كذلك، قم بتعيين`IsEmbedded` الملكية ل`true` لتضمين الخط.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## الخطوة 7: احفظ مستند PDF المحدث
 احفظ مستند PDF المحدث باستخدام الملف`Save` طريقة`Document` كائن، وتحديد مسار ملف الإخراج.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لتضمين الخطوط القياسية من النوع 1 باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل مستند PDF موجود
Document pdfDocument = new Document(dataDir + "input.pdf");
// قم بتعيين خاصية EmbedStandardFonts للمستند
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// تحقق مما إذا كان الخط مضمنًا بالفعل
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## خاتمة
لقد نجحت في تضمين خطوط Type 1 القياسية في مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ ملف PDF المحدث مع الخطوط المضمنة في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو محور هذا البرنامج التعليمي؟

ج: يوفر هذا البرنامج التعليمي دليلاً خطوة بخطوة لتضمين الخطوط القياسية من النوع 1 في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. يوضح كود مصدر C# المصاحب الإجراءات اللازمة.

#### س: ما هي مساحة الاسم التي أحتاج إلى استيرادها؟

ج: في ملف التعليمات البرمجية الذي تنوي تضمين خطوط النوع 1 القياسية فيه، قم بتضمين مساحة الاسم التالية في أعلى الملف:

```csharp
using Aspose.Pdf;
```

#### س: كيف أحدد دليل المستندات؟

 ج: تحديد موقع الخط`string dataDir = "YOUR DOCUMENT DIRECTORY";` في التعليمات البرمجية واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني تحميل مستند PDF موجود؟

 ج: في الخطوة 4، ستقوم بتحميل مستند PDF موجود باستخدام ملف`Document` منشئ وتوفير المسار إلى ملف PDF الإدخال.

####  س: ما هو الغرض من`EmbedStandardFonts` property?

 ج: في الخطوة 5، ستقوم بتعيين`EmbedStandardFonts` خاصية الوثيقة ل`true`، مما يتيح تضمين الخطوط القياسية من النوع 1.

#### س: كيف أقوم بتضمين الخطوط في كل صفحة؟

 ج: تتضمن الخطوة 6 التكرار خلال كل صفحة من مستند PDF. بالنسبة للخطوط غير المضمنة بالفعل، ستقوم بتعيين`IsEmbedded` الملكية ل`true` لتضمين الخط.

#### س: كيف يمكنني حفظ مستند PDF المحدث؟

 ج: في الخطوة 7، ستستخدم`Save` طريقة`Document` كائن لحفظ مستند PDF المحدث، مع تحديد مسار ملف الإخراج.

#### س: ما أهمية تضمين الخطوط في مستند PDF؟

ج: يضمن تضمين الخطوط تضمين الخطوط المستخدمة في ملف PDF داخل الملف نفسه. ويضمن ذلك عرضًا متسقًا للنص حتى لو لم يكن نظام المستلم مثبتًا عليه الخطوط المطلوبة.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، اكتسبت المعرفة والمهارات اللازمة لتضمين الخطوط القياسية من النوع 1 في مستند PDF باستخدام Aspose.PDF لـ .NET. وهذا يضمن العرض الصحيح للنص عبر أنظمة مختلفة.