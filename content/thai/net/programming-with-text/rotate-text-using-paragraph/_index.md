---
title: หมุนข้อความโดยใช้ย่อหน้าในไฟล์ PDF
linktitle: หมุนข้อความโดยใช้ย่อหน้าในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีหมุนข้อความโดยใช้ย่อหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 380
url: /th/net/programming-with-text/rotate-text-using-paragraph/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ย่อหน้า ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการบทแนะนำต่อ โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Aspose.PDF สำหรับไลบรารี .NET แล้ว คุณสามารถรับได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อติดตั้งในโครงการของคุณ

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

เพิ่มคำสั่งต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณเพื่อนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## ขั้นตอนที่ 3: สร้างเอกสาร PDF

 เริ่มต้น`Document` วัตถุเพื่อสร้างเอกสาร PDF ใหม่:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: เพิ่มหน้า

 รับหน้าใดหน้าหนึ่งจากเอกสารโดยใช้`Pages.Add()` วิธี:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 5: สร้างย่อหน้าข้อความ

 สร้างก`TextParagraph` วัตถุและกำหนดตำแหน่งบนหน้า:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

ปรับค่าตำแหน่งตามความต้องการของคุณ

## ขั้นตอนที่ 6: สร้างและกำหนดค่าส่วนของข้อความ

 สร้างหลายรายการ`TextFragment` วัตถุและตั้งค่าข้อความและคุณสมบัติ:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

ปรับข้อความและคุณสมบัติอื่นๆ ตามต้องการ

## ขั้นตอนที่ 7: เพิ่มส่วนข้อความต่อท้ายย่อหน้า

 เพิ่มส่วนข้อความที่สร้างขึ้นต่อท้ายย่อหน้าโดยใช้`AppendLine` วิธี:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## ขั้นตอนที่ 8: สร้าง TextBuilder และต่อท้ายย่อหน้า

 สร้างก`TextBuilder` วัตถุโดยใช้`pdfPage` และต่อท้ายย่อหน้าข้อความในหน้า PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## ขั้นตอนที่ 9: บันทึกเอกสาร PDF

 บันทึกเอกสาร PDF ที่แก้ไขแล้วลงในไฟล์โดยใช้นามสกุล`Save` วิธี:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"TextFragmentTests_Rotated2_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

### ตัวอย่างซอร์สโค้ดสำหรับการหมุนข้อความโดยใช้ย่อหน้าโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เริ่มต้นวัตถุเอกสาร
Document pdfDocument = new Document();
// รับเฉพาะหน้า
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// สร้างส่วนของข้อความ
TextFragment textFragment1 = new TextFragment("rotated text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ตั้งค่าการหมุน
textFragment1.TextState.Rotation = 45;
// สร้างส่วนของข้อความ
TextFragment textFragment2 = new TextFragment("main text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// สร้างส่วนของข้อความ
TextFragment textFragment3 = new TextFragment("another rotated text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ตั้งค่าการหมุน
textFragment3.TextState.Rotation = -45;
// เพิ่มส่วนข้อความต่อท้ายย่อหน้า
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// สร้างวัตถุ TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// เพิ่มย่อหน้าข้อความต่อท้ายหน้า PDF
textBuilder.AppendParagraph(paragraph);
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีการหมุนข้อความโดยใช้ย่อหน้าในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การสร้างเอกสารไปจนถึงการบันทึกเวอร์ชันที่แก้ไข ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อจัดการการหมุนข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "หมุนข้อความโดยใช้ย่อหน้า" คืออะไร

ตอบ: บทช่วยสอน "หมุนข้อความโดยใช้ย่อหน้า" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ย่อหน้าข้อความในเอกสาร PDF บทช่วยสอนให้คำแนะนำทีละขั้นตอนและโค้ดตัวอย่างเพื่อให้บรรลุฟังก์ชันนี้

#### ถาม: "การหมุนข้อความโดยใช้ย่อหน้า" หมายความว่าอย่างไร

ตอบ: การหมุนข้อความโดยใช้ย่อหน้าหมายถึงความสามารถในการใช้การหมุนกับข้อความภายในเอกสาร PDF โดยใช้ย่อหน้าข้อความ เทคนิคนี้ช่วยให้คุณสามารถวางแนวข้อความในมุมหรือตำแหน่งต่างๆ ภายในเนื้อหา PDF

#### ถาม: เหตุใดฉันจึงต้องการหมุนข้อความในเอกสาร PDF

ตอบ: การหมุนข้อความในเอกสาร PDF อาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การเน้นเนื้อหาเฉพาะ การสร้างการออกแบบเชิงศิลปะ หรือการปรับปรุงเค้าโครงและความสามารถในการอ่าน

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่ได้อย่างไร

 ตอบ: หากต้องการสร้างเอกสาร PDF ใหม่ ให้เริ่มต้น a`Document`วัตถุจากไลบรารี Aspose.PDF คุณสามารถใช้ออบเจ็กต์นี้เพื่อเพิ่มหน้าและเนื้อหาลงใน PDF

#### ถาม: ฉันจะหมุนข้อความโดยใช้ย่อหน้าได้อย่างไร

ตอบ: หากต้องการหมุนข้อความโดยใช้ย่อหน้า:

1.  สร้างก`TextParagraph` วัตถุ.
2.  สร้าง`TextFragment` วัตถุที่มีข้อความและมุมการหมุนที่ต้องการ
3. เพิ่มส่วนข้อความต่อท้ายย่อหน้าข้อความ
4.  สร้างก`TextBuilder` วัตถุและต่อท้ายย่อหน้าข้อความในหน้า PDF เฉพาะ

#### ถาม: ฉันสามารถควบคุมมุมการหมุนของส่วนข้อความแต่ละรายการได้หรือไม่

 ตอบ: ได้ คุณสามารถควบคุมมุมการหมุนของแต่ละบุคคลได้`TextFragment` วัตถุโดยการตั้งค่า`TextState.Rotation` คุณสมบัติ. ค่าบวกหมายถึงการหมุนตามเข็มนาฬิกา ในขณะที่ค่าลบหมายถึงการหมุนทวนเข็มนาฬิกา

#### ถาม: ฉันสามารถใช้มุมการหมุนที่แตกต่างกันกับส่วนของข้อความที่แตกต่างกันภายในย่อหน้าเดียวกันได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้มุมการหมุนที่แตกต่างกันกับมุมต่างๆ ได้`TextFragment` วัตถุภายในย่อหน้าเดียวกันโดยการตั้งค่า`TextState.Rotation` คุณสมบัติของแต่ละส่วนตามลำดับ

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่หมุนแล้วได้อย่างไร

ตอบ: หากต้องการบันทึกเอกสาร PDF ที่หมุนแล้ว ให้ใช้ไฟล์`Save` วิธีการของ`Document` object และระบุเส้นทางและชื่อไฟล์เอาต์พุตที่ต้องการ