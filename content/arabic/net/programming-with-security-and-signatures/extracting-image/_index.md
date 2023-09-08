---
title: استخراج الصورة
linktitle: استخراج الصورة
second_title: Aspose.PDF لمرجع .NET API
description: يمكنك استخراج الصور بسهولة من مستندات PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-security-and-signatures/extracting-image/
---
يمكن أن يكون استخراج الصور من مستند PDF مفيدًا في كثير من الحالات. باستخدام Aspose.PDF for .NET، يمكنك استخراج الصور بسهولة باستخدام كود المصدر التالي:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج الصورة منه. يستبدل`"YOUR DOCUMENTS DIRECTORY"`في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## الخطوة 3: استخراج الصورة من وثيقة PDF

الآن سنقوم باستخراج الصورة من مستند PDF باستخدام الكود التالي:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

في هذا المثال، نقوم بالتكرار خلال كل حقل من حقول النموذج في مستند PDF. إذا تم العثور على حقل توقيع، فإننا نستخرج الصورة المرتبطة ونحفظها في ملف JPEG.

### نموذج التعليمات البرمجية المصدر لاستخراج الصور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## خاتمة

تهنئة ! الآن لديك دليل خطوة بخطوة لاستخراج الصور من مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك دمج هذا الكود في مشاريعك الخاصة لاستخراج الصور واستخدامها حسب الحاجة.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات استخراج الصور المتقدمة ومعالجة مستندات PDF.


### الأسئلة الشائعة

#### س: هل Aspose.PDF for .NET مناسب للمبتدئين؟

ج: على الرغم من أن بعض الإلمام ببرمجة C# مفيد، إلا أن برنامجنا التعليمي مصمم ليكون مناسبًا للمبتدئين، ويرشدك خلال كل خطوة.

#### س: هل يمكنني استخراج صور متعددة في وقت واحد؟

ج: بالتأكيد! ومن خلال تنفيذ الحلقات وتكييف الكود المقدم، يمكنك استخراج صور متعددة من مستند PDF واحد.

#### س: هل Aspose.PDF for .NET هو الحل الوحيد لاستخراج الصور؟

ج: على الرغم من توفر أدوات أخرى، فإن Aspose.PDF for .NET مشهور بكفاءته وميزاته الشاملة.

#### س: هل يمكنني استخدام الصور المستخرجة لأغراض تجارية؟

ج: نعم، بمجرد استخراجها، تصبح الصور ملكك لاستخدامها حسب الحاجة، بما في ذلك المشاريع التجارية.

#### س: أين يمكنني العثور على المزيد من الموارد حول معالجة ملفات PDF باستخدام Aspose.PDF؟

ج: قم بزيارة وثائقنا الرسمية للحصول على مجموعة كبيرة من الموارد والرؤى حول معالجة ملفات PDF المتقدمة باستخدام Aspose.PDF لـ .NET.