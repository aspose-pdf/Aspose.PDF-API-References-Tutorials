---
title: หมุนข้อความโดยใช้ส่วนข้อความในไฟล์ PDF
linktitle: หมุนข้อความโดยใช้ส่วนข้อความในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีหมุนข้อความโดยใช้ส่วนย่อยของข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 390
url: /th/net/programming-with-text/rotate-text-using-text-fragment/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ส่วนย่อยของข้อความในไฟล์ PDF ซอร์สโค้ด C# ที่ให้มาสาธิตกระบวนการทีละขั้นตอน

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

## ขั้นตอนที่ 5: สร้างส่วนของข้อความ

 สร้างหลายรายการ`TextFragment` วัตถุ ตั้งค่าข้อความและคุณสมบัติ และระบุตำแหน่งบนเพจ:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

ปรับข้อความ ตำแหน่ง และคุณสมบัติอื่นๆ ตามต้องการ

## ขั้นตอนที่ 6: สร้าง TextBuilder และต่อท้ายส่วนของข้อความ

 สร้างก`TextBuilder` วัตถุโดยใช้`pdfPage` และต่อท้ายส่วนของข้อความในหน้า PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF

 บันทึกเอกสาร PDF ที่แก้ไขแล้วลงในไฟล์โดยใช้นามสกุล`Save` วิธี:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"TextFragmentTests_Rotated1_out.pdf"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

### ตัวอย่างซอร์สโค้ดสำหรับการหมุนข้อความโดยใช้ Text Fragment โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เริ่มต้นวัตถุเอกสาร
Document pdfDocument = new Document();
// รับเฉพาะหน้า
Page pdfPage = (Page)pdfDocument.Pages.Add();
// สร้างส่วนของข้อความ
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// ตั้งค่าคุณสมบัติข้อความ
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// สร้างส่วนของข้อความที่หมุน
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// ตั้งค่าคุณสมบัติข้อความ
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// สร้างส่วนของข้อความที่หมุน
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// ตั้งค่าคุณสมบัติข้อความ
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// สร้างวัตถุ TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// เพิ่มส่วนข้อความต่อท้ายหน้า PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีการหมุนข้อความโดยใช้ส่วนข้อความในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน ตั้งแต่การสร้างเอกสารไปจนถึงการบันทึกเวอร์ชันที่แก้ไข ตอนนี้คุณสามารถรวมโค้ดนี้เข้ากับโปรเจ็กต์ C# ของคุณเองเพื่อจัดการการหมุนข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "หมุนข้อความโดยใช้ส่วนข้อความ" คืออะไร

ตอบ: บทช่วยสอน "หมุนข้อความโดยใช้ส่วนข้อความ" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดกระบวนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ส่วนข้อความในเอกสาร PDF บทช่วยสอนให้คำแนะนำทีละขั้นตอนและโค้ดตัวอย่างเพื่อให้บรรลุฟังก์ชันนี้

#### ถาม: "การหมุนข้อความโดยใช้ส่วนข้อความ" หมายความว่าอย่างไร

ตอบ: การหมุนข้อความโดยใช้ส่วนย่อยของข้อความหมายถึงความสามารถในการใช้การหมุนกับส่วนย่อยของข้อความแต่ละส่วนภายในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF เทคนิคนี้ช่วยให้คุณควบคุมการวางแนวของข้อความในมุมหรือตำแหน่งต่างๆ ภายในเนื้อหา PDF

#### ถาม: เหตุใดฉันจึงต้องการหมุนส่วนของข้อความในเอกสาร PDF

ตอบ: การหมุนส่วนย่อยของข้อความในเอกสาร PDF อาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การเน้นเนื้อหาเฉพาะ การสร้างการออกแบบเชิงศิลปะ หรือการปรับปรุงเค้าโครงและความสามารถในการอ่าน

#### ถาม: ฉันจะตั้งค่าโปรเจ็กต์สำหรับบทช่วยสอนได้อย่างไร

ตอบ: เพื่อตั้งค่าโครงการ:

1. สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบรวม (IDE) ที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET
3. เพิ่มคำสั่งการใช้ที่จำเป็นลงในไฟล์ C# ของคุณ

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่ได้อย่างไร

 ตอบ: หากต้องการสร้างเอกสาร PDF ใหม่ ให้เริ่มต้น a`Document`วัตถุจากไลบรารี Aspose.PDF คุณสามารถใช้ออบเจ็กต์นี้เพื่อเพิ่มหน้าและเนื้อหาลงใน PDF

#### ถาม: ฉันจะหมุนส่วนของข้อความโดยใช้ส่วนของข้อความได้อย่างไร

ตอบ: หากต้องการหมุนส่วนของข้อความโดยใช้ส่วนของข้อความ:

1.  สร้าง`TextFragment` วัตถุ
2. ตั้งค่าข้อความและคุณสมบัติของส่วนของข้อความ
3. ระบุตำแหน่งของส่วนของข้อความบนเพจ
4.  ตั้งค่ามุมการหมุนโดยใช้`TextState.Rotation` คุณสมบัติของส่วนของข้อความ
5.  สร้างก`TextBuilder`object และต่อท้ายส่วนของข้อความในหน้า PDF

#### ถาม: ฉันสามารถใช้มุมการหมุนที่แตกต่างกันกับส่วนของข้อความที่แตกต่างกันได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้มุมการหมุนที่แตกต่างกันกับมุมต่างๆ ได้`TextFragment` วัตถุ ส่วนของข้อความแต่ละส่วนสามารถระบุมุมการหมุนของตัวเองได้โดยใช้`TextState.Rotation` คุณสมบัติ.

#### ถาม: ฉันจะบันทึกเอกสาร PDF ด้วยส่วนข้อความที่หมุนได้อย่างไร

 ตอบ: หากต้องการบันทึกเอกสาร PDF ด้วยส่วนของข้อความที่หมุน ให้ใช้`Save` วิธีการของ`Document` object และระบุเส้นทางและชื่อไฟล์เอาต์พุตที่ต้องการ