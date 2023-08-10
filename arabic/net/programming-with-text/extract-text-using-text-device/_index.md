---
title: استخراج النص باستخدام جهاز النص
linktitle: استخراج النص باستخدام جهاز النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج نص من مستند PDF باستخدام Text Device في Aspose.PDF for .NET.
type: docs
weight: 210
url: /ar/net/programming-with-text/extract-text-using-text-device/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من مستند PDF باستخدام جهاز النص في Aspose.PDF for .NET. يوضح كود المصدر C # المقدم الخطوات الضرورية.

## متطلبات
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C # آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: قم بإعداد المشروع
1. قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية حيث تريد استخراج النص ، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود ، حدد موقع السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجود باستخدام امتداد`Document` المُنشئ وتمرير المسار إلى ملف PDF المُدخل.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## الخطوة 5: استخراج النص باستخدام جهاز النص
 إنشاء`StringBuilder` كائن لعقد النص المستخرج. كرر خلال كل صفحة من المستند واستخدم ملف`TextDevice` لاستخراج النص من كل صفحة.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## الخطوة 6: احفظ النص المستخرج
 حدد مسار ملف الإخراج واحفظ النص المستخرج في ملف نصي باستخدام الامتداد`File.WriteAllText` طريقة.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### نموذج التعليمات البرمجية المصدر لاستخراج النص باستخدام جهاز النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
// سلسلة لعقد النص المستخرج
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// إنشاء جهاز نصي
		TextDevice textDevice = new TextDevice();
		//تعيين خيارات استخراج النص - تعيين وضع استخراج النص (Raw أو Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// تحويل صفحة معينة وحفظ النص في الدفق
		textDevice.Process(pdfPage, textStream);
		// تحويل صفحة معينة وحفظ النص في الدفق
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// إغلاق دفق الذاكرة
		textStream.Close();
		// احصل على نص من دفق الذاكرة
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// احفظ النص المستخرج في ملف نصي
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في استخراج نص من مستند PDF باستخدام Text Device في Aspose.PDF for .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.