---
title: تضمين الخط
linktitle: تضمين الخط
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تضمين الخطوط في ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة. تأكد من عرض المستندات الخاصة بك بشكل صحيح على أي جهاز.
type: docs
weight: 120
url: /ar/net/programming-with-document/embedfont/
---

في هذا البرنامج التعليمي ، سنناقش كيفية تضمين الخطوط في ملف PDF باستخدام Aspose.PDF لـ .NET. Aspose.PDF for .NET مكتبة قوية تتيح للمطورين إنشاء مستندات PDF وتحريرها ومعالجتها برمجيًا. توفر هذه المكتبة مجموعة كبيرة من الميزات للعمل مع مستندات PDF ، بما في ذلك إضافة النصوص والصور والجداول وغير ذلك الكثير. يعد دمج الخطوط في ملف PDF مطلبًا شائعًا للمطورين الذين يرغبون في ضمان عرض ملف PDF بشكل صحيح على أجهزة مختلفة ، بغض النظر عما إذا كانت الخطوط المطلوبة مثبتة على تلك الأجهزة أم لا.

## الخطوة 1: إنشاء تطبيق C # Console جديد
للبدء ، قم بإنشاء تطبيق C # Console جديد في Visual Studio. يمكنك تسميته ما شئت. بمجرد إنشاء المشروع ، تحتاج إلى إضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد Aspose.PDF Namespace
أضف السطر التالي من التعليمات البرمجية أعلى ملف C # لاستيراد مساحة الاسم Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: تحميل ملف PDF موجود
لتضمين الخطوط في ملف PDF موجود ، تحتاج إلى تحميل هذا الملف باستخدام فئة المستند. يوضح الكود التالي كيفية تحميل ملف PDF موجود:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملف PDF موجود
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 4: كرر عبر جميع الصفحات
بمجرد تحميل ملف PDF ، ستحتاج إلى التكرار خلال جميع الصفحات في المستند. لكل صفحة ، تحتاج إلى التحقق من استخدام أي خطوط ، وإذا كان الأمر كذلك ، فأنت بحاجة إلى تضمين هذه الخطوط. يوضح الكود التالي كيفية التكرار خلال جميع الصفحات في ملف PDF وتضمين الخطوط:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // تحقق مما إذا كان الخط مضمّنًا بالفعل
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // تحقق من وجود كائنات النموذج
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // تحقق مما إذا كان الخط مضمنًا
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## الخطوة 5: احفظ مستند PDF
بمجرد دمج جميع الخطوط في ملف PDF ، ستحتاج إلى حفظ المستند. يوضح الكود التالي كيفية حفظ ملف PDF:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لـ Embed Font باستخدام Aspose.PDF لـ .NET

إليك التعليمات البرمجية المصدر الكاملة لدمج خط باستخدام Aspose.PDF for .NET.


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//قم بتحميل ملفات PDF موجودة
Document doc = new Document(dataDir + "input.pdf");

// كرر من خلال جميع الصفحات
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// تحقق مما إذا كان الخط مضمّنًا بالفعل
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// تحقق من وجود كائنات النموذج
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// تحقق مما إذا كان الخط مضمنًا
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## خاتمة
في هذه المقالة ، ناقشنا كيفية تضمين الخطوط في ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF ، بما في ذلك إضافة الخطوط وتضمينها. يعد دمج الخطوط في ملف PDF خطوة مهمة لضمان عرض المستند بشكل صحيح على أجهزة مختلفة ، بغض النظر عما إذا كانت الخطوط المطلوبة مثبتة على تلك الأجهزة
