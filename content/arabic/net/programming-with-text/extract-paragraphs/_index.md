---
title: استخراج الفقرات من ملف PDF
linktitle: استخراج الفقرات من ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخراج الفقرات في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 160
url: /ar/net/programming-with-text/extract-paragraphs/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج الفقرات في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد استخراج الفقرات منه، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجودًا باستخدام`Document` المنشئ وتمرير المسار إلى ملف PDF المدخل.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 5: استخراج الفقرات
 إنشاء مثيل`ParagraphAbsorber` الصف واستخدامه`Visit` طريقة استخراج الفقرات من الوثيقة.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## الخطوة 6: التكرار خلال الفقرات
قم بالتنقل عبر الفقرات المستخرجة للوصول إلى محتويات النص. استخدم الحلقات المتداخلة للتنقل عبر الأقسام والأسطر داخل كل فقرة.

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

### عينة من كود المصدر لاستخراج الفقرات باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح ملف PDF موجود
Document doc = new Document(dataDir + "input.pdf");
// إنشاء ParagraphAbsorber
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
لقد نجحت في استخراج فقرات من مستند PDF باستخدام Aspose.PDF for .NET. وقد تم عرض الفقرات المستخرجة في نافذة وحدة التحكم.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية استخراج الفقرات من ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر كود المصدر C# المصاحب خطوات عملية لتحقيق هذه المهمة.

#### س: ما هي المساحات الأسماء التي يجب أن أستوردها؟

أ: في ملف الكود الذي تنوي استخراج الفقرات منه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### س: كيف أحدد دليل المستند؟

 أ: حدد موقع الخط`string dataDir = "YOUR DOCUMENT DIRECTORY";` في الكود واستبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 أ: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام`Document` المنشئ وتوفير المسار إلى ملف PDF المدخل.

#### س: كيف يمكنني استخراج الفقرات من المستند؟

 أ: تتضمن الخطوة 5 إنشاء مثيل لـ`ParagraphAbsorber` الصف واستخدامه`Visit` طريقة استخراج الفقرات من مستند PDF.

#### س: كيف يمكنني تكرار الفقرات المستخرجة؟

أ: ترشدك الخطوة 6 خلال التنقل عبر الفقرات المستخرجة. تُستخدم الحلقات المتداخلة لتجاوز الأقسام والأسطر داخل كل فقرة، وفي النهاية الوصول إلى محتويات النص وعرضها.

#### س: ما هو أهم ما يمكن تعلمه من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم كيفية استخراج فقرات من مستند PDF باستخدام Aspose.PDF لـ .NET. يتم عرض الفقرات المستخرجة في نافذة وحدة التحكم، مما يوفر لك نظرة ثاقبة قيمة حول بنية محتوى المستند.