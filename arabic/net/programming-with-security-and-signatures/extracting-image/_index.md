---
title: استخراج الصورة
linktitle: استخراج الصورة
second_title: Aspose.PDF لمرجع .NET API
description: استخرج الصور بسهولة من مستندات PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 70
url: /ar/net/programming-with-security-and-signatures/extracting-image/
---

يمكن أن يكون استخراج الصور من مستند PDF مفيدًا في كثير من الحالات. باستخدام Aspose.PDF for .NET ، يمكنك استخراج الصور بسهولة باستخدام الكود المصدري التالي:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد استخراج الصورة منه. يستبدل`"YOUR DOCUMENTS DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## الخطوة 3: استخرج الصورة من مستند PDF

سنقوم الآن باستخراج الصورة من مستند PDF باستخدام الكود التالي:

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

في هذا المثال ، نقوم بإجراء حلقة عبر كل حقل من حقول النموذج في مستند PDF. إذا تم العثور على حقل توقيع ، فإننا نستخرج الصورة المرتبطة ونحفظها في ملف JPEG.

### عينة من التعليمات البرمجية المصدر لاستخراج الصورة باستخدام Aspose.PDF لـ .NET 
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

تهنئة ! لديك الآن دليل خطوة بخطوة لاستخراج الصور من مستند PDF باستخدام Aspose.PDF for .NET. يمكنك دمج هذا الرمز في مشاريعك الخاصة لاستخراج الصور واستخدامها حسب الحاجة.

تأكد من مراجعة وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول ميزات استخراج الصور المتقدمة ومعالجة مستندات PDF.