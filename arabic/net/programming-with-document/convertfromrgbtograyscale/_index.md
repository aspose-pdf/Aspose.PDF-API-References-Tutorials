---
title: تحويل من RGB إلى تدرج الرمادي
linktitle: تحويل من RGB إلى تدرج الرمادي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحويل ملفات PDF من RGB إلى تدرج الرمادي باستخدام Aspose.PDF لـ .NET. تحسين جودة الطباعة وتقليل حجم الملف.
type: docs
weight: 60
url: /ar/net/programming-with-document/convertfromrgbtograyscale/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تحويل مستند PDF من مساحة ألوان RGB إلى تدرج الرمادي باستخدام Aspose.PDF لـ .NET. يمكن أن يكون هذا التحويل مفيدًا لأغراض مختلفة ، مثل تقليل حجم الملف أو إعداد المستندات للطباعة. اتبع الدليل المفصل أدناه:

## الخطوة 1: قم بتحميل ملف PDF المصدر

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document document = new Document(dataDir + "input.pdf"))
{
    // الكود الخاص بك هنا ...
}
```

## الخطوة 2: حدد استراتيجية التحويل

```csharp
Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();
```

## الخطوة 3: تحويل كل صفحة إلى تدرج الرمادي

```csharp
for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
{
    Page page = document.Pages[idxPage];
    strategy.Convert(page);
}
```

## الخطوة 4: احفظ الملف الناتج

```csharp
document.Save(dataDir + "Test-gray_out.pdf");
```

تهانينا! لقد نجحت في تحويل مستند PDF من RGB إلى تدرج الرمادي باستخدام Aspose.PDF لـ .NET.

### مثال على كود مصدر للتحويل من RGB إلى تدرج الرمادي باستخدام Aspose.PDF for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل ملف PDF المصدر
using (Document document = new Document(dataDir + "input.pdf"))
{
    Aspose.Pdf.RgbToDeviceGrayConversionStrategy strategy = new Aspose.Pdf.RgbToDeviceGrayConversionStrategy();

    for (int idxPage = 1; idxPage <= document.Pages.Count; idxPage++)
    {
        Page page = document.Pages[idxPage];
        strategy.Convert(page);
    }

    document.Save(dataDir + "Test-gray_out.pdf");
}
```

الآن يمكنك بسهولة تحويل مستندات PDF الخاصة بك من RGB إلى تدرج الرمادي باستخدام Aspose.PDF لـ .NET.

