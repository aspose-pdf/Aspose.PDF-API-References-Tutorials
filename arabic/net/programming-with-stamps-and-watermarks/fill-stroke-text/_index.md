---
title: تعبئة نص الشطب
linktitle: تعبئة نص الشطب
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية ملء النص وتحديد الخطوط العريضة بسهولة في مستندات PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة حول كيفية ملء النص وتحديده في مستند PDF باستخدام Aspose.PDF for .NET. سنوضح لك كيفية استخدام كود المصدر C # المتوفر لتطبيق ألوان التعبئة والمخطط التفصيلي على النص في مستند PDF.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة.
- تم تنزيل مكتبة Aspose.PDF لـ .NET والمشار إليها في مشروعك.

## الخطوة 2: إنشاء كائن حالة النص

الخطوة الأولى هي إنشاء كائن TextState لتمرير الخصائص المتقدمة. إليك الطريقة:

```csharp
// قم بإنشاء كائن TextState لنقل الخصائص المتقدمة
TextState ts = new TextState();

// تعيين لون المخطط التفصيلي
ts.StrokingColor = Color.Gray;

// تحديد وضع تجسيد النص
ts.RenderingMode = TextRenderingMode.StrokeText;
```

يقوم الكود أعلاه بإنشاء كائن TextState جديد ويضبط لون المخطط التفصيلي وكذلك كيفية عرض النص.

## الخطوة 3: تحميل مستند PDF

الآن بعد أن أصبح كائن TextState جاهزًا ، يمكننا تحميل مستند PDF حيث نريد تطبيق تعبئة النص والمخطط التفصيلي. إليك الطريقة:

```csharp
// قم بتحميل مستند PDF كمدخل
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

يقوم الكود أعلاه بتحميل مستند PDF الحالي باستخدام فئة PdfFileStamp من مكتبة Aspose.PDF.Facades.

## الخطوة 4: أضف Fill and Stroke إلى النص

الآن بعد أن تم تحميل مستند PDF ، يمكننا إضافة التعبئة والمخطط التفصيلي للنص. إليك الطريقة:

```csharp
// قم بإنشاء طابع (ختم) بالنص المحدد والخصائص
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// ربط كائن حالة النص
stamp.BindTextState(ts);

// تعيين الأصل X ، Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// أضف الختم إلى المستند
fileStamp.AddStamp(stamp);
```

يُنشئ الكود أعلاه طابعًا بالنص المحدد وخصائص التعبئة والحد المحددة.

## الخطوة 5: احفظ المستند الناتج

بمجرد إضافة ختم النص ، يمكننا حفظ مستند PDF المعدل. إليك الطريقة:

```csharp
// احفظ المستند المعدل
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

يحفظ الكود أعلاه مستند PDF المحرر في الدليل المحدد.

### عينة من التعليمات البرمجية المصدر لتعبئة النص باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بإنشاء كائن TextState لنقل الخصائص المتقدمة
TextState ts = new TextState();

// اضبط لون السكتة الدماغية
ts.StrokingColor = Color.Gray;

// تعيين وضع عرض النص
ts.RenderingMode = TextRenderingMode.StrokeText;

//قم بتحميل مستند إدخال PDF
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// ربط TextState
stamp.BindTextState(ts);

// تعيين أصل X ، Y.
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// أضف طابع
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## خاتمة

تهنئة ! لقد تعلمت كيفية تعبئة النص وتحديد الخطوط العريضة له في مستند PDF باستخدام Aspose.PDF for .NET. يمكنك الآن تطبيق هذه المعرفة لتخصيص ألوان التعبئة والمخطط التفصيلي في مستندات PDF الخاصة بك.
