---
title: إزالة الارتباطات التشعبية بعد التحويل من HTML
linktitle: إزالة الارتباطات التشعبية بعد التحويل من HTML
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإزالة الارتباطات التشعبية بعد تحويل HTML إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 250
url: /ar/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
في هذا البرنامج التعليمي، سنرشدك خلال عملية إزالة الارتباطات التشعبية من ملف PDF تم إنشاؤه من ملف HTML باستخدام Aspose.PDF لـ .NET. الارتباطات التشعبية هي روابط قابلة للنقر عليها والتي قد تعيد التوجيه إلى صفحات أو مواقع ويب أخرى. باتباع الخطوات أدناه، ستتمكن من إزالة الارتباطات التشعبية من ملف PDF الناتج.

## المتطلبات الأساسية
قبل البدء، تأكد من استيفاء المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- مكتبة Aspose.PDF لـ .NET مثبتة على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: تحميل ملف HTML وإزالة الارتباطات التشعبية
في هذه الخطوة، سنقوم بتحميل ملف HTML وإزالة الارتباطات التشعبية من مستند PDF الناتج. استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل ملف HTML باستخدام خيارات تحميل HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// تصفح التعليقات التوضيحية للصفحة الأولى من المستند
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // تحقق مما إذا كان التعليق التوضيحي عبارة عن رابط
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // تحقق مما إذا كان الإجراء من النوع GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // استخدم أداة امتصاص أجزاء النص للعثور على أجزاء النص المطابقة
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // قم بالمراجعة عبر أجزاء النص المطابقة وقم بإزالة السمات من الارتباطات التشعبية
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // قم بإزالة التعليق التوضيحي من الصفحة
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي الذي يوجد به ملف HTML الخاص بك.

## الخطوة 2: حفظ ملف PDF الناتج
وأخيرًا، سنقوم بحفظ ملف PDF الناتج بدون الارتباطات التشعبية. استخدم الكود التالي:

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
في هذا البرنامج التعليمي، قمنا بتغطية العملية خطوة بخطوة لإزالة الارتباطات التشعبية من ملف PDF تم إنشاؤه من ملف HTML باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه، ستتمكن من إزالة الارتباطات التشعبية بنجاح من ملف PDF الناتج.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من العمل مع مستندات PDF في تطبيقات C#. وهو يقدم مجموعة واسعة من الوظائف، بما في ذلك القدرة على تحويل ملفات HTML إلى PDF ومعالجة محتوى PDF.

#### س: لماذا أرغب في إزالة الارتباطات التشعبية من ملف PDF؟

ج: هناك أسباب مختلفة لإزالة الارتباطات التشعبية من ملف PDF. على سبيل المثال، قد ترغب في إزالة الروابط الخارجية لأغراض الطباعة أو الأرشفة أو التأكد من أن محتوى PDF غير قابل للتنقل عبر الارتباطات التشعبية.

#### س: كيف يمكنني تحميل ملف HTML وإزالة الارتباطات التشعبية باستخدام Aspose.PDF لـ .NET؟

 ج: لتحميل ملف HTML وإزالة الارتباطات التشعبية، يمكنك استخدام Aspose.PDF لملفات .NET`HtmlLoadOptions` فصل. قم بالتكرار من خلال التعليقات التوضيحية لصفحات PDF للعثور على التعليقات التوضيحية للارتباط وتعديل سماتها.

#### س: هل يمكنني تخصيص اسم ملف الإخراج لملف PDF الناتج؟

ج: نعم، يمكنك تخصيص اسم الملف الناتج لملف PDF الناتج عن طريق تعديل الكود الذي يحفظ مستند PDF. ما عليك سوى تغيير اسم الملف المطلوب في ملف`doc.Save()` طريقة.

#### س: هل من الممكن إزالة الارتباطات التشعبية بشكل انتقائي بناءً على معايير معينة؟

ج: نعم، يمكنك إزالة الارتباطات التشعبية بشكل انتقائي بناءً على معايير محددة. على سبيل المثال، يمكنك اختيار إزالة الروابط الخارجية فقط أو الروابط التي تشير إلى عناوين URL محددة.