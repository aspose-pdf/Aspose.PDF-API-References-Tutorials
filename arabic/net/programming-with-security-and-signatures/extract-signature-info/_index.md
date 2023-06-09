---
title: استخراج معلومات التوقيع
linktitle: استخراج معلومات التوقيع
second_title: Aspose.PDF لمرجع .NET API
description: استخراج معلومات التوقيع باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 80
url: /ar/net/programming-with-security-and-signatures/extract-signature-info/
---

يمكن أن تكون عملية استخراج معلومات التوقيع من مستند PDF مفيدة جدًا في سيناريوهات مختلفة. سواء أكنت بحاجة إلى التحقق من صحة وثيقة موقعة أو تحليل الشهادة المستخدمة للتوقيع ، توفر مكتبة Aspose.PDF for .NET حلاً مناسبًا. في هذا البرنامج التعليمي ، سنوجهك خلال العملية خطوة بخطوة لاستخراج معلومات التوقيع باستخدام كود المصدر C # المقدم.

## متطلبات

قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية:

1. المعرفة الأساسية بلغة البرمجة C #.
2. Aspose.PDF لمكتبة .NET مثبتة على نظامك.
3. وثيقة PDF صالحة مع واحد أو أكثر من حقول التوقيع.

الآن ، دعنا نتعمق في تفاصيل التنفيذ.

## الخطوة 1: استيراد المكتبات المطلوبة

 للبدء ، تحتاج إلى استيراد المكتبات الضرورية إلى مشروع C # الخاص بك. في هذه الحالة ، نحتاج إلى استيراد ملف`Aspose.Pdf` و`System.IO` مساحات الأسماء. يمكن القيام بذلك عن طريق إضافة الكود التالي في بداية ملف C # الخاص بك:

```csharp
using Aspose.Pdf;
using System.IO;
```

## الخطوة 2: ضبط مسار المستند

 بعد ذلك ، تحتاج إلى تعيين المسار إلى مستند PDF الذي تريد استخراج معلومات التوقيع منه. يستبدل`"YOUR DOCUMENTS DIRECTORY"` في مقتطف الشفرة التالي بالمسار الفعلي للمستند:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## الخطوة 3: استخراج معلومات التوقيع

الآن ، دعنا ننتقل إلى الجزء الرئيسي من الكود حيث نقوم باستخراج معلومات التوقيع من مستند PDF. نحن نكرر كل حقل في نموذج المستند ونتحقق مما إذا كان حقل توقيع. إذا تم العثور على حقل توقيع ، فإننا نواصل استخراج الشهادة. أضف مقتطف الشفرة التالي:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // استخراج الشهادة
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## الخطوة 4: استخراج الشهادة

في هذه الخطوة ، نقوم باستخراج الشهادة من حقل التوقيع وحفظها كملف. يمكن تحليل الشهادة المستخرجة أو استخدامها لأغراض التحقق من الصحة. يوضح مقتطف الشفرة أدناه عملية الاستخراج والحفظ:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## الخطوة الخامسة

: حفظ الشهادة

أخيرًا ، نحفظ الشهادة المستخرجة كملف. في هذا المثال ، يتم حفظ الشهادة باسم "input.cer" في الدليل المحدد. يمكنك تعديل الكود ليناسب متطلباتك. إليك مقتطف الشفرة لحفظ الشهادة:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

هذا كل شيء! لقد نجحت في استخراج معلومات التوقيع باستخدام Aspose.PDF for .NET. لا تتردد في دمج هذا الرمز في تطبيقاتك الخاصة أو تعديله وفقًا لاحتياجاتك.

### نموذج التعليمات البرمجية المصدر لـ Extract Signature Info باستخدام Aspose.PDF for .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، استعرضنا دليلًا تفصيليًا حول كيفية استخراج معلومات التوقيع من مستند PDF باستخدام Aspose.PDF لمكتبة .NET. قمنا بتغطية عملية استيراد المكتبات المطلوبة ، وتحديد مسار المستند ، واستخراج معلومات التوقيع ، واستخراج الشهادة ، وحفظها في ملف. باتباع هذه الخطوات ، يمكنك بسهولة استرداد تفاصيل التوقيع والعمل معها حسب الحاجة.