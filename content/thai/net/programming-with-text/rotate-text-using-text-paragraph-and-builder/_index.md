---
title: หมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้างในไฟล์ PDF
linktitle: หมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้างในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีหมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้างในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 410
url: /th/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้างในไฟล์ PDF ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

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

## ขั้นตอนที่ 5: สร้างและหมุนย่อหน้าข้อความ

 สร้างก`for` วนซ้ำเพื่อสร้างย่อหน้าข้อความหลายย่อหน้าที่มีการหมุนต่างกัน:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

ปรับตำแหน่งและค่าการหมุนตามความต้องการของคุณ

## ขั้นตอนที่ 6: สร้างและกำหนดค่าส่วนของข้อความ

 สร้างหลายรายการ`TextFragment` วัตถุ ตั้งค่าข้อความและคุณสมบัติ:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
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
}
```

## ขั้นตอนที่ 9: บันทึกเอกสาร PDF

 บันทึกเอกสาร PDF ที่แก้ไขแล้วลงในไฟล์โดยใช้นามสกุล`Save` วิธี:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"TextFragmentTests_Rotated4_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

### ซอร์สโค้ดตัวอย่างสำหรับการหมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้างโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เริ่มต้นวัตถุเอกสาร
Document pdfDocument = new Document();
// รับเฉพาะหน้า
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// ระบุการหมุน
	paragraph.Rotation = i * 90 + 45;
	// สร้างส่วนของข้อความ
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// สร้างส่วนของข้อความ
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// สร้างส่วนของข้อความ
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// ตั้งค่าคุณสมบัติข้อความ
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// สร้างส่วนของข้อความ
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// ตั้งค่าคุณสมบัติข้อความ
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// สร้างวัตถุ TextBuilder
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// เพิ่มส่วนข้อความต่อท้ายหน้า PDF
	textBuilder.AppendParagraph(paragraph);
}
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีการหมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้างในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การสร้างเอกสารไปจนถึงการบันทึกเวอร์ชันที่แก้ไข ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อจัดการการหมุนข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "หมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้าง" คืออะไร

ตอบ: บทช่วยสอน "หมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้าง" ให้คำแนะนำที่ครอบคลุมเกี่ยวกับวิธีใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ย่อหน้าข้อความและตัวสร้างภายในเอกสาร PDF บทช่วยสอนนี้สาธิตคำแนะนำทีละขั้นตอนและรวมตัวอย่างโค้ด C# เพื่อการหมุนเวียนข้อความด้วยย่อหน้าและการจัดรูปแบบที่กำหนดเอง

#### ถาม: บทช่วยสอนนี้แตกต่างจากบทช่วยสอนการหมุนข้อความก่อนหน้าอย่างไร

ตอบ: ไม่เหมือนบทช่วยสอนก่อนหน้านี้ บทช่วยสอนนี้รวมการใช้ย่อหน้าข้อความ ตัวสร้าง และมุมการหมุนเพื่อให้ได้เอฟเฟกต์การหมุนข้อความขั้นสูงยิ่งขึ้น โดยจะสาธิตวิธีการสร้างย่อหน้าข้อความหลายย่อหน้าด้วยมุมการหมุนที่แตกต่างกัน และใช้การจัดรูปแบบแบบกำหนดเองกับส่วนของข้อความแต่ละส่วน

#### ถาม: การใช้ย่อหน้าข้อความและตัวสร้างสำหรับการหมุนข้อความมีความสำคัญอย่างไร

ตอบ: การใช้ย่อหน้าข้อความและตัวสร้างช่วยให้สามารถควบคุมการหมุนและการจัดรูปแบบข้อความได้ดีขึ้น ย่อหน้าข้อความนำเสนอวิธีที่มีโครงสร้างในการจัดระเบียบส่วนของข้อความ ในขณะที่ตัวสร้างอำนวยความสะดวกในการสร้างและจัดการเนื้อหาข้อความภายในเอกสาร PDF

#### ถาม: ฉันสามารถใช้มุมการหมุนที่แตกต่างกันกับแต่ละย่อหน้าของข้อความได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้มุมการหมุนที่แตกต่างกันกับแต่ละย่อหน้าของข้อความได้โดยการตั้งค่า`Rotation` ทรัพย์สินของ`TextParagraph` วัตถุ. สิ่งนี้ช่วยให้คุณสร้างเอฟเฟกต์การหมุนข้อความที่หลากหลายและไดนามิกภายในเอกสาร PDF

#### ถาม: ฉันจะปรับแต่งการจัดรูปแบบของส่วนข้อความภายในย่อหน้าข้อความได้อย่างไร

 ตอบ: คุณสามารถปรับแต่งการจัดรูปแบบของส่วนข้อความได้โดยการตั้งค่าคุณสมบัติต่างๆ ของ`TextState` ภายในแต่ละ`TextFragment` วัตถุ. คุณสมบัติต่างๆ เช่น ขนาดแบบอักษร ประเภทแบบอักษร สีพื้นหน้าและพื้นหลัง และการขีดเส้นใต้ สามารถปรับเพื่อให้ได้เอฟเฟกต์ภาพที่ต้องการ

#### ถาม: ฉันสามารถสร้างเอฟเฟกต์การหมุนข้อความที่ซับซ้อนมากขึ้นโดยใช้วิธีนี้ได้หรือไม่

ตอบ: อย่างแน่นอน ด้วยการสร้างย่อหน้าข้อความหลายย่อหน้าซ้ำๆ ด้วยมุมการหมุนและตัวเลือกการจัดรูปแบบที่แตกต่างกัน คุณจะได้รับเอฟเฟกต์การหมุนข้อความที่ซับซ้อนและดึงดูดสายตา ซึ่งช่วยเพิ่มความสามารถในการอ่านและความสวยงามของเอกสาร PDF ของคุณ

#### ถาม: เป็นไปได้ไหมที่จะรวมการหมุนข้อความเข้ากับเทคนิคการจัดการข้อความอื่นๆ

ตอบ: ได้ คุณสามารถรวมการหมุนข้อความเข้ากับเทคนิคการจัดการข้อความอื่นๆ ที่ไลบรารี Aspose.PDF มอบให้ได้ ซึ่งรวมถึงการเพิ่มตาราง รูปภาพ ไฮเปอร์ลิงก์ และอื่นๆ เพื่อสร้างเอกสาร PDF ที่สมบูรณ์และให้ข้อมูล

#### ถาม: ฉันต้องมีใบอนุญาตพิเศษเพื่อใช้ไลบรารี Aspose.PDF ในโปรเจ็กต์ของฉันหรือไม่

ตอบ: ใช่ คุณต้องมีใบอนุญาต Aspose ที่ถูกต้องเพื่อใช้ไลบรารี Aspose.PDF ในโปรเจ็กต์ของคุณ คุณสามารถขอรับใบอนุญาตได้จากเว็บไซต์ Aspose ซึ่งจะให้ข้อมูลประจำตัวที่จำเป็นแก่คุณในการบูรณาการและใช้งานไลบรารีอย่างมีประสิทธิภาพ