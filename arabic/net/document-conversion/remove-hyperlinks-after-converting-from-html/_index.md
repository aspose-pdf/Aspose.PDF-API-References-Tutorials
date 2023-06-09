---
title: قم بإزالة الارتباطات التشعبية بعد التحويل من Html
linktitle: قم بإزالة الارتباطات التشعبية بعد التحويل من Html
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإزالة الارتباطات التشعبية بعد تحويل HTML إلى PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 250
url: /ar/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية إزالة الارتباطات التشعبية من ملف PDF تم إنشاؤه من ملف HTML باستخدام Aspose.PDF لـ .NET. الارتباطات التشعبية هي روابط قابلة للنقر قد تعيد التوجيه إلى صفحات أو مواقع ويب أخرى. باتباع الخطوات أدناه ، ستتمكن من إزالة الارتباطات التشعبية من ملف PDF الناتج.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل ملف HTML وإزالة الارتباطات التشعبية
في هذه الخطوة ، سنقوم بتحميل ملف HTML ونزيل الارتباطات التشعبية من مستند PDF الناتج. استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل ملف HTML باستخدام خيارات تحميل HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// تصفح التعليقات التوضيحية للصفحة الأولى من المستند
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // تحقق مما إذا كان التعليق التوضيحي رابطًا
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // تحقق مما إذا كان الإجراء من نوع GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // استخدم أداة امتصاص أجزاء النص للعثور على أجزاء نص مطابقة
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // تكرار أجزاء النص المطابقة وإزالة السمات من الارتباطات التشعبية
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // أزل التعليق التوضيحي من الصفحة
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملف HTML الخاص بك.

## الخطوة 2: حفظ ملف PDF الناتج
أخيرًا ، سنقوم بحفظ ملف PDF الناتج بدون الارتباطات التشعبية. استخدم الكود التالي:

```csharp
// احفظ ملف PDF الناتج
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 يحفظ الكود أعلاه ملف PDF الناتج باسم الملف`"RemoveHyperlinksFromText_out.pdf"`.

### مثال على التعليمات البرمجية المصدر لإزالة الارتباطات التشعبية بعد التحويل من Html باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لإزالة الارتباطات التشعبية من ملف PDF تم إنشاؤه من ملف HTML باستخدام Aspose.PDF for .NET. باتباع الإرشادات الموضحة أعلاه ، ستتمكن من إزالة الارتباطات التشعبية بنجاح من ملف PDF الناتج.