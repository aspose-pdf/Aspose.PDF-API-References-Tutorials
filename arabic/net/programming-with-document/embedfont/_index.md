---
title: تضمين الخط في ملف PDF
linktitle: تضمين الخط في ملف PDF
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

// قم بتحميل ملفات PDF موجودة
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


## اختتام تضمين الخط في ملف PDF
في هذه المقالة ، ناقشنا كيفية تضمين الخطوط في ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF ، بما في ذلك إضافة الخطوط وتضمينها. يعد دمج الخطوط في ملف PDF خطوة مهمة لضمان عرض المستند بشكل صحيح على أجهزة مختلفة ، بغض النظر عما إذا كانت الخطوط المطلوبة مثبتة على تلك الأجهزة

### التعليمات

#### س: ما سبب أهمية تضمين الخطوط في ملف PDF؟

ج: يعد دمج الخطوط في ملف PDF أمرًا ضروريًا لضمان ظهور المستند بشكل صحيح على أجهزة وأنظمة مختلفة. عندما يتم تضمين الخطوط ، فإنها تصبح جزءًا من ملف PDF ، مما يلغي الاعتماد على الخطوط الخارجية المثبتة على جهاز العرض.

#### س: هل يمكنني تضمين كل الخطوط المستخدمة في ملف PDF؟

ج: نعم ، يمكنك تضمين كل الخطوط المستخدمة في ملف PDF. يوفر Aspose.PDF for .NET طريقة مباشرة للتكرار من خلال جميع الخطوط المستخدمة في ملف PDF وتضمينها لضمان التقديم الدقيق على الأجهزة المختلفة.

#### س: هل Aspose.PDF for .NET متوافق مع تنسيقات الخطوط المختلفة؟

ج: نعم ، يدعم Aspose.PDF for .NET تنسيقات خطوط متنوعة ، بما في ذلك خطوط TrueType و OpenType و Type 1 و CFF. يمكنه تضمين الخطوط في ملف PDF بغض النظر عن تنسيقها.

#### س: هل يؤدي تضمين الخطوط إلى زيادة حجم ملف مستند PDF؟

ج: نعم ، يمكن أن يؤدي تضمين الخطوط في مستند PDF إلى زيادة حجم الملف ، حيث يتم تضمين بيانات الخط في ملف PDF نفسه. ومع ذلك ، فإن هذا يضمن بقاء مظهر المستند متسقًا ، بغض النظر عن توفر الخط على جهاز العرض.

#### س: هل يمكنني تخصيص عملية تضمين الخط؟

ج: نعم ، يسمح لك Aspose.PDF for .NET بتخصيص عملية دمج الخط. يمكنك اختيار الخطوط المراد تضمينها ، أو استبعاد خطوط معينة ، أو دمج مجموعات فرعية محددة فقط من الخط لتحسين حجم الملف.