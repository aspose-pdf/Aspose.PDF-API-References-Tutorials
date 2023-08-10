---
title: تضمين خط قياسي من النوع 1
linktitle: تضمين خط قياسي من النوع 1
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تضمين خطوط Type 1 القياسية في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 140
url: /ar/net/programming-with-text/embed-standard-type-1fonts/
---

سيرشدك هذا البرنامج التعليمي خلال عملية دمج خطوط Type 1 القياسية في مستند PDF باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد تضمين خطوط Type 1 القياسية ، أضف ما يلي باستخدام التوجيه في أعلى الملف:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: قم بتحميل مستند PDF الحالي
 قم بتحميل مستند PDF موجود باستخدام ملف`Document` المُنشئ وتمرير المسار إلى ملف PDF المُدخل.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## الخطوة 5: قم بتعيين خاصية EmbedStandardFonts
 تعيين`EmbedStandardFonts` ملكية المستند إلى`true` لتمكين دمج خطوط Type 1 القياسية.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## الخطوة 6: تضمين الخطوط في كل صفحة
 قم بالتكرار خلال كل صفحة من صفحات مستند PDF وتحقق مما إذا كانت الخطوط مضمنة بالفعل. إذا لم يكن كذلك ، فاضبط`IsEmbedded` الملكية ل`true` لتضمين الخط.

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
 احفظ مستند PDF المحدث باستخدام ملف`Save` طريقة`Document` كائن ، مع تحديد مسار ملف الإخراج.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Embed Standard Type 1Fonts باستخدام Aspose.PDF for .NET 
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
			// تحقق مما إذا كان الخط مضمّنًا بالفعل
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
لقد نجحت في تضمين خطوط Type 1 القياسية في مستند PDF باستخدام Aspose.PDF for .NET. تم حفظ ملف PDF المحدث مع الخطوط المضمنة في مسار ملف الإخراج المحدد.