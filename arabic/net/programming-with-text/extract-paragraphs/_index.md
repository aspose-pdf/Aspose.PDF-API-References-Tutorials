---
title: استخراج الفقرات
linktitle: استخراج الفقرات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج فقرات من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 160
url: /ar/net/programming-with-text/extract-paragraphs/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخراج الفقرات من مستند PDF باستخدام Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد استخراج الفقرات ، أضف التعليمات التالية باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجود باستخدام امتداد`Document` المُنشئ وتمرير المسار إلى ملف PDF المُدخل.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## الخطوة 5: استخرج الفقرات
 تجسيد`ParagraphAbsorber` الطبقة واستخدامه`Visit` طريقة لاستخراج الفقرات من المستند.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## الخطوة 6: كرر من خلال الفقرات
قم بالتكرار خلال الفقرات المستخرجة للوصول إلى محتويات النص. استخدم الحلقات المتداخلة للتنقل عبر الأقسام والأسطر داخل كل فقرة.

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
// افتح ملف PDF موجود
Document doc = new Document(dataDir + "input.pdf");
// إنشاء فقرة ممتص
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
لقد نجحت في استخراج فقرات من مستند PDF باستخدام Aspose.PDF for .NET. تم عرض الفقرات المستخرجة في نافذة وحدة التحكم.