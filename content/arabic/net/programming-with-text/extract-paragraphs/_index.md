---
title: استخراج الفقرات في ملف PDF
linktitle: استخراج الفقرات في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج الفقرات من ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 160
url: /ar/net/programming-with-text/extract-paragraphs/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج الفقرات في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد استخراج الفقرات منه، أضف ما يلي باستخدام التوجيهات الموجودة في أعلى الملف:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجود باستخدام الملف`Document`منشئ وتمرير المسار إلى ملف PDF الإدخال.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 5: استخراج الفقرات
 إنشاء مثيل`ParagraphAbsorber` الصف واستخدامه`Visit` طريقة استخراج الفقرات من الوثيقة.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## الخطوة 6: التكرار من خلال الفقرات
قم بالمرور عبر الفقرات المستخرجة للوصول إلى محتويات النص. استخدم حلقات متداخلة للتنقل عبر الأقسام والأسطر داخل كل فقرة.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### نموذج التعليمات البرمجية المصدر لاستخراج الفقرات باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//افتح ملف PDF موجود
Document doc = new Document(dataDir + "input.pdf");
// إنشاء مثيل لامتصاص الفقرة
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## خاتمة
لقد نجحت في استخراج الفقرات من مستند PDF باستخدام Aspose.PDF لـ .NET. تم عرض الفقرات المستخرجة في نافذة وحدة التحكم.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية استخراج الفقرات من ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر كود مصدر C# المصاحب خطوات عملية لتحقيق هذه المهمة.

#### س: ما هي مساحات الأسماء التي يجب علي استيرادها؟

ج: في ملف التعليمات البرمجية الذي تنوي استخراج الفقرات منه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### س: كيف أحدد دليل المستندات؟

 ج: تحديد موقع الخط`string dataDir = "YOUR DOCUMENT DIRECTORY";` في التعليمات البرمجية واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 ج: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام الملف`Document` منشئ وتوفير المسار إلى ملف PDF الإدخال.

#### س: كيف يمكنني استخراج فقرات من الوثيقة؟

 ج: تتضمن الخطوة 5 إنشاء مثيل لـ`ParagraphAbsorber` الصف واستخدامه`Visit` طريقة استخراج الفقرات من وثيقة PDF.

#### س: كيف يمكنني التكرار خلال الفقرات المستخرجة؟

ج: ترشدك الخطوة 6 خلال التكرار عبر الفقرات المستخرجة. تُستخدم الحلقات المتداخلة لاجتياز الأقسام والأسطر داخل كل فقرة، للوصول في النهاية إلى محتويات النص وعرضها.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية استخراج الفقرات من مستند PDF باستخدام Aspose.PDF لـ .NET. تم عرض الفقرات المستخرجة في نافذة وحدة التحكم، مما يوفر لك رؤية قيمة حول بنية محتوى المستند.