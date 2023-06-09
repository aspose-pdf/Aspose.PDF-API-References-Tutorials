---
title: نص إلى PDF
linktitle: نص إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: تحويل بسيط وفعال للملفات النصية إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 300
url: /ar/net/document-conversion/text-to-pdf/
---

سيرشدك هذا البرنامج التعليمي خلال خطوات تحويل ملف نصي إلى ملف PDF باستخدام Aspose.PDF for .NET. يقدم Aspose.PDF حلاً بسيطًا وفعالًا لتحويل النص العادي إلى PDF مع الحفاظ على تنسيق النص وعرضه. اتبع الخطوات أدناه لإجراء هذا التحويل.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من تلبية المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت مكتبة Aspose.PDF لـ .NET على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: قراءة الملف النصي
 الخطوة الأولى هي قراءة محتويات الملف النصي باستخدام امتداد`StreamReader` فصل. استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// اقرأ الملف النصي
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي حيث يوجد ملفك النصي.

## الخطوة الثانية: إنشاء وثيقة PDF
 الخطوة الثانية هي إنشاء ملف`Document` الذي سيمثل وثيقة PDF النهائية. استخدم الكود التالي:

```csharp
// قم بإنشاء كائن مستند
Document doc = new Document();
```

## الخطوة 3: إضافة نص إلى المستند
الخطوة الثالثة هي إضافة النص المقروء إلى صفحة وثيقة PDF. استخدم الكود التالي:

```csharp
// أضف صفحة جديدة إلى المستند
Page page = doc.Pages.Add();

//قم بإنشاء كائن TextFragment وقم بتمرير النص المقروء كوسيطة
TextFragment text = new TextFragment(tr.ReadToEnd());

// أضف فقرة النص إلى الصفحة
page.Paragraphs.Add(text);
```

## الخطوة 4: حفظ ملف PDF
أخيرًا ، احفظ ملف PDF الناتج عن طريق تحديد المسار المطلوب واسم الملف. استخدم الكود التالي:

```csharp
// احفظ ملف PDF الناتج
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

تأكد من تحديد المسار المطلوب واسم الملف لملف PDF الناتج.

### مثال على كود المصدر لـ Text to PDF باستخدام Aspose.PDF لـ .NET

```csharp
try
{
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// اقرأ الملف النصي المصدر
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// إنشاء كائن مستند عن طريق استدعاء المُنشئ الفارغ الخاص به
	Document doc = new Document();

	// أضف صفحة جديدة في مجموعة Pages من المستندات
	Page page = doc.Pages.Add();

	// قم بإنشاء مثيل لـ TextFragmet وقم بتمرير النص من كائن القارئ إلى مُنشئه كوسيطة
	TextFragment text = new TextFragment(tr.ReadToEnd());
	// Text.TextState.Font = FontRepository.FindFont ("Arial Unicode MS") ؛

	// أضف فقرة نصية جديدة في مجموعة الفقرات وقم بتمرير الكائن TextFragment
	page.Paragraphs.Add(text);

	// حفظ ملف PDF الناتج
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل ملف نصي إلى ملف PDF باستخدام Aspose.PDF for .NET. باتباع الخطوات المذكورة أعلاه ، يمكنك بسهولة إجراء هذا التحويل. استخدم هذه الطريقة لتحويل ملفاتك النصية إلى PDF واستمتع بمرونة وجودة Aspose.PDF.