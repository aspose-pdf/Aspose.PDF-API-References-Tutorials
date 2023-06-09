---
title: تحديث لون نص الارتباط
linktitle: تحديث لون نص الارتباط
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديث لون نص الروابط في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 130
url: /ar/net/programming-with-links-and-actions/update-link-text-color/
---

تعرف على كيفية تحديث لون نص الروابط في ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.

## الخطوة الأولى: تهيئة البيئة

تأكد من قيامك بإعداد بيئة التطوير الخاصة بك باستخدام مشروع C # ومراجع Aspose.PDF المناسبة.

## الخطوة الثانية: تحميل ملف PDF

قم بتعيين مسار الدليل للمستندات الخاصة بك وقم بتحميل ملف PDF باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل ملف PDF
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## الخطوة 3: تصفح التعليقات التوضيحية للارتباط

قم بالتكرار خلال جميع التعليقات التوضيحية للارتباط في الصفحة الثانية من المستند باستخدام الكود التالي:

```csharp
foreach(Annotation annotation in doc.Pages[1].Annotations)
{
     if (annotation is LinkAnnotation)
     {
         // ابحث عن النص تحت التعليق التوضيحي
         TextFragmentAbsorber ta = new TextFragmentAbsorber();
         Rectangle rect = annotation.Rect;
         rect.LLX -= 10;
         rect.LLY -= 10;
         rect.URX += 10;
         rect.URY += 10;
         ta.TextSearchOptions = new TextSearchOptions(rect);
         your.Visit(doc.Pages[1]);
         // تغيير لون النص.
         foreach(TextFragment tf in ta.TextFragments)
         {
             tf.TextState.ForegroundColor = Color.Red;
         }
     }
}
```

## الخطوة 4: احفظ المستند بنص الارتباط المحدث

 احفظ المستند بنص الارتباط المحدث باستخدام امتداد`Save` طريقة:

```csharp
dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
doc.Save(dataDir);
```

## الخطوة 5: عرض النتيجة

اعرض رسالة تفيد بأنه تم تحديث لون نص التعليق التوضيحي للرابط بنجاح وحدد موقع الملف المحفوظ:

```csharp
Console.WriteLine("\nText color of link annotations updated successfully.\nFile saved to location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Update Link Text Color باستخدام Aspose.PDF for .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل ملف PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is LinkAnnotation)
		{
			// ابحث في النص تحت التعليق التوضيحي
			TextFragmentAbsorber ta = new TextFragmentAbsorber();
			Rectangle rect = annotation.Rect;
			rect.LLX -= 10;
			rect.LLY -= 10;
			rect.URX += 10;
			rect.URY += 10;
			ta.TextSearchOptions = new TextSearchOptions(rect);
			ta.Visit(doc.Pages[1]);
			// تغيير لون النص.
			foreach (TextFragment tf in ta.TextFragments)
			{
				tf.TextState.ForegroundColor = Color.Red;
			}
		}
	}
	dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
	// احفظ المستند مع الارتباط المحدث
	doc.Save(dataDir);
	Console.WriteLine("\nLinkAnnotation text color updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية تحديث لون نص الروابط في ملف PDF باستخدام Aspose.PDF لـ .NET. استخدم هذه المعرفة لتخصيص مظهر الروابط الخاصة بك في مستندات PDF.

الآن بعد أن أكملت هذا الدليل ، يمكنك تطبيق هذه المفاهيم على مشاريعك الخاصة واستكشاف المزيد من الميزات التي يوفرها Aspose.PDF لـ .NET.