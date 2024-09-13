---
title: تضمين الخطوط القياسية من النوع 1 في ملف PDF
linktitle: تضمين الخطوط القياسية من النوع 1 في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تضمين الخطوط القياسية من النوع 1 في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 140
url: /ar/net/programming-with-text/embed-standard-type-1fonts/
---
سيرشدك هذا البرنامج التعليمي خلال عملية تضمين الخطوط القياسية من النوع 1 في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد تضمين الخطوط القياسية من النوع 1 فيه، أضف التوجيه التالي باستخدام في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: تحميل مستند PDF الموجود
 قم بتحميل مستند PDF موجود باستخدام`Document`المنشئ وتمرير المسار إلى ملف PDF المدخل.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## الخطوة 5: تعيين خاصية EmbedStandardFonts
 ضبط`EmbedStandardFonts` ملكية الوثيقة`true` من أجل تمكين تضمين الخطوط القياسية من النوع 1.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## الخطوة 6: تضمين الخطوط في كل صفحة
 قم بالتنقل عبر كل صفحة من مستند PDF وتحقق مما إذا كانت الخطوط مُضمنة بالفعل. إذا لم يكن الأمر كذلك، فقم بتعيين`IsEmbedded` الممتلكات ل`true` لتضمين الخط.

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
 احفظ مستند PDF المحدث باستخدام`Save` طريقة`Document` الكائن الذي يحدد مسار ملف الإخراج.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### عينة من كود المصدر لتضمين الخطوط القياسية من النوع 1 باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل مستند PDF موجود
Document pdfDocument = new Document(dataDir + "input.pdf");
// تعيين خاصية EmbedStandardFonts للمستند
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// التحقق مما إذا كان الخط مُضمنًا بالفعل
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
لقد قمت بنجاح بتضمين الخطوط القياسية من النوع 1 في مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ ملف PDF المحدث بالخطوط المضمنة في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو التركيز في هذا البرنامج التعليمي؟

ج: يوفر هذا البرنامج التعليمي دليلاً خطوة بخطوة لتضمين الخطوط القياسية من النوع 1 في ملف PDF باستخدام مكتبة Aspose.PDF for .NET. يوضح كود المصدر C# المصاحب الإجراءات اللازمة.

#### س: ما هي المساحة الإسمية التي أحتاج إلى استيرادها؟

أ: في ملف الكود الذي تنوي تضمين الخطوط القياسية من النوع 1 فيه، قم بتضمين مساحة الأسماء التالية في أعلى الملف:

```csharp
using Aspose.Pdf;
```

#### س: كيف أحدد دليل المستند؟

 أ: حدد موقع الخط`string dataDir = "YOUR DOCUMENT DIRECTORY";` في الكود واستبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف يمكنني تحميل مستند PDF موجود؟

 أ: في الخطوة 4، ستقوم بتحميل مستند PDF موجود باستخدام`Document` المنشئ وتوفير المسار إلى ملف PDF المدخل.

####  س: ما هو الغرض من`EmbedStandardFonts` property?

 أ: في الخطوة 5، ستقوم بتعيين`EmbedStandardFonts` ملكية الوثيقة`true`، مما يتيح تضمين الخطوط القياسية من النوع 1.

#### س: كيف أقوم بتضمين الخطوط في كل صفحة؟

 أ: تتضمن الخطوة 6 تكرار كل صفحة من مستند PDF. بالنسبة للخطوط التي لم يتم تضمينها بالفعل، ستقوم بتعيين`IsEmbedded` الممتلكات ل`true` لتضمين الخط.

#### س: كيف يمكنني حفظ مستند PDF المحدث؟

 أ: في الخطوة 7، سوف تستخدم`Save` طريقة`Document` كائن لحفظ مستند PDF المحدث، مع تحديد مسار ملف الإخراج.

#### س: ما أهمية تضمين الخطوط في مستند PDF؟

أ: يضمن تضمين الخطوط تضمين الخطوط المستخدمة في ملف PDF داخل الملف نفسه. وهذا يضمن عرض النص بشكل متسق حتى إذا لم يكن نظام المستلم يحتوي على الخطوط المطلوبة.

#### س: ما هو الدرس الرئيسي المستفاد من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، اكتسبت المعرفة والمهارات اللازمة لتضمين الخطوط القياسية من النوع 1 في مستند PDF باستخدام Aspose.PDF لـ .NET. وهذا يضمن عرض النص بشكل صحيح عبر أنظمة مختلفة.