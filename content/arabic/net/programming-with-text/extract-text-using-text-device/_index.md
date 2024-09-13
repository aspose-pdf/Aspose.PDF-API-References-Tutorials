---
title: استخراج النص باستخدام أداة النص
linktitle: استخراج النص باستخدام أداة النص
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخراج النص من مستند PDF باستخدام جهاز النص في Aspose.PDF لـ .NET.
type: docs
weight: 210
url: /ar/net/programming-with-text/extract-text-using-text-device/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من مستند PDF باستخدام أداة Text Device في Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد استخراج النص منه، أضف ما يلي باستخدام التوجيهات في أعلى الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## الخطوة 3: تعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجودًا باستخدام`Document`المنشئ وتمرير المسار إلى ملف PDF المدخل.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## الخطوة 5: استخراج النص باستخدام Text Device
 إنشاء`StringBuilder` الكائن الذي يحمل النص المستخرج. قم بالتكرار عبر كل صفحة من المستند واستخدم`TextDevice` لاستخراج النص من كل صفحة.

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
 حدد مسار ملف الإخراج واحفظ النص المستخرج في ملف نصي باستخدام`File.WriteAllText` طريقة.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### عينة من كود المصدر لاستخراج النص باستخدام جهاز النص باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//سلسلة لحفظ النص المستخرج
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// إنشاء جهاز نصي
		TextDevice textDevice = new TextDevice();
		// تعيين خيارات استخراج النص - تعيين وضع استخراج النص (خام أو نقي)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// تحويل صفحة معينة وحفظ النص في الدفق
		textDevice.Process(pdfPage, textStream);
		// تحويل صفحة معينة وحفظ النص في الدفق
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// إغلاق مجرى الذاكرة
		textStream.Close();
		// الحصول على نص من مجرى الذاكرة
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// حفظ النص المستخرج في ملف نصي
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في استخراج نص من مستند PDF باستخدام أداة Text Device في Aspose.PDF for .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يوفر هذا البرنامج التعليمي إرشادات حول استخراج النص من مستند PDF باستخدام ميزة Text Device في Aspose.PDF for .NET. يوضح كود المصدر C# المصاحب الخطوات اللازمة لتحقيق هذه المهمة.

#### س: ما هي المساحات الأسماء التي يجب أن أستوردها؟

أ: في ملف الكود الذي تخطط لاستخراج النص منه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### س: كيف أحدد دليل المستند؟

 أ: في الكود، ابحث عن السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 أ: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام`Document` المنشئ وتوفير المسار إلى ملف PDF المدخل.

#### س: كيف يمكنني استخراج النص باستخدام جهاز النص؟

 أ: تتضمن الخطوة 5 إنشاء`StringBuilder` الكائن الذي يحمل النص المستخرج. ثم ستنتقل عبر كل صفحة من المستند وتستخدم`TextDevice` جنبا إلى جنب مع`TextExtractionOptions` لاستخراج النص من كل صفحة.

#### س: كيف أحفظ النص المستخرج في ملف؟

 أ: في الخطوة 6، ستحدد مسار ملف الإخراج وتستخدم`File.WriteAllText`طريقة لحفظ النص المستخرج في ملف نصي.

#### س: ما هو أهم ما يمكن تعلمه من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، ستتعلم كيفية الاستفادة من ميزة Text Device في Aspose.PDF for .NET لاستخراج نص من مستند PDF. يتم حفظ النص المستخرج في ملف إخراج محدد، مما يتيح لك معالجة المحتوى المستخرج والاستفادة منه حسب الحاجة.