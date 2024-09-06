---
title: หมุนข้อความโดยใช้ย่อหน้าในไฟล์ PDF
linktitle: หมุนข้อความโดยใช้ย่อหน้าในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีหมุนข้อความโดยใช้ย่อหน้าในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 380
url: /th/net/programming-with-text/rotate-text-using-paragraph/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ย่อหน้า โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการตามบทช่วยสอน โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose หรือใช้ NuGet เพื่อติดตั้งในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

เริ่มต้นด้วยการสร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น

เพิ่มคำสั่ง using ต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณเพื่อนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## ขั้นตอนที่ 3: สร้างเอกสาร PDF

 เริ่มต้นการใช้งาน`Document` วัตถุที่จะสร้างเอกสาร PDF ใหม่:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 อย่าลืมเปลี่ยน`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 4: เพิ่มหน้า

 รับหน้าเฉพาะจากเอกสารโดยใช้`Pages.Add()` วิธี:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## ขั้นตอนที่ 5: สร้างย่อหน้าข้อความ

 สร้าง`TextParagraph` วัตถุและกำหนดตำแหน่งบนหน้า:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

ปรับค่าตำแหน่งตามความต้องการของคุณ

## ขั้นตอนที่ 6: สร้างและกำหนดค่าส่วนข้อความ

 สร้างหลาย ๆ`TextFragment` วัตถุและตั้งค่าข้อความและคุณสมบัติของวัตถุเหล่านี้:

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

ปรับแต่งข้อความและคุณสมบัติอื่น ๆ ตามความต้องการ

## ขั้นตอนที่ 7: ผนวกข้อความบางส่วนลงในย่อหน้า

 ผนวกส่วนข้อความที่สร้างขึ้นลงในย่อหน้าโดยใช้`AppendLine` วิธี:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## ขั้นตอนที่ 8: สร้าง TextBuilder และผนวกย่อหน้า

 สร้าง`TextBuilder` วัตถุที่ใช้`pdfPage` และผนวกย่อหน้าข้อความลงในหน้า PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## ขั้นตอนที่ 9: บันทึกเอกสาร PDF

 บันทึกเอกสาร PDF ที่แก้ไขแล้วไปยังไฟล์โดยใช้`Save` วิธี:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 อย่าลืมเปลี่ยน`"TextFragmentTests_Rotated2_out.pdf"` พร้อมชื่อไฟล์เอาท์พุตตามที่ต้องการ

### ตัวอย่างโค้ดต้นฉบับสำหรับการหมุนข้อความโดยใช้ย่อหน้าโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// การเริ่มต้นวัตถุเอกสาร
Document pdfDocument = new Document();
// รับหน้าเฉพาะ
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// สร้างข้อความส่วนย่อย
TextFragment textFragment1 = new TextFragment("rotated text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ตั้งค่าการหมุน
textFragment1.TextState.Rotation = 45;
// สร้างข้อความส่วนย่อย
TextFragment textFragment2 = new TextFragment("main text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// สร้างข้อความส่วนย่อย
TextFragment textFragment3 = new TextFragment("another rotated text");
// ตั้งค่าคุณสมบัติข้อความ
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ตั้งค่าการหมุน
textFragment3.TextState.Rotation = -45;
// ผนวกข้อความบางส่วนเข้าในย่อหน้า
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// สร้างวัตถุ TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// ผนวกย่อหน้าข้อความลงในหน้า PDF
textBuilder.AppendParagraph(paragraph);
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีหมุนข้อความโดยใช้ย่อหน้าในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การสร้างเอกสารจนถึงการบันทึกเวอร์ชันที่แก้ไข ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโปรเจ็กต์ C# ของคุณเองเพื่อควบคุมการหมุนข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "หมุนข้อความโดยใช้ย่อหน้า" คืออะไร

A: บทช่วยสอน "หมุนข้อความโดยใช้ย่อหน้า" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดขั้นตอนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ย่อหน้าข้อความในเอกสาร PDF บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและโค้ดตัวอย่างเพื่อให้บรรลุฟังก์ชันการทำงานนี้

#### ถาม: “การหมุนข้อความโดยใช้ย่อหน้า” หมายถึงอะไร

A: การหมุนข้อความโดยใช้ย่อหน้าหมายถึงความสามารถในการหมุนข้อความในเอกสาร PDF โดยใช้ย่อหน้าข้อความ เทคนิคนี้ช่วยให้คุณวางข้อความในมุมหรือตำแหน่งต่างๆ ภายในเนื้อหา PDF ได้

#### ถาม: เหตุใดฉันจึงต้องหมุนข้อความในเอกสาร PDF

ตอบ การหมุนข้อความในเอกสาร PDF สามารถเป็นประโยชน์ได้หลายประการ เช่น การเน้นเนื้อหาเฉพาะ การสร้างการออกแบบทางศิลปะ หรือการปรับปรุงเค้าโครงและการอ่านได้

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่ได้อย่างไร

 ก: หากต้องการสร้างเอกสาร PDF ใหม่ ให้เริ่มต้น`Document`วัตถุจากไลบรารี Aspose.PDF คุณสามารถใช้วัตถุนี้เพื่อเพิ่มหน้าและเนื้อหาลงใน PDF

#### ถาม: ฉันจะหมุนข้อความโดยใช้ย่อหน้าได้อย่างไร

ก: การหมุนข้อความโดยใช้ย่อหน้า:

1.  สร้าง`TextParagraph` วัตถุ.
2.  สร้าง`TextFragment` วัตถุที่มีข้อความและมุมการหมุนตามต้องการ
3. ผนวกชิ้นส่วนข้อความลงในย่อหน้าข้อความ
4.  สร้าง`TextBuilder` วัตถุและผนวกย่อหน้าข้อความลงในหน้า PDF ที่เฉพาะเจาะจง

#### ถาม: ฉันสามารถควบคุมมุมการหมุนของข้อความแต่ละส่วนได้หรือไม่

 A: ใช่ คุณสามารถควบคุมมุมการหมุนของแต่ละรายการได้`TextFragment` วัตถุโดยการตั้งค่า`TextState.Rotation` คุณสมบัติ ค่าบวกแสดงถึงการหมุนตามเข็มนาฬิกา ส่วนค่าลบแสดงถึงการหมุนทวนเข็มนาฬิกา

#### ถาม: ฉันสามารถใช้มุมการหมุนที่แตกต่างกันกับส่วนข้อความที่แตกต่างกันภายในย่อหน้าเดียวกันได้หรือไม่

 A: ใช่ คุณสามารถปรับมุมการหมุนที่แตกต่างกันได้`TextFragment` วัตถุภายในย่อหน้าเดียวกันโดยการตั้งค่า`TextState.Rotation` คุณสมบัติของชิ้นส่วนแต่ละชิ้นให้เหมาะสม

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่หมุนได้อย่างไร

ก: หากต้องการบันทึกเอกสาร PDF ที่หมุน ให้ใช้`Save` วิธีการของ`Document` วัตถุและระบุเส้นทางและชื่อไฟล์เอาท์พุตที่ต้องการ