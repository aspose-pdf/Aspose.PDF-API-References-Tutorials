---
title: احصل على نص الارتباط التشعبي
linktitle: احصل على نص الارتباط التشعبي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج نص الارتباط التشعبي من ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 70
url: /ar/net/programming-with-links-and-actions/get-hyperlink-text/
---

تعرف على كيفية استخراج النص من الارتباطات التشعبية في ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.

## الخطوة الأولى: تهيئة البيئة

تأكد من قيامك بإعداد بيئة التطوير الخاصة بك باستخدام مشروع C # ومراجع Aspose.PDF المناسبة.

## الخطوة الثانية: تحميل ملف PDF

قم بتعيين مسار الدليل للمستندات الخاصة بك وقم بتحميل ملف PDF باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل ملف PDF
Document document = new Document(dataDir + "input.pdf");
```

## الخطوة 3: التنقل عبر صفحات المستند

 كرر كل صفحة من صفحات المستند باستخدام ملف`foreach` حلقة:

```csharp
foreach(Page page in document.Pages)
{
     // عرض التعليقات التوضيحية للارتباط
     ShowLinkAnnotations(page);
}
```

## الخطوة 4: معالجة الأخطاء

أضف معالجة الأخطاء للقبض على أي استثناء وعرض رسالة الخطأ المقابلة:

```csharp
catch (Exception ex)
{
     Console.WriteLine(ex.Message);
}
```

### نموذج التعليمات البرمجية المصدر للحصول على نص الارتباط التشعبي باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل ملف PDF
	Document document = new Document(dataDir + "input.pdf");
	// كرر خلال كل صفحة من صفحات PDF
	foreach (Page page in document.Pages)
	{
		// إظهار التعليق التوضيحي للارتباط
		ShowLinkAnnotations(page);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية استخراج نص الارتباط التشعبي من ملف PDF باستخدام Aspose.PDF for .NET. يمكنك استخدام هذه المعرفة للتعامل مع الارتباطات التشعبية في مشاريعك وأتمتة المهام المتعلقة بملفات PDF.

الآن بعد أن أكملت هذا الدليل ، يمكنك تطبيق هذه المفاهيم على مشاريعك الخاصة واستكشاف المزيد من الميزات التي يوفرها Aspose.PDF لـ .NET.