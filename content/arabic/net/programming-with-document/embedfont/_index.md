---
title: تضمين الخط في ملف PDF
linktitle: تضمين الخط في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تضمين الخطوط في ملف PDF باستخدام Aspose.PDF لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة. تأكد من عرض مستنداتك بشكل صحيح على أي جهاز.
type: docs
weight: 120
url: /ar/net/programming-with-document/embedfont/
---
في هذا البرنامج التعليمي، سنناقش كيفية تضمين الخطوط في ملف PDF باستخدام Aspose.PDF لـ .NET. Aspose.PDF for .NET هي مكتبة قوية تتيح للمطورين إنشاء مستندات PDF وتحريرها ومعالجتها برمجيًا. توفر هذه المكتبة مجموعة واسعة من الميزات للعمل مع مستندات PDF، بما في ذلك إضافة النصوص والصور والجداول وغير ذلك الكثير. يعد تضمين الخطوط في ملف PDF متطلبًا شائعًا للمطورين الذين يريدون التأكد من عرض ملف PDF بشكل صحيح على أجهزة مختلفة، بغض النظر عما إذا كانت الخطوط المطلوبة مثبتة على تلك الأجهزة أم لا.

## الخطوة 1: إنشاء تطبيق وحدة تحكم C# جديد
للبدء، قم بإنشاء تطبيق C# Console جديد في Visual Studio. يمكنك تسميتها ما تريد. بمجرد إنشاء المشروع، تحتاج إلى إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد مساحة الاسم Aspose.PDF
أضف السطر التالي من التعليمات البرمجية في أعلى ملف C# الخاص بك لاستيراد مساحة الاسم Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: تحميل ملف PDF موجود
لتضمين الخطوط في ملف PDF موجود، تحتاج إلى تحميل هذا الملف باستخدام فئة المستند. يوضح التعليمة البرمجية التالية كيفية تحميل ملف PDF موجود:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملف PDF موجود
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 4: التكرار عبر جميع الصفحات
بمجرد قيامك بتحميل ملف PDF، ستحتاج إلى التكرار خلال جميع الصفحات الموجودة في المستند. بالنسبة لكل صفحة، تحتاج إلى التحقق من استخدام أي خطوط، وإذا كان الأمر كذلك، فأنت بحاجة إلى تضمين تلك الخطوط. يوضح التعليمة البرمجية التالية كيفية التكرار عبر كافة الصفحات في ملف PDF وتضمين الخطوط:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // تحقق مما إذا كان الخط مضمنًا بالفعل
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // التحقق من وجود كائنات النموذج
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
بمجرد تضمين جميع الخطوط في ملف PDF، ستحتاج إلى حفظ المستند. الكود التالي يوضح كيفية حفظ ملف PDF:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// حفظ وثيقة PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لتضمين الخط باستخدام Aspose.PDF لـ .NET

إليك الكود المصدري الكامل لتضمين خط باستخدام Aspose.PDF لـ .NET.


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملفات PDF الموجودة
Document doc = new Document(dataDir + "input.pdf");

// التكرار من خلال جميع الصفحات
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// تحقق مما إذا كان الخط مضمنًا بالفعل
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// التحقق من وجود كائنات النموذج
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


## الاستنتاج تضمين الخط في ملف PDF
في هذه المقالة، ناقشنا كيفية تضمين الخطوط في ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF، بما في ذلك إضافة الخطوط وتضمينها. يعد تضمين الخطوط في ملف PDF خطوة مهمة لضمان عرض المستند بشكل صحيح على أجهزة مختلفة، بغض النظر عما إذا كانت الخطوط المطلوبة مثبتة على تلك الأجهزة أم لا

### الأسئلة الشائعة

#### س: ما أهمية تضمين الخطوط في ملف PDF؟

ج: يعد تضمين الخطوط في ملف PDF أمرًا ضروريًا لضمان ظهور المستند بشكل صحيح على الأجهزة والأنظمة المختلفة. عندما يتم تضمين الخطوط، فإنها تصبح جزءًا من ملف PDF، مما يلغي الاعتماد على الخطوط الخارجية المثبتة على جهاز العرض.

#### س: هل يمكنني تضمين جميع الخطوط المستخدمة في ملف PDF؟

ج: نعم، يمكنك تضمين جميع الخطوط المستخدمة في ملف PDF. يوفر Aspose.PDF for .NET أسلوبًا مباشرًا للتكرار عبر جميع الخطوط المستخدمة في ملف PDF وتضمينها لضمان العرض الدقيق على الأجهزة المختلفة.

#### س: هل يتوافق Aspose.PDF for .NET مع تنسيقات الخطوط المختلفة؟

ج: نعم، يدعم Aspose.PDF for .NET تنسيقات الخطوط المختلفة، بما في ذلك خطوط TrueType وOpenType وType 1 وCFF. يمكنه تضمين الخطوط في ملف PDF بغض النظر عن تنسيقها.

#### س: هل يؤدي تضمين الخطوط إلى زيادة حجم ملف مستند PDF؟

ج: نعم، يمكن أن يؤدي تضمين الخطوط في مستند PDF إلى زيادة حجم الملف، حيث يتم تضمين بيانات الخط داخل ملف PDF نفسه. ومع ذلك، يضمن ذلك بقاء مظهر المستند متسقًا، بغض النظر عن توفر الخط على جهاز العرض.

#### س: هل يمكنني تخصيص عملية تضمين الخط؟

ج: نعم، Aspose.PDF for .NET يسمح لك بتخصيص عملية تضمين الخط. يمكنك اختيار الخطوط المراد تضمينها، أو استبعاد خطوط معينة، أو تضمين مجموعات فرعية محددة فقط من الخط لتحسين حجم الملف.