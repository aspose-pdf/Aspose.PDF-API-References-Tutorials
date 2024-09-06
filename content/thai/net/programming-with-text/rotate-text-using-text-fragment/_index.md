---
title: หมุนข้อความโดยใช้ส่วนข้อความในไฟล์ PDF
linktitle: หมุนข้อความโดยใช้ส่วนข้อความในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีหมุนข้อความโดยใช้ชิ้นส่วนข้อความในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 390
url: /th/net/programming-with-text/rotate-text-using-text-fragment/
---
บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ส่วนข้อความในไฟล์ PDF โค้ดต้นฉบับ C# ที่ให้มาจะสาธิตขั้นตอนต่างๆ ทีละขั้นตอน

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

## ขั้นตอนที่ 5: สร้างชิ้นส่วนข้อความ

 สร้างหลาย ๆ`TextFragment` วัตถุ ตั้งค่าข้อความและคุณสมบัติ และระบุตำแหน่งบนหน้า:

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

ปรับแต่งข้อความ ตำแหน่ง และคุณสมบัติอื่นตามต้องการ

## ขั้นตอนที่ 6: สร้าง TextBuilder และผนวกส่วนข้อความ

 สร้าง`TextBuilder` วัตถุที่ใช้`pdfPage` และผนวกส่วนข้อความลงในหน้า PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร PDF

 บันทึกเอกสาร PDF ที่แก้ไขแล้วไปยังไฟล์โดยใช้`Save` วิธี:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 อย่าลืมเปลี่ยน`"TextFragmentTests_Rotated1_out.pdf"` พร้อมชื่อไฟล์เอาท์พุตตามที่ต้องการ

### ตัวอย่างโค้ดต้นฉบับสำหรับการหมุนข้อความโดยใช้ Text Fragment โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// การเริ่มต้นวัตถุเอกสาร
Document pdfDocument = new Document();
// รับหน้าเฉพาะ
Page pdfPage = (Page)pdfDocument.Pages.Add();
// สร้างข้อความส่วนย่อย
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// ตั้งค่าคุณสมบัติข้อความ
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// สร้างชิ้นส่วนข้อความที่หมุน
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// ตั้งค่าคุณสมบัติข้อความ
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// สร้างชิ้นส่วนข้อความที่หมุน
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// ตั้งค่าคุณสมบัติข้อความ
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// สร้างวัตถุ TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// ผนวกส่วนข้อความลงในหน้า PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// บันทึกเอกสาร
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีหมุนข้อความโดยใช้ส่วนข้อความในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนตั้งแต่การสร้างเอกสารจนถึงการบันทึกเวอร์ชันที่แก้ไข ตอนนี้คุณสามารถนำโค้ดนี้ไปใช้กับโปรเจ็กต์ C# ของคุณเองเพื่อควบคุมการหมุนข้อความในไฟล์ PDF

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "หมุนข้อความโดยใช้ส่วนข้อความ" คืออะไร

A: บทช่วยสอน "หมุนข้อความโดยใช้ Text Fragment" มีวัตถุประสงค์เพื่อแนะนำคุณตลอดขั้นตอนการใช้ไลบรารี Aspose.PDF สำหรับ .NET เพื่อหมุนข้อความโดยใช้ Text Fragment ในเอกสาร PDF บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและโค้ดตัวอย่างเพื่อให้บรรลุฟังก์ชันการทำงานนี้

#### ถาม: "การหมุนข้อความโดยใช้ชิ้นส่วนข้อความ" หมายถึงอะไร

A: การหมุนข้อความโดยใช้ส่วนข้อความหมายถึงความสามารถในการหมุนส่วนข้อความแต่ละส่วนในเอกสาร PDF โดยใช้ไลบรารี Aspose.PDF เทคนิคนี้ช่วยให้คุณควบคุมทิศทางของข้อความในมุมหรือตำแหน่งต่างๆ ภายในเนื้อหา PDF ได้

#### ถาม: เหตุใดฉันจึงต้องหมุนชิ้นส่วนข้อความในเอกสาร PDF

ตอบ การหมุนส่วนข้อความในเอกสาร PDF สามารถเป็นประโยชน์ได้หลายประการ เช่น การเน้นเนื้อหาเฉพาะ การสร้างการออกแบบทางศิลปะ หรือการปรับปรุงเค้าโครงและการอ่านได้

#### ถาม: ฉันจะตั้งค่าโครงการสำหรับบทช่วยสอนได้อย่างไร

ก: การตั้งค่าโครงการ:

1. สร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณต้องการ
2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.PDF สำหรับ .NET
3. เพิ่มคำสั่งการใช้ที่จำเป็นลงในไฟล์ C# ของคุณ

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่ได้อย่างไร

 ก: หากต้องการสร้างเอกสาร PDF ใหม่ ให้เริ่มต้น`Document`วัตถุจากไลบรารี Aspose.PDF คุณสามารถใช้วัตถุนี้เพื่อเพิ่มหน้าและเนื้อหาลงใน PDF

#### ถาม: ฉันจะหมุนชิ้นส่วนข้อความโดยใช้ชิ้นส่วนข้อความได้อย่างไร

ก: การหมุนชิ้นส่วนข้อความโดยใช้ชิ้นส่วนข้อความ:

1.  สร้าง`TextFragment` วัตถุ
2. ตั้งค่าข้อความและคุณสมบัติของชิ้นส่วนข้อความ
3. ระบุตำแหน่งของชิ้นส่วนข้อความบนหน้า
4.  ตั้งค่ามุมการหมุนโดยใช้`TextState.Rotation` คุณสมบัติของชิ้นส่วนข้อความ
5.  สร้าง`TextBuilder`วัตถุและผนวกชิ้นส่วนข้อความลงในหน้า PDF

#### ถาม: ฉันสามารถใช้มุมการหมุนที่แตกต่างกันกับชิ้นส่วนข้อความที่แตกต่างกันได้หรือไม่

 A: ใช่ คุณสามารถปรับมุมการหมุนที่แตกต่างกันได้`TextFragment` วัตถุ แต่ละส่วนของข้อความสามารถมีมุมการหมุนของตัวเองได้โดยใช้`TextState.Rotation` คุณสมบัติ.

#### ถาม: ฉันจะบันทึกเอกสาร PDF ที่มีชิ้นส่วนข้อความที่หมุนได้อย่างไร

 ก: หากต้องการบันทึกเอกสาร PDF ที่มีชิ้นส่วนข้อความที่หมุน ให้ใช้`Save` วิธีการของ`Document` วัตถุและระบุเส้นทางและชื่อไฟล์เอาท์พุตที่ต้องการ